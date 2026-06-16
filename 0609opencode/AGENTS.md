# AGENTS.md — 高雄地標之旅

## 專案性質

純靜態網站（HTML + CSS），無建置工具、無套件管理、無測試框架。直接在瀏覽器開啟 `.html` 即可瀏覽。

## 檔案結構

| 檔案 | 用途 |
|---|---|
| `index.html` | 首頁，三景點卡片 + 連結 |
| `weiwuying.html` | 衛武營（歷史/地理/建築/人文/交通/美食） |
| `lotus-pond.html` | 蓮池潭（同上結構） |
| `85-tower.html` | 85大樓（同上結構） |
| `css/style.css` | 所有樣式，無框架 |
| `images/` | 圖片目錄（`.png` 檔需手動放入） |

## 重要約定

- **圖片**：頁面引用 `images/衛武營.png`、`images/蓮池潭.png`、`images/85大樓.png`、`images/kaohsiung-hero.jpg`，這些檔案不一定存在。Agent 無法讀取圖片輸入，需告知使用者自行放入。
- **導航**：所有頁面頂部導覽列使用相對連結，新增頁面時必須加入導覽。
- **內容結構**：每個景點頁面固定依序為「概覽 → 歷史 → 地理/建築 → 人文 → 交通 → 美食」六區塊。
- **交替佈局**：`.content-block` 預設圖左文右；加上 `.reverse` 類別會用 `direction: rtl` 切換為圖右文左（非典型作法，編輯時勿拆除此類別）。
- **語言**：全部繁體中文（zh-TW），無 i18n。
- **無開發伺服器**：不需 `npm install`、`npm run dev`，直接以 `file://` 開啟。

## 編輯守則

- 新增景點頁面時，複製既有頁面的 HTML 結構並按六區塊撰寫。
- 圖片使用 `style="background-image: url('images/xxx.png'); background-color: #..."` 內聯樣式，`background-color` 作為載入前的佔位色。
- 響應式斷點在 `768px`（見 CSS 結尾 `@media`）。
