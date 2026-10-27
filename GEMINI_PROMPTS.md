# 步驟圖 Gemini 提示詞

本檔整理教學中全部 22 張步驟圖的生成提示詞。生成後請以指定檔名存入 [`images/`](images/) 資料夾，教學頁面就會自動顯示。

## 使用方式

1. 每次生成時，先貼上下方的「共用風格前綴」，再接著貼上該圖的提示詞。
2. 提示詞以英文撰寫，因為目前圖像模型對英文指令的遵循度較好；畫面中需要出現的繁體中文介面文字已用引號標出。
3. 生成後若中文字出現錯字或亂碼，可請 Gemini 重新生成，或改用影像編輯工具修正文字。
4. 建議輸出比例 16:9，存成 PNG。

> AI 生成的介面圖是「示意圖」，細節不一定與實際畫面完全相同。如果追求精確，也可以用真實的 Redmine 截圖，再請 Gemini 依照提示詞中的「標註」部分加上紅色編號與箭頭。

## 共用風格前綴

```
A clean, high-resolution UI tutorial illustration of the Redmine project management web application, in the style of an annotated software screenshot. Use Redmine's default theme: a dark slate-blue top menu bar, a medium blue header band with the project title in white, white main content area, light gray right sidebar, small sans-serif text, gray table borders. All interface text must be in Traditional Chinese exactly as specified in quotes. Annotation style: bright red numbered circles (1, 2, 3...) with thin red arrows pointing to the relevant UI elements, and red rounded rectangles highlighting key areas. Flat, crisp, no browser chrome other than a simple address bar, no people, no watermark, 16:9 aspect ratio.
```

---

## 第 1 章 入門與介面導覽

### `01-01-login.png`｜登入畫面

```
Show the Redmine sign-in page. Centered login box with fields labeled "登入帳號" and "密碼", a checkbox "保持已登入狀態", a link "忘記密碼", and a button "登入". Top right corner of the page shows links "登入" and "註冊". Annotations: red circle 1 pointing to "登入" link at top right, red circle 2 pointing to the username and password fields, red circle 3 pointing to the "登入" button.
```

### `01-02-layout.png`｜畫面配置說明

```
Show a Redmine project overview page for a project named "官網改版 2026". Top menu bar left side: "首頁", "我的頁面", "專案", "管理"; right side: "登入身分 王小明", "我的帳戶", "登出". Header band with project name and a search box labeled "搜尋" plus a dropdown "跳至專案...". Below, a row of tabs: "概觀", "活動", "路線圖", "議題", "耗用工時", "甘特圖", "行事曆", "新聞", "文件", "Wiki", "檔案", "設定". Main area shows "議題追蹤" summary table; right sidebar shows "成員" list. Annotations: four red rounded rectangles labeled 1 (top menu bar), 2 (header with search), 3 (tab row), 4 (content area and sidebar).
```

### `01-03-my-account.png`｜我的帳戶設定

```
Show Redmine "我的帳戶" page. Left column form section "資訊" with fields "名字", "姓氏", "電子郵件", "語言" dropdown showing "Traditional Chinese (繁體中文)". Section "電子郵件通知" with a dropdown "只通知我觀察或參與的事項". Section "偏好選項" with "時區" dropdown showing "(GMT+08:00) Taipei". A "儲存" button at the bottom. Right sidebar has link "變更密碼". Annotations: red circle 1 on the language dropdown, 2 on the email notification dropdown, 3 on the time zone dropdown, 4 on the "儲存" button, 5 on "變更密碼".
```

### `01-04-my-page.png`｜我的頁面

```
Show Redmine "我的頁面" dashboard. Two columns of blocks: left block titled "分派給我的議題" containing a small issue table with columns "#", "追蹤標籤", "狀態", "主旨"; right block titled "我回報的議題". Top right has a dropdown "新增..." for adding blocks. Each block has a small "×" in its top right corner. Annotations: red circle 1 on the "新增..." dropdown, red circle 2 with a curved arrow showing a block being dragged by its title, red circle 3 on a block's "×" icon.
```

---

## 第 2 章 一般成員操作

### `02-01-project-list.png`｜專案列表與概觀

```
Split view illustration. Left half: Redmine "專案" list page showing project names "官網改版 2026", "行動 App", "內部系統維護" with short descriptions. Right half: the overview page of "官網改版 2026" showing "議題追蹤" box with counts per tracker ("錯誤", "功能", "支援"), and a "成員" box in the sidebar. A large red arrow goes from the project name on the left to the overview on the right. Annotations: red circle 1 on top menu "專案", red circle 2 on project name, red circle 3 on the "跳至專案..." dropdown in the header.
```

### `02-02-new-issue.png`｜新增議題表單

```
Show the Redmine "新增議題" form. Fields from top: "追蹤標籤" dropdown set to "錯誤", "主旨" text field containing "登入頁面在 Safari 無法送出", large "概述" text area with a toolbar, then a two-column grid: left side "狀態" (新建立), "優先權" (高), "分派給", "目標版本"; right side "開始日期", "完成日期", "預估工時", "完成百分比". Below: "檔案" with a "選擇檔案" button, "觀察者" with checkboxes of names. Bottom buttons "建立" and "建立並繼續". Annotations: red circles 1 on tracker, 2 on subject, 3 on description, 4 on the two-column field grid, 5 on file upload, 6 on watchers, 7 on the "建立" button.
```

### `02-03-edit-issue.png`｜編輯議題並更新狀態

```
Show a Redmine issue page "錯誤 #128 登入頁面在 Safari 無法送出" in edit mode. Top right has links "編輯", "記錄工時", "觀察", "複製". The edit area shows "狀態" dropdown changed to "進行中", "完成百分比" dropdown set to "50 %", a "筆記" text area with text "已找到原因，正在修正表單驗證。", and a "耗用工時" section with "耗用工時" field "2" and "活動" dropdown "開發". "送出" button at bottom. Below, a history entry by another user. Annotations: red circle 1 on "編輯", 2 on the status dropdown, 3 on percent done, 4 on notes area, 5 on time section, 6 on "送出".
```

### `02-04-log-time.png`｜記錄工時

```
Show the Redmine "耗用工時" form with heading "耗用工時". Fields: "議題" with "#128", "日期" with a date picker showing 2026-10-27, "耗用工時" with "2.5", "留言" text field "修正表單驗證", "活動" dropdown "開發". Buttons "建立" and "建立並繼續". Annotations: red circle 1 on the issue field, 2 on hours field, 3 on activity dropdown, 4 on the "建立" button.
```

### `02-05-issue-filter.png`｜議題篩選與自訂查詢

```
Show Redmine "議題" list page. Top section "篩選條件" expanded with rows: checkbox "狀態" with "未結案"; checkbox "分派給" with "等於" and "<<我>>". On the right a dropdown "新增篩選條件". Collapsed section "選項". Below, links "套用", "清除", "儲存". Then an issue table with columns "#", "追蹤標籤", "狀態", "優先權", "主旨", "分派給", "更新時間". Right sidebar has section "自訂查詢" listing "我的未結案議題". Annotations: red circle 1 on filter rows, 2 on "新增篩選條件", 3 on "選項", 4 on "套用", 5 on "儲存", 6 on the sidebar saved query.
```

---

## 第 3 章 專案經理操作

### `03-01-new-project.png`｜新增專案表單

```
Show Redmine "新增專案" form. Fields: "名稱" with "官網改版 2026", "概述" text area, "代碼" with "website-2026" and small gray hint text, "首頁", checkbox "公開" (unchecked), "父專案" dropdown, checkbox "繼承成員". Section "模組" with checkboxes "議題追蹤", "工時追蹤", "新聞", "文件", "檔案", "Wiki", "版本庫", "討論版", "行事曆", "甘特圖". Section "追蹤標籤" with checkboxes "錯誤", "功能", "支援". Button "建立". Annotations: red circle 1 on name, 2 on identifier field with a small red warning label, 3 on "公開" checkbox, 4 on modules section, 5 on trackers section, 6 on "建立".
```

### `03-02-add-members.png`｜新增專案成員

```
Show Redmine project "設定" page with tab "成員" active. A modal dialog titled "新增成員" overlays the page: a search field, a list of users and groups with checkboxes ("前端組", "王小明", "李大華" checked), and a "角色" section with checkboxes "管理者", "開發者" (checked), "回報者". Button "新增". Behind the modal, the member table with columns "使用者 / 群組", "角色". Annotations: red circle 1 on "設定" tab, 2 on "成員" sub-tab, 3 on user checkboxes, 4 on role checkboxes, 5 on "新增" button.
```

### `03-03-new-version.png`｜新增版本

```
Show Redmine "新增版本" form inside project settings. Fields: "名稱" with "v1.0", "概述", "狀態" dropdown showing options "開放中", "已鎖定", "已結束", "Wiki 頁面", "日期" with a date picker, "共用" dropdown "不共用". Button "建立". Annotations: red circle 1 on name, 2 on status dropdown (expanded showing the three options), 3 on date, 4 on sharing, 5 on "建立".
```

### `03-04-bulk-edit.png`｜批次編輯議題的右鍵選單

```
Show Redmine issue list with three rows checked and highlighted in light yellow. A right-click context menu is open beside them with items: "編輯", "狀態 ▸", "追蹤標籤 ▸", "優先權 ▸", "目標版本 ▸", "分派給 ▸" (hovered, showing a submenu with names "王小明", "李大華"), "完成百分比 ▸", "觀察", "複製", "刪除議題". Annotations: red circle 1 on the checked checkboxes, 2 on the context menu, 3 on the "分派給" submenu.
```

### `03-05-gantt.png`｜甘特圖

```
Show Redmine "甘特圖" tab. Top controls: month selectors "2026年10月", "顯示 3 個月", and "套用" link. Left column lists version "v1.0" and issues under it. Right side shows a timeline grid by weeks with horizontal bars; bars are partly filled to show progress, one bar is red indicating overdue, a diamond marker indicates the version due date, and a vertical dashed red line marks today. Bottom right has export links "PDF" and "PNG". Annotations: red circle 1 on date controls, 2 on a progress bar, 3 on the overdue red bar, 4 on the version diamond, 5 on export links.
```

### `03-06-roadmap.png`｜路線圖

```
Show Redmine "路線圖" tab. Two version sections: "v1.0" with due date text and a green progress bar at 65 percent with text "13 議題 (8 已結案 — 5 未結案)", followed by a short list of related issues; "v1.1" with a progress bar at 10 percent. Right sidebar with checkboxes "錯誤", "功能", "支援" and "顯示已結束的版本", and an "套用" button. Annotations: red circle 1 on a version title, 2 on the progress bar, 3 on the issue list, 4 on sidebar filters.
```

### `03-07-wiki.png`｜Wiki 編輯畫面

```
Show Redmine "Wiki" tab in edit mode. A formatting toolbar above a text area containing markup lines: "h1. 開發規範", "請參考 [[部署步驟]]", "相關議題：#128". Below the editor, tabs "編輯" and "預覽", a "留言" field, and buttons "儲存" and "預覽". Right sidebar with "Wiki" links "首頁", "依標題索引", "依日期索引". Annotations: red circle 1 on the toolbar, 2 on the "[[部署步驟]]" text, 3 on "#128", 4 on "儲存" button, 5 on the sidebar index links.
```

### `03-08-time-report.png`｜工時報表

```
Show Redmine "耗用工時" tab with sub-tab "報表" active. Controls: "日期" range filter, "詳細" dropdown set to "月", "新增" dropdown to add criteria showing "使用者" and "活動" as selected criteria. A table with rows of user names and activities, columns per month "2026-08", "2026-09", "2026-10", and a "總計" column. Bottom link "匯出 CSV". Annotations: red circle 1 on "報表" sub-tab, 2 on criteria selector, 3 on period dropdown, 4 on the totals column, 5 on "CSV" export link.
```

---

## 第 4 章 系統管理員操作

### `04-01-settings.png`｜系統設定

```
Show Redmine "管理" > "設定" page. A row of tabs: "一般", "顯示", "驗證", "API", "專案", "使用者", "議題追蹤", "耗用工時", "檔案", "電子郵件通知", "收件", "版本庫". The "驗證" tab is active, showing a checkbox "需要驗證" checked, a dropdown "註冊" set to "手動啟用帳戶", "密碼最小長度" field "8", and a "儲存" button. Left side admin menu lists "專案", "使用者", "群組", "角色與權限", "追蹤標籤", "議題狀態", "工作流程", "自訂欄位", "列舉值清單", "設定", "LDAP 驗證", "外掛", "資訊". Annotations: red circle 1 on "設定" in admin menu, 2 on the tabs row, 3 on "需要驗證", 4 on registration dropdown, 5 on "儲存".
```

### `04-02-users.png`｜使用者管理

```
Show Redmine "管理" > "使用者" list page. A "新增使用者" link at top right, a filter row with "狀態" dropdown "啟用中" and a search box. Table columns "登入帳號", "名字", "姓氏", "電子郵件", "系統管理員", "建立日期", "最後連線", and action links "鎖定" and "刪除" on each row. Annotations: red circle 1 on "新增使用者", 2 on the status filter, 3 on a "鎖定" link with a small red note label.
```

### `04-03-roles.png`｜角色權限設定

```
Show Redmine "角色與權限" edit page for role "開發者". Top fields: "名稱", "議題可見度" dropdown "所有非私人議題". Below, permission checkboxes grouped in boxes titled "專案", "議題追蹤", "工時追蹤", "Wiki", with items such as "檢視議題", "新增議題", "編輯議題", "新增筆記", "刪除議題", "記錄工時", "編輯 Wiki 頁面". "儲存" button. Annotations: red circle 1 on role name, 2 on issue visibility dropdown, 3 on the "議題追蹤" permission group, 4 on "儲存".
```

### `04-04-workflow.png`｜工作流程設定

```
Show Redmine "工作流程" edit page. Top selectors: "角色" dropdown "開發者", "追蹤標籤" dropdown "錯誤", button "編輯". Tabs "狀態轉換" (active) and "欄位權限". A matrix table: row header "目前狀態" listing "新建立", "進行中", "已解決", "回饋中", "已結案", "已拒絕"; column header "允許的新狀態" with the same statuses; some cells checked with checkboxes. Below, two collapsed sections "當使用者為作者時額外允許的轉換" and "當使用者為被分派者時額外允許的轉換". "儲存" button. Annotations: red circle 1 on role and tracker selectors, 2 on the matrix with an arrow from row "新建立" to column "進行中" checkbox, 3 on "欄位權限" tab, 4 on "儲存".
```

### `04-05-custom-fields.png`｜新增自訂欄位

```
Show Redmine "新增自訂欄位" form for type "議題". Fields: "格式" dropdown "清單", "名稱" with "影響範圍", "可能的值" text area with lines "前台", "後台", "資料庫", checkboxes "必填", "可用做篩選條件", "可搜尋". Right side boxes "追蹤標籤" with checkboxes "錯誤", "功能", "支援" and "專案" with checkbox "供所有專案使用". "建立" button. Annotations: red circle 1 on format, 2 on possible values, 3 on the required checkbox, 4 on tracker checkboxes, 5 on "建立".
```
