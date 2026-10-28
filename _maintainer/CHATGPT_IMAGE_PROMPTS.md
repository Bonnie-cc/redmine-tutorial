# 步驟圖 ChatGPT 生圖提示詞

> 本檔是維護者用的資料，一般讀者不需要閱讀。

本檔整理教學中全部步驟圖的 ChatGPT 生圖提示詞與目前狀態。生成後請以指定檔名存入 [`images/`](../images/) 資料夾，同名檔案上傳後會直接覆蓋舊圖，教學頁面就會顯示新圖。

提示詞中所有用引號標出的介面文字，都照 Redmine 官方繁體中文翻譯（`config/locales/zh-TW.yml`，5.1～7.0 版）撰寫，和教學內文「」中的名稱一致。追蹤標籤、狀態、角色、優先權等使用載入預設組態後的預設名稱。

## 使用方式

1. 在 ChatGPT 開一個**新對話專門用來生圖**，第一則訊息先貼上下方的「共用風格前綴」，請它記住這個風格。
2. 之後每張圖只要貼上該圖的提示詞即可。同一個對話中生成的圖，配色與風格會比較一致。
3. 選出第一張滿意的圖後，之後生成其他圖時可以把它一起上傳，並加上一句「請沿用這張圖的風格」，一致性會更好。
4. 提示詞以英文撰寫，畫面中需要出現的繁體中文介面文字已用引號標出。
5. 生成後**逐字檢查畫面中的中文**，並對照下方「常見誤植對照」。有錯字時，不必整張重來，可以直接回覆 ChatGPT「把左上角的『○○』改成『××』，其他保持不變」，請它局部修改。
6. 下載後**確認存成真正的 PNG 格式**（不要只改副檔名），依指定檔名上傳到 `images/`。

### 進階做法：用真實截圖加標註

如果你有架設好的 Redmine（可照 [01 快速試用](../docs/01-quick-try.md) 在自己電腦上架一個，並載入繁體中文的預設組態），最精確的做法是：

1. 用示範資料操作到對應畫面，擷取真實截圖。
2. 把截圖上傳到 ChatGPT，貼上該圖提示詞中 `Annotations:` 之後的部分，並說明「請在這張截圖上加上這些標註，畫面內容不要更動」。

這樣畫面百分之百正確，標註風格也能和其他圖一致。

### 常見誤植對照

生成的圖常會「自動修正」成較口語的用詞，檢查時請特別留意下表左欄的字是否出現在畫面上：

| 不應出現 | 正確（官方介面） |
|---|---|
| 首頁（頂端列） | 網站首頁 |
| 我的頁面、我的工作台、個人設定 | 帳戶首頁（頂端列）、我的帳戶 |
| 專案（頂端列） | 專案清單 |
| 管理（頂端列） | 網站管理 |
| 跳至專案... | 選擇欲前往的專案... |
| 路線圖、行事曆、議題（頁籤） | 版本藍圖、日曆、議題清單 |
| 檔案（專案頁籤） | 檔案清單 |
| 錯誤（追蹤標籤） | 臭蟲 |
| 進行中（議題狀態）、新建、回饋中、已結案 | 實作中、新建立、已回應、已結束 |
| 管理者、開發者、回報者（角色） | 管理人員、開發人員、報告人員 |
| 分派給、指派給 | 被分派者 |
| 目標版本（欄位名稱） | 版本 |
| 完成百分比 | 完成比例 |
| 觀察、觀察者 | 監看、監看員 |
| 記錄工時（按鈕） | 記錄時間 |
| 新增議題、新增專案、新增成員、新增版本 | 建立新議題、建立新專案、建立新成員、建立新版本 |
| 工作流程（後台選單） | 流程 |
| 使用者（後台選單） | 用戶清單 |
| 版本庫 | 儲存機制（頁籤）、版本控管（模組名稱） |
| 未結案（篩選值） | 進行中 |

## 圖片狀態總覽

| 狀態 | 意義 |
|---|---|
| ✅ 可用 | 已生成，畫面文字與教學內文一致 |
| 🔁 需重新生成 | 已有圖片，但畫面文字與目前內文不一致，或有亂碼、看似真實的個人資料 |
| ⏳ 待生成 | 尚未生成，教學頁面目前會顯示為破圖 |

2026-10-28 已依本檔提示詞重新生成全部 27 張圖，並逐張核對畫面文字。

| 檔名 | 章節 | 狀態 | 備註 |
|---|---|---|---|
| `01-01-load-default-config.png` | 1.4 載入預設設定 | ✅ 可用 | |
| `02-01-login.png` | 2.1 登入系統 | ✅ 可用 |  |
| `02-02-layout.png` | 2.2 認識畫面配置 | ✅ 可用 |  |
| `02-03-my-account.png` | 2.3 個人帳戶設定 | ✅ 可用 |  |
| `02-04-my-page.png` | 2.4 我的頁面 | ✅ 可用 |  |
| `03-01-project-list.png` | 3.1 進入專案 | ✅ 可用 |  |
| `03-02-new-issue.png` | 3.2 建立議題 | ✅ 可用 |  |
| `03-03-edit-issue.png` | 3.3 更新議題 | ✅ 可用 | 右側欄有一個虛構的「變更追蹤標籤」區塊，不影響教學 |
| `03-04-log-time.png` | 3.7 記錄工時 | ✅ 可用 |  |
| `03-05-issue-filter.png` | 3.8 篩選議題清單 | ✅ 可用 |  |
| `04-01-formatting-toolbar.png` | 4.1 文字格式 | ✅ 可用 | |
| `05-01-new-project.png` | 5.1 建立專案 | ✅ 可用 |  |
| `05-02-add-members.png` | 5.2 加入專案成員 | ✅ 可用 |  |
| `05-03-new-version.png` | 5.3 設定版本 | ✅ 可用 |  |
| `05-04-bulk-edit.png` | 5.5 分派與追蹤工作 | ✅ 可用 | 「建立新議題」按鈕外多一個紅框，不影響教學 |
| `05-05-gantt.png` | 5.7 甘特圖 | ✅ 可用 | #103 標為逾期，但完成日期其實還沒到 |
| `05-06-roadmap.png` | 5.8 路線圖 | ✅ 可用 |  |
| `05-07-wiki.png` | 5.9 Wiki | ✅ 可用 |  |
| `05-08-time-report.png` | 5.10 工時報表 | ✅ 可用 | 右側欄為虛構內容，含舊詞「依使用者」 |
| `07-01-settings.png` | 7.1 系統設定 | ✅ 可用 |  |
| `07-02-users.png` | 7.2 使用者管理 | ✅ 可用 |  |
| `07-03-roles.png` | 7.4 角色與權限 | ✅ 可用 |  |
| `07-04-workflow.png` | 7.7 工作流程 | ✅ 可用 |  |
| `07-05-custom-fields.png` | 7.8 自訂欄位 | ✅ 可用 |  |
| `08-01-repository-keywords.png` | 8.1 版本庫整合 | ✅ 可用 | |
| `08-02-api-key.png` | 8.2 REST API | ✅ 可用 | |
| `08-03-csv-import.png` | 8.3 CSV 匯入 | ✅ 可用 | |

> 更新圖片後，請一併更新這張表。

## 共用風格前綴

在生圖對話的第一則訊息貼上：

```
I will ask you to create a series of UI tutorial illustrations. Please keep this style for every image in this conversation:

A clean, high-resolution UI tutorial illustration of the Redmine project management web application, in the style of an annotated software screenshot. Use Redmine's default theme: a dark slate-blue top menu bar, a medium blue header band with the project title in white, a row of project tabs below the header, white main content area, light gray right sidebar, small sans-serif text, gray table borders. All interface text must be in Traditional Chinese (Taiwan) exactly as specified in quotes — copy every quoted string character by character, never replace it with a synonym or a more common wording, do not invent extra text, and leave areas blank rather than filling them with made-up words. Unless a prompt says otherwise, the top menu bar always shows on the left "網站首頁", "帳戶首頁", "專案清單", "網站管理", "說明", and on the right "目前登入 王小明", "我的帳戶", "登出"; project tabs belong only in the tab row under the header, never in the top menu bar. Annotation style: bright red numbered circles (1, 2, 3...) with thin red arrows pointing to the relevant UI elements, and red rounded rectangles highlighting key areas. Use only fictional data: the project is "官網改版 2026" with identifier website-2026; URLs and email addresses must use example.com; person names come only from this list: 王小明, 李大華, 陳美玲, 張志強, 林小君. A simple browser window frame with an address bar showing https://redmine.example.com/... is fine; no people, no watermark. Wide landscape format.

Reply "OK" and wait for my first image request.
```

---

## 第 01 章 快速試用

### `01-01-load-default-config.png`｜載入預設設定

```
Show the Redmine "網站管理" (Administration) page of a freshly installed Redmine, with no project header and no project tabs. Address bar: https://redmine.example.com/admin. Top menu bar right side shows "目前登入 admin", "我的帳戶", "登出". Page title "網站管理". In the main area, a pale yellow notice box with two lines of text: "角色、追蹤標籤、議題狀態與流程尚未被設定完成。" and "強烈建議您先載入預設的組態。將預設組態載入之後，您可再變更其中之值。" Below it, a label "語言:" followed by a dropdown showing "Chinese/Traditional (繁體中文)" and a button "載入預設組態". Right sidebar admin menu lists "專案清單", "用戶清單", "群組清單", "角色與權限", "追蹤標籤清單", "議題狀態清單", "流程", "自訂欄位清單", "列舉值清單", "設定", "LDAP 驗證", "外掛程式", "資訊". Annotations: red circle 1 on "網站管理" in the top menu, 2 on the language dropdown, 3 on the "載入預設組態" button.
```

## 第 02 章 入門與介面導覽

### `02-01-login.png`｜登入畫面

```
Show the Redmine sign-in page, not logged in. Address bar: https://redmine.example.com/login. Top menu bar left: "網站首頁", "專案清單", "說明"; top right links "登入" and "註冊". No project tabs. Centered login box with fields labeled "帳戶名稱" and "密碼", a link "遺失密碼" next to the password label, a checkbox "維持已登入狀態", and a button "登入". Annotations: red circle 1 pointing to the "登入" link at top right, red circle 2 pointing to the account name and password fields, red circle 3 pointing to the "登入" button.
```

### `02-02-layout.png`｜畫面配置說明

```
Show the Redmine project overview page for project "官網改版 2026". Address bar: https://redmine.example.com/projects/website-2026. Header band with the project name; on its right a search box labeled "搜尋" and a dropdown "選擇欲前往的專案...". Below the header, a row of tabs: "概觀" (active), "活動", "版本藍圖", "議題清單", "耗用工時", "甘特圖", "日曆", "新聞", "文件", "Wiki", "檔案清單", "設定". Main area shows a box "議題追蹤" with a table: columns "進行中", "已結束", "總計"; rows "臭蟲", "功能", "支援" with small numbers. Below it a box "耗用工時" showing "120.50 小時". Right sidebar shows a box "成員" listing "管理人員: 王小明", "開發人員: 李大華, 陳美玲", "報告人員: 張志強, 林小君". Annotations: four red rounded rectangles labeled 1 (top menu bar), 2 (header with search and project dropdown), 3 (tab row), 4 (content area and sidebar).
```

### `02-03-my-account.png`｜我的帳戶設定

```
Show the Redmine "我的帳戶" page. Address bar: https://redmine.example.com/my/account. No project tabs. Left column form section "資訊" with fields "名字" (小明), "姓氏" (王), "電子郵件" (xiaoming@example.com), "語言" dropdown showing "Chinese/Traditional (繁體中文)". Section "電子郵件提醒選項" with a dropdown "只提醒我監看中或參與中的事物" and a checkbox "不提醒我自己所做的變更". Section "偏好選項" with "時區" dropdown showing "(GMT+08:00) Taipei" and "回應排序" dropdown "以時間由遠至近排序". A "儲存" button at the bottom. Right sidebar has links "變更密碼" and a section "API 存取金鑰" with a link "顯示". Annotations: red circle 1 on the language dropdown, 2 on the email notification dropdown, 3 on the time zone dropdown, 4 on the "儲存" button, 5 on "變更密碼".
```

### `02-04-my-page.png`｜我的頁面

```
Show the Redmine "帳戶首頁" (My page) dashboard. Address bar: https://redmine.example.com/my/page. No project header and no project tabs; the blue header band shows "Redmine". Page title "帳戶首頁". Two columns of blocks: left block titled "分派給我的議題" containing a small issue table with columns "#", "追蹤標籤", "狀態", "主旨" and rows such as "#125 臭蟲 實作中 修正登入後跳轉頁面錯誤", "#124 功能 新建立 新增會員信箱驗證功能"; right block titled "我通報的議題" with a similar table. Top right of the content area has a label "新增:" with a dropdown for adding blocks. Each block has a small "×" icon in its top right corner and a drag handle at its title. Annotations: red circle 1 on the "新增:" dropdown, red circle 2 with a curved dashed arrow showing a block being dragged by its title, red circle 3 on a block's "×" icon.
```

## 第 03 章 一般成員操作

### `03-01-project-list.png`｜專案列表與概觀

```
Split view illustration. Left half: Redmine "專案清單" page (address bar https://redmine.example.com/projects) showing project names "官網改版 2026", "行動 App", "內部系統維護", each with a one-line description. Right half: the "概觀" tab of "官網改版 2026" showing a box "議題追蹤" with columns "進行中", "已結束", "總計" and rows "臭蟲", "功能", "支援", and a box "成員" in the sidebar. A large red arrow goes from the project name on the left to the overview on the right. Top menu bar on both halves follows the standard layout. Annotations: red circle 1 on "專案清單" in the top menu, red circle 2 on the project name "官網改版 2026", red circle 3 on the "選擇欲前往的專案..." dropdown in the header of the right half.
```

### `03-02-new-issue.png`｜建立新議題表單

```
Show the Redmine "建立新議題" form in project "官網改版 2026", tab "議題清單" active. Address bar: https://redmine.example.com/projects/website-2026/issues/new. Fields from top: "追蹤標籤" dropdown set to "臭蟲", "主旨" text field containing "登入頁面在 Safari 無法送出", a checkbox "私人", large "概述" text area with a formatting toolbar, then a two-column grid: left side "狀態" (新建立), "優先權" (高), "被分派者" (empty), "版本" (empty); right side "開始日期", "完成日期", "預估工時" (with suffix "小時"), "完成比例" (0 %). Below: "檔案" with a file chooser button, "監看員" with checkboxes of names "王小明", "李大華", "陳美玲". Bottom buttons "建立" and "繼續建立". Annotations: red circles 1 on tracker, 2 on subject, 3 on description, 4 on the two-column field grid, 5 on file upload, 6 on watchers, 7 on the "建立" button.
```

### `03-03-edit-issue.png`｜編輯議題並更新狀態

```
Show a Redmine issue page "臭蟲 #128" with subject "登入頁面在 Safari 無法送出" in project "官網改版 2026", tab "議題清單" active, in edit mode. Address bar: https://redmine.example.com/issues/128. Top right of the issue has links "編輯", "記錄時間", "監看", "複製". The edit area shows a fieldset "變更屬性" with "狀態" dropdown changed to "實作中" and "完成比例" dropdown set to "50 %"; a fieldset "記錄時間" with fields "耗用工時" ("2"), "活動" dropdown ("開發") and "回應"; a fieldset "筆記" with a text area containing "已找到原因，正在修正表單驗證。" and a checkbox "私人筆記" below it. Buttons "送出" and "預覽" at bottom. Below, a history entry by "張志強". Annotations: red circle 1 on "編輯", 2 on the status dropdown, 3 on "完成比例", 4 on the notes area, 5 on the "記錄時間" fieldset, 6 on "送出".
```

### `03-04-log-time.png`｜記錄工時

```
Show the Redmine time entry form in project "官網改版 2026", tab "耗用工時" active, with page heading "耗用工時". Address bar: https://redmine.example.com/projects/website-2026/time_entries/new. Fields: "議題" with "128" and the issue subject shown next to it, "日期" with a date picker showing 2026-10-27, "小時" with "2.5", "回應" text field "修正表單驗證", "活動" dropdown "開發". Buttons "建立" and "繼續建立". Annotations: red circle 1 on the issue field, 2 on the "小時" field, 3 on the "活動" dropdown, 4 on the "建立" button.
```

### `03-05-issue-filter.png`｜議題篩選與自訂查詢

```
Show the Redmine "議題清單" page in project "官網改版 2026", tab "議題清單" active. Address bar: https://redmine.example.com/projects/website-2026/issues. Top section "篩選條件" expanded with rows: checkbox "狀態" with operator dropdown "進行中"; checkbox "被分派者" with operator "等於" and value "<<我自己>>". On the right a dropdown labeled "加入新篩選條件". Collapsed section "選項清單". Below, links "套用", "清除", "儲存". Then an issue table with columns "#", "追蹤標籤", "狀態", "優先權", "主旨", "被分派者", "更新日期"; rows use trackers "臭蟲" and "功能", statuses "新建立" and "實作中", and assignee "王小明". Right sidebar has a section "我的自訂查詢" listing "我未完成的工作". Annotations: red circle 1 on the filter rows, 2 on "加入新篩選條件", 3 on "選項清單", 4 on "套用", 5 on "儲存", 6 on the sidebar saved query.
```

## 第 04 章 文字格式與連結語法

### `04-01-formatting-toolbar.png`｜編輯工具列與預覽

```
Show the "概述" editor of the Redmine "建立新議題" form in project "官網改版 2026". Above the text area there are two tabs "編輯" and "預覽", and a formatting toolbar with icon buttons for bold, italic, underline, strikethrough, inline code, headings, lists, quote, code block, link, image, table, and a small "?" help icon at the far right end of the toolbar. The text area contains CommonMark Markdown lines: "### 重現步驟", "1. 用 Safari 開啟登入頁", "2. 按下 **登入**", "相關議題：#128". Annotations: red circle 1 on the toolbar, 2 on the "?" help icon, 3 on the "預覽" tab.
```

## 第 05 章 專案經理操作

### `05-01-new-project.png`｜建立新專案表單

```
Show the Redmine "建立新專案" form. Address bar: https://redmine.example.com/projects/new. No project tabs. Fields: "名稱" with "官網改版 2026", "概述" text area, "代碼" with "website-2026" and small gray hint text below it, "網站首頁", checkbox "公開" (unchecked), "父專案" dropdown, checkbox "繼承父專案成員". Fieldset "模組" with checkboxes "議題追蹤", "工時追蹤", "新聞", "文件", "檔案", "Wiki", "版本控管", "討論區", "日曆", "甘特圖". Fieldset "追蹤標籤" with checkboxes "臭蟲", "功能", "支援". Buttons "建立" and "繼續建立". Annotations: red circle 1 on name, 2 on identifier field with a small red note label "建立後無法修改", 3 on "公開" checkbox, 4 on the modules fieldset, 5 on the trackers fieldset, 6 on "建立".
```

### `05-02-add-members.png`｜建立新成員

```
Show Redmine project "官網改版 2026" with the "設定" tab active. Below the tabs, settings sub-tabs: "專案", "成員" (active), "議題追蹤", "版本", "議題分類清單", "儲存機制清單", "論壇", "工時追蹤". A link "建立新成員" at top right of the member table. A modal dialog titled "建立新成員" overlays the page: a label "搜尋用戶或群組：" with a search field, a list of users and groups with checkboxes ("前端組", "王小明", "李大華" checked; "陳美玲" unchecked), and a section "角色" with checkboxes "管理人員", "開發人員" (checked), "報告人員". Button "新增". Behind the modal, the member table with columns "用戶 / 群組", "角色". Annotations: red circle 1 on "設定" tab, 2 on "成員" sub-tab, 3 on user checkboxes, 4 on role checkboxes, 5 on the "新增" button.
```

### `05-03-new-version.png`｜建立新版本

```
Show the Redmine "建立新版本" form for project "官網改版 2026", tab "設定" active. Address bar: https://redmine.example.com/projects/website-2026/versions/new. Fields: "名稱" with "v1.0", "概述", "狀態" dropdown expanded showing exactly three options "進行中" (selected), "已鎖定", "已結束"; a separate text field "Wiki 網頁" below it (not inside the dropdown); "日期" with a date picker showing 2026-11-20, "共用" dropdown expanded showing "不共用" (selected), "與子專案共用", "與專案階層架構共用", "與專案樹共用", "與全部的專案共用". Buttons "建立" and "繼續建立". Annotations: red circle 1 on name, 2 on the status dropdown with its three options, 3 on date, 4 on sharing, 5 on "建立".
```

### `05-04-bulk-edit.png`｜批次編輯議題的右鍵選單

```
Show the Redmine "議題清單" page of project "官網改版 2026" with three rows checked and highlighted in light yellow. Table columns "#", "追蹤標籤", "狀態", "優先權", "主旨", "被分派者", "版本". A right-click context menu is open beside them with items: "大量編輯", "狀態 ▸", "追蹤標籤 ▸", "優先權 ▸", "版本 ▸", "被分派者 ▸" (hovered, showing a submenu with "<<我自己>>", "王小明", "李大華", "空值"), "完成比例 ▸", "監看", "複製", "刪除". Annotations: red circle 1 on the checked checkboxes, 2 on the context menu, 3 on the "被分派者" submenu.
```

### `05-05-gantt.png`｜甘特圖

```
Show the Redmine "甘特圖" tab of project "官網改版 2026". Top controls: a number dropdown "3" followed by the text "個月, 開始月份", then dropdowns "10月" and "2026", and a link "套用". Left column lists version "第一階段：首頁與形象頁" and issues under it ("#101 首頁視覺設計", "#102 首頁切版", "#103 首頁 RWD 調整"). Right side shows a timeline grid by weeks with horizontal bars: the unfinished part of each bar is gray and the completed part is green, each bar followed by its percentage; one bar has a red section indicating it is overdue; a diamond marker indicates the version due date, and a vertical dashed red line marks today. Bottom right has the text "匯出至:" followed by links "PDF" and "PNG". Annotations: red circle 1 on the date controls, 2 on a progress bar, 3 on the overdue red section, 4 on the version diamond, 5 on the export links.
```

### `05-06-roadmap.png`｜版本藍圖

```
Show the Redmine "版本藍圖" tab of project "官網改版 2026". Address bar: https://redmine.example.com/projects/website-2026/roadmap. Two version sections: "第一階段：首頁與形象頁" with due date "2026-11-20", a green progress bar at 65 percent, and the text "13 個議題 (8 已結束 — 5 進行中)", followed by a short list of related issues ("臭蟲 #128 登入頁面在 Safari 無法送出", "功能 #102 首頁切版"); "第二階段：會員中心" with a progress bar at 10 percent. Right sidebar with checkboxes "臭蟲", "功能", "支援" and "顯示已完成的版本", and a "套用" button. Annotations: red circle 1 on a version title, 2 on the progress bar, 3 on the issue list, 4 on the sidebar filters.
```

### `05-07-wiki.png`｜Wiki 編輯畫面

```
Show the Redmine "Wiki" tab of project "官網改版 2026" in edit mode. Address bar: https://redmine.example.com/projects/website-2026/wiki/開發規範/edit. Page heading "開發規範". A formatting toolbar above a text area containing CommonMark Markdown lines: "# 開發規範", "{{toc}}", "請參考 [[部署步驟]]", "相關議題：#128". Above the text area, tabs "編輯" and "預覽". Below the editor, a "回應" field and buttons "儲存" and "預覽". Right sidebar titled "Wiki" with links "首頁", "依標題索引", "依日期索引". Annotations: red circle 1 on the toolbar, 2 on the "[[部署步驟]]" text, 3 on "#128", 4 on the "儲存" button, 5 on the sidebar index links.
```

### `05-08-time-report.png`｜工時報告

```
Show the Redmine "耗用工時" tab of project "官網改版 2026", with sub-tabs "明細" and "報告", and "報告" active. Controls: a "日期" range filter, a dropdown labeled "明細" set to "月", and a dropdown labeled "新增" to add criteria, with "用戶" and "活動" already shown as selected criteria. A table with rows of user names ("王小明", "李大華", "陳美玲") and activities ("設計", "開發"), columns per month "2026-08", "2026-09", "2026-10", and a "總計" column. Bottom text "匯出至:" with a link "CSV". Annotations: red circle 1 on the "報告" sub-tab, 2 on the "新增" criteria selector, 3 on the "明細" dropdown, 4 on the totals column, 5 on the "CSV" export link.
```

## 第 07 章 系統管理員操作

### `07-01-settings.png`｜系統設定

```
Show the Redmine "網站管理" > "設定" page. Address bar: https://redmine.example.com/settings. No project tabs. Page title "設定". A row of tabs: "一般", "顯示", "驗證", "API", "專案清單", "用戶清單", "議題追蹤", "工時追蹤", "檔案", "電子郵件提醒選項", "傳入的電子郵件", "儲存機制清單". The "驗證" tab is active, showing a checkbox "需要驗證" checked, a dropdown "註冊選項" set to "手動啟用帳戶", "密碼最小長度" field "8", a dropdown "雙因素驗證" set to "選用項", and a "儲存" button. Right sidebar admin menu lists "專案清單", "用戶清單", "群組清單", "角色與權限", "追蹤標籤清單", "議題狀態清單", "流程", "自訂欄位清單", "列舉值清單", "設定" (highlighted), "LDAP 驗證", "外掛程式", "資訊". Annotations: red circle 1 on "設定" in the admin menu, 2 on the tabs row, 3 on "需要驗證", 4 on the "註冊選項" dropdown, 5 on "儲存".
```

### `07-02-users.png`｜用戶清單

```
Show the Redmine "網站管理" > "用戶清單" page. Address bar: https://redmine.example.com/users. No project tabs. Page title "用戶清單", a link "建立新用戶" at top right. A "篩選條件" section with a row: checkbox "狀態", operator "等於", value "活動中". Links "套用", "清除". Table columns "帳戶名稱", "名字", "姓氏", "電子郵件", "管理者", "建立日期", "最近連線日期", and a "…" button at the end of each row. Rows use exactly these fictional users: admin (admin@example.com, admin checked), xiaoming 小明 王 (xiaoming@example.com), dahua 大華 李 (dahua@example.com), meiling 美玲 陳 (meiling@example.com), zhiqiang 志強 張 (zhiqiang@example.com). On the "zhiqiang" row, a small context menu is open with items "編輯", "鎖定", "刪除". Annotations: red circle 1 on "建立新用戶", 2 on the status filter, 3 on the "鎖定" menu item with a small red note label "離職人員請鎖定，不要刪除".
```

### `07-03-roles.png`｜角色與權限

```
Show the Redmine "角色與權限" edit page for role "開發人員" under "網站管理". Address bar: https://redmine.example.com/roles/2/edit. No project tabs. Page title "角色與權限 » 開發人員". Top fields: "名稱" with "開發人員", "議題可見度" dropdown "所有非私人議題". Below, a "權限" section with permission checkboxes grouped in fieldsets titled "專案", "議題追蹤", "工時追蹤", "Wiki". Items: under "專案": "編輯專案", "管理成員", "管理版本"; under "議題追蹤": "檢視議題", "新增議題", "編輯議題", "新增筆記", "設定筆記為私人筆記", "檢視私人筆記", "管理子任務", "刪除議題"; under "工時追蹤": "檢視耗用工時", "紀錄耗用工時", "編輯自己的工時記錄"; under "Wiki": "檢視 wiki", "編輯 wiki 頁面". Each permission appears only once. "儲存" button. Annotations: red circle 1 on the role name, 2 on the issue visibility dropdown, 3 on the "議題追蹤" permission fieldset, 4 on "儲存".
```

### `07-04-workflow.png`｜流程設定

```
Show the Redmine "流程" (Workflow) edit page under "網站管理". Address bar: https://redmine.example.com/workflows/edit. No project tabs. Page title "流程". Top selectors: "角色" dropdown "開發人員", "追蹤標籤" dropdown "臭蟲", a checkbox "僅顯示此追蹤標籤所使用之狀態", button "編輯". Tabs "狀態轉換" (active) and "欄位權限". A matrix table: row header "目前狀態" listing "新建立", "實作中", "已解決", "已回應", "已結束", "已拒絕"; column header "可變更至以下狀態" with the same statuses; some cells checked. Below, two collapsed sections "用戶為作者時額外允許的流程轉換" and "用戶為被分派者時額外允許的流程轉換". "儲存" button. Annotations: red circle 1 on the role and tracker selectors, 2 on the matrix with an arrow from row "新建立" to the checkbox in column "實作中", 3 on the "欄位權限" tab, 4 on "儲存".
```

### `07-05-custom-fields.png`｜建立新自訂欄位

```
Show the Redmine "建立新自訂欄位" form for type "議題" under "網站管理" > "自訂欄位清單". Address bar: https://redmine.example.com/custom_fields/new?type=IssueCustomField. No project tabs. Fields: "格式" dropdown "清單", "名稱" with "影響範圍", "可能值" text area with lines "前台", "後台", "資料庫", checkboxes "必填", "用來作為篩選器", "可用做搜尋條件". Right side fieldsets "追蹤標籤" with checkboxes "臭蟲", "功能", "支援", and "專案" with a checkbox "給全部的專案". Buttons "建立" and "繼續建立". Annotations: red circle 1 on format, 2 on possible values, 3 on the "必填" checkbox, 4 on the tracker checkboxes, 5 on "建立".
```

## 第 08 章 進階功能與整合

### `08-01-repository-keywords.png`｜儲存機制關鍵字設定

```
Show the Redmine "網站管理" > "設定" page with the "儲存機制清單" tab active. Address bar: https://redmine.example.com/settings?tab=repositories. No project tabs. Content: a checkbox "自動擷取認可" (unchecked); a fieldset titled "認可訊息中參照(或修正)議題之關鍵字" containing a text field "認可用於參照之關鍵字" with "refs,references,IssueID"; a table with columns "追蹤標籤", "認可用於修正之關鍵字", "已套用狀態", "完成比例" and one row "全部", "fixes,closes", "已解決", "100 %"; a checkbox "啟用認可中的時間記錄" (checked) with a dropdown "時間記錄對應的活動" set to "開發". "儲存" button. Annotations: red circle 1 on the "儲存機制清單" tab, 2 on the referencing keywords field, 3 on the fixing keywords row, 4 on the time logging checkbox, 5 on "儲存".
```

### `08-02-api-key.png`｜API 存取金鑰

```
Show the Redmine "我的帳戶" page. Address bar: https://redmine.example.com/my/account. No project tabs. The main area shows only one section "資訊" with exactly four fields "名字" (小明), "姓氏" (王), "電子郵件" (xiaoming@example.com), "語言" dropdown "Chinese/Traditional (繁體中文)", then a "儲存" button; no other sections. The right sidebar has a section "API 存取金鑰" with a link "顯示", the text "API 存取金鑰建立於 3 天 之前", and a link "回復". A small popup box next to it displays a masked key "••••••••••••••••••••••••". Annotations: red circle 1 on the "API 存取金鑰" section, 2 on "顯示", 3 on "回復", with a small red note label "請勿外流".
```

### `08-03-csv-import.png`｜CSV 匯入欄位對應

```
Show the Redmine "匯入議題" field mapping page for project "官網改版 2026", tab "議題清單" active. Address bar: https://redmine.example.com/imports/1/mapping. Page title "匯入議題". A form maps Redmine fields to CSV columns using dropdowns, laid out in two columns: "專案" → "官網改版 2026", "追蹤標籤" → "追蹤標籤", "主旨" → "主旨", "概述" → "概述", "被分派者" → "被分派者", "優先權" → "優先權", "開始日期" → "開始日期", "完成日期" → "完成日期". Below, a fieldset "檔案內容預覽" with a table of three rows: a header row "追蹤標籤 | 主旨 | 概述 | 被分派者 | 優先權 | 開始日期 | 完成日期", then "功能 | 首頁視覺設計 | 依品牌手冊設計首頁 | 陳美玲 | 正常 | 2026-11-01 | 2026-11-07" and "功能 | 首頁切版 | 依設計稿切版 | 李大華 | 正常 | 2026-11-08 | 2026-11-14". Buttons "« 上一頁" and "匯入". Annotations: red circle 1 on the page title, 2 on the field mapping dropdowns, 3 on the preview table, 4 on "匯入".
```
