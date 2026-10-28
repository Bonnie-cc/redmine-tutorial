# 附錄 A 名詞中英對照

[← 回目錄](../README.md)

本教學用「」標示的按鈕、選單與欄位，一律照 Redmine 官方繁體中文翻譯書寫，和你的畫面一致。內文說明為了好讀，有時會用較口語的說法，例如畫面上的「監看」，內文會說「觀察」。下表的「本教學說法」和「官方介面」兩欄就是兩者的對照；兩欄相同時，代表教學直接沿用官方名稱。

官方翻譯以 Redmine 5.1～7.0 為準，各版本大致相同。遇到名詞和你的畫面對不上時，可以先查英文原文，再對照你的介面；查詢官方文件或上網搜尋解法時，用英文名詞也會找到更多資料。

## 核心概念

| 本教學說法 | 官方介面 | 英文 | 說明 |
|---|---|---|---|
| 專案 | 專案 | Project | 工作的最上層容器，可設定子專案 |
| 子專案 | 子專案 | Subproject | 隸屬於某個父專案的專案 |
| 議題 | 議題 | Issue | 一筆待辦工作，可以是錯誤、功能或支援請求 |
| 追蹤標籤 | 追蹤標籤 | Tracker | 議題的類型，預設有臭蟲（Bug）、功能（Feature）、支援（Support） |
| 狀態 | 狀態 | Status | 議題目前所在的階段 |
| 優先權 | 優先權 | Priority | 議題的重要程度 |
| 版本 | 版本 | Version | 專案的里程碑或發佈版本 |
| 目標版本 | 版本 | Target version | 議題預計在哪個版本完成 |
| 議題分類 | 議題分類 | Issue category | 專案內自訂的議題分類，可設定自動分派 |
| 子議題 | 子任務 | Subtask | 拆解自父議題的小工作 |
| 父議題 | 父議題 | Parent task | 包含子議題的議題 |
| 關聯的議題 | 相關的議題清單 | Related issues | 議題之間的關係，例如阻擋、重複、優先於 |
| 成員 | 成員 | Member | 被加入專案的使用者或群組 |
| 角色 | 角色 | Role | 成員在專案中的身分，決定權限 |
| 群組 | 群組 | Group | 多位使用者的集合，可整批加入專案 |
| 工作流程 | 流程 | Workflow | 各角色可以做的狀態轉換 |
| 模組 | 模組 | Module | 專案可個別啟用的功能，例如 Wiki、甘特圖 |
| 版本庫 | 儲存機制（頁籤）；版本控管（模組名稱） | Repository | 連結的 Git、Subversion 等程式碼版本庫 |

## 預設資料

載入預設組態後建立的名稱，管理員可以自行改名。

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 錯誤 | 臭蟲 | Bug |
| 進行中 | 實作中 | In Progress |
| 回饋中 | 已回應 | Feedback |
| 已結案 | 已結束 | Closed |
| 管理者 | 管理人員 | Manager |
| 開發者 | 開發人員 | Developer |
| 回報者 | 報告人員 | Reporter |
| 緊急 | 速 | Urgent |
| 立刻 | 急 | Immediate |

## 議題欄位

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 主旨 | 主旨 | Subject |
| 概述 | 概述 | Description |
| 分派給、負責人 | 被分派者 | Assignee |
| 作者 | 作者 | Author |
| 觀察者 | 監看員 | Watchers |
| 開始日期 | 開始日期 | Start date |
| 完成日期 | 完成日期 | Due date |
| 預估工時 | 預估工時 | Estimated time |
| 耗用工時 | 耗用工時 | Spent time |
| 完成百分比 | 完成比例（5.1、6.0 為「完成百分比」） | % Done |
| 筆記 | 筆記 | Notes |
| 私人筆記 | 私人筆記 | Private notes |
| 私人 | 私人 | Private |
| 自訂欄位 | 自訂欄位 | Custom field |

## 頂端列與專案頁籤

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 首頁 | 網站首頁 | Home |
| 我的頁面 | 帳戶首頁 | My page |
| 我的帳戶 | 我的帳戶 | My account |
| 專案 | 專案清單 | Projects |
| 管理 | 網站管理 | Administration |
| 說明 | 說明 | Help |
| 概觀 | 概觀 | Overview |
| 活動 | 活動 | Activity |
| 路線圖 | 版本藍圖 | Roadmap |
| 議題 | 議題清單 | Issues |
| 甘特圖 | 甘特圖 | Gantt |
| 行事曆 | 日曆 | Calendar |
| 新聞 | 新聞 | News |
| 文件 | 文件 | Documents |
| 檔案 | 檔案清單 | Files |
| 討論區 | 論壇 | Forums |
| 版本庫 | 儲存機制 | Repository |
| 設定 | 設定 | Settings |

## 管理後台

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 使用者 | 用戶清單 | Users |
| 群組 | 群組清單 | Groups |
| 角色與權限 | 角色與權限 | Roles and permissions |
| 追蹤標籤 | 追蹤標籤清單 | Trackers |
| 議題狀態 | 議題狀態清單 | Issue statuses |
| 工作流程 | 流程 | Workflow |
| 自訂欄位 | 自訂欄位清單 | Custom fields |
| 列舉值清單 | 列舉值清單 | Enumerations |
| LDAP 驗證 | LDAP 驗證 | LDAP authentication |
| 外掛 | 外掛程式 | Plugins |
| 資訊 | 資訊 | Information |
| 非成員 | 非會員 | Non member |
| 匿名使用者 | 匿名者 | Anonymous |
| 收信設定 | 傳入的電子郵件 | Incoming emails |
| 通知設定 | 電子郵件提醒選項 | Email notifications |

## 常見操作

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 新增議題 | 建立新議題 | New issue |
| 編輯 | 編輯 | Edit |
| 記錄工時 | 記錄時間 | Log time |
| 觀察 / 取消觀察 | 監看 / 取消監看 | Watch / Unwatch |
| 複製 | 複製 | Copy |
| 套用 | 套用 | Apply |
| 清除 | 清除 | Clear |
| 儲存 | 儲存 | Save |
| 匯入 | 匯入 | Import |
| 匯出 | 匯出至 | Also available in |
| 鎖定 | 鎖定 | Lock |
| 封存 | 封存 | Archive |
| 結束（專案） | 關閉 | Close |
| 忘記密碼 | 遺失密碼 | Lost password |

## 篩選條件

| 本教學說法 | 官方介面 | 英文 |
|---|---|---|
| 未結案 | 進行中（篩選運算子，代表所有尚未結束的狀態） | open |
| 已結案 | 已結束 | closed |
| 我 | <<我自己>> | <<me>> |
| 無（未分派） | 空值 | none |

---

[← 回目錄](../README.md)
