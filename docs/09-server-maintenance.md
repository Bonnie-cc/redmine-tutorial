# 09 伺服器維運

[← 回目錄](../README.md)

> **本章你會學到**：用 Docker Compose 架設給團隊正式使用的 Redmine、設定寄信、備份與還原、版本升級，以及基本的安全建議。

> 本章以 Docker Compose 搭配 PostgreSQL 為例，這是目前最容易維護的方式之一。如果你是直接在伺服器上安裝 Ruby 與 Redmine，請改參考官方的安裝與升級文件，連結見 [附錄 D](appendix-d-resources.md)。

## 9.1 正式環境部署

和 [01 快速試用](01-quick-try.md) 不同，正式環境需要做到三件事：使用獨立的資料庫、資料存放在容器外面、固定 Redmine 版本。

1. 在伺服器上建立資料夾，例如 `/opt/redmine`，以及會用到的子資料夾：

   ```bash
   mkdir -p /opt/redmine/{config,files,plugins,backup}
   cd /opt/redmine
   ```

   接著在 `/opt/redmine` 中建立 `docker-compose.yml`：

   ```yaml
   services:
     redmine:
       image: redmine:7.0          # 固定版本，不要用 latest
       restart: always
       ports:
         - "3000:3000"
       environment:
         REDMINE_DB_POSTGRES: db
         REDMINE_DB_DATABASE: redmine
         REDMINE_DB_USERNAME: redmine
         REDMINE_DB_PASSWORD: 請改成一組強密碼
         SECRET_KEY_BASE: 請改成一組很長的隨機字串
       volumes:
         - ./files:/usr/src/redmine/files                                  # 附件
         - ./plugins:/usr/src/redmine/plugins                              # 外掛
         - ./config/configuration.yml:/usr/src/redmine/config/configuration.yml  # 寄信等設定
       depends_on:
         - db

     db:
       image: postgres:16
       restart: always
       environment:
         POSTGRES_DB: redmine
         POSTGRES_USER: redmine
         POSTGRES_PASSWORD: 請改成一組強密碼    # 與上方 REDMINE_DB_PASSWORD 相同
       volumes:
         - ./db-data:/var/lib/postgresql/data
   ```

2. 隨機字串可以用以下指令產生：

   ```bash
   openssl rand -hex 64
   ```

3. 建立寄信設定檔 `config/configuration.yml`（內容見 [9.2](#92-寄信設定)），然後啟動：

   ```bash
   docker compose up -d
   ```

4. 用瀏覽器開啟 `http://伺服器位址:3000`，依 [1.3](01-quick-try.md#13-首次登入) 與 [1.4](01-quick-try.md#14-載入預設設定) 完成首次登入與載入預設設定。

> 映像檔的版本標籤請到 Docker Hub 的 redmine 頁面確認目前有哪些可用的版本。如果你需要使用尚未支援 7.x 的外掛，可以先改用 `redmine:6.1`。`latest` 會在你不注意時自動跳到新版本，正式環境請一律指定版本。

## 9.2 寄信設定

Redmine 寄送通知信需要 SMTP 伺服器，設定寫在 `config/configuration.yml`：

```yaml
production:
  email_delivery:
    delivery_method: :smtp
    smtp_settings:
      address: smtp.example.com
      port: 587
      domain: example.com
      authentication: :login
      user_name: redmine@example.com
      password: 信箱密碼
      enable_starttls_auto: true
```

修改後執行 `docker compose restart redmine` 重新啟動，再到「網站管理」→「設定」→「電子郵件提醒選項」按「寄送測試郵件」確認。

> 使用 Gmail、Microsoft 365 等服務寄信時，通常需要使用「應用程式密碼」而非帳號的登入密碼，請參考各服務的說明。

## 9.3 備份

Redmine 的資料分成兩部分，**兩個都要備份**，缺一不可：

| 資料 | 內容 | 位置（依 9.1 的設定） |
|---|---|---|
| 資料庫 | 專案、議題、Wiki、使用者、工時等所有文字資料 | PostgreSQL 容器 |
| 附件目錄 | 所有上傳的檔案與圖片 | `/opt/redmine/files` |

**備份資料庫**

```bash
cd /opt/redmine
docker compose exec -T db pg_dump -U redmine redmine > backup/redmine-db-$(date +%Y%m%d).sql
```

**備份附件**

```bash
tar czf backup/redmine-files-$(date +%Y%m%d).tar.gz files
```

**建議做法**

- 把以上指令寫成腳本，用 cron 每天自動執行。
- 備份檔要另外存放到**其他機器或雲端空間**，和 Redmine 放在同一台伺服器上的備份，在伺服器故障時一樣會遺失。
- 保留最近一段時間的備份（例如 30 天），並自動刪除更舊的檔案。
- 同時備份 `docker-compose.yml`、`config/configuration.yml` 與 `plugins/`。
- **定期練習還原**。從來沒有還原成功過的備份，不算真正的備份。

## 9.4 還原

> ⚠️ 還原會覆蓋目前所有資料，請先確認你選的是正確的備份檔，並建議先在另一台測試機上練習。

```bash
cd /opt/redmine
docker compose stop redmine

# 還原資料庫
docker compose exec -T db dropdb -U redmine redmine
docker compose exec -T db createdb -U redmine redmine
docker compose exec -T db psql -U redmine redmine < backup/redmine-db-20261028.sql

# 還原附件
rm -rf files
tar xzf backup/redmine-files-20261028.tar.gz

docker compose start redmine
```

還原後登入檢查幾筆議題與附件是否正常。

## 9.5 升級

1. 閱讀新版本的發佈說明（Changelog），特別注意不相容的變更。
2. 確認所有外掛都支援新版本。
3. **完整備份**，見 [9.3](#93-備份)。
4. 修改 `docker-compose.yml` 中的版本標籤，例如從 `redmine:6.1` 改為 `redmine:7.0`。
5. 執行：

   ```bash
   docker compose pull
   docker compose up -d
   docker compose logs -f redmine
   ```

   官方映像檔在啟動時會自動更新資料庫結構。觀察記錄中沒有錯誤訊息，並能正常開啟網頁，就代表升級完成。
6. 到「網站管理」→「資訊」確認版本號已更新，並抽查幾個常用功能。

> 跨大版本升級（例如 6.x 到 7.x）前，強烈建議先用備份資料在測試環境演練一次。

## 9.6 安全建議

- **一律使用 HTTPS**：在 Redmine 前面加一層反向代理（例如 Nginx、Caddy），由它處理 SSL 憑證，不要讓 3000 埠直接對外開放。設定好後，記得到「網站管理」→「設定」→「一般」把「協定」改為 HTTPS。
- **保持更新**：Redmine 會不定期發佈安全性修正版本，請關注官方公告並及時升級。
- **最小權限**：系統管理員帳號越少越好，並要求管理員啟用雙因素驗證，見 [7.11](07-administrator.md#711-安全性設定)。
- **檢查公開設定**：確認「需要驗證」、「匿名者」角色、專案公開設定符合你的需求，見 [7.1](07-administrator.md#71-系統設定)。
- **防火牆**：資料庫連接埠不要對外開放。依 9.1 的設定，PostgreSQL 只在 Docker 內部網路中使用，沒有對外公開。

---

上一章：[← 08 進階功能與整合](08-integration.md)｜下一章：[10 常見問題 →](10-faq.md)
