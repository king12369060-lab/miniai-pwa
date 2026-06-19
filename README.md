# MiniAI Local Final PDF

完全本機版，不連 OpenAI、不連 Gemini、不需要 API Key、不需要 Vercel 後端。此版本新增文字型 PDF 匯入。

## 最終版功能

- 手機底部導航列
- 分類首頁
- 本機知識庫
- 本機搜尋與簡單整理
- 任務管理
- 到期日、提醒時間、優先級
- 重複任務：每天、每週、每月
- 任務匯出 `.ics` 行事曆
- 常用模板：
  - 股票操作紀錄
  - 健康症狀紀錄
  - 旅遊行程
  - SOP
  - 待辦
  - 方劑 / 食療
  - 翡翠資料
  - 帳號安全檢查
- TXT / Markdown / JSON / 文字型 PDF 文件匯入
- 全部資料匯出 / 匯入備份
- PWA 安裝
- 離線快取

## 要上傳到 GitHub 的檔案

只需要這些：

```text
index.html
manifest.json
service-worker.js
icon-192.svg
icon-512.svg
README.md
```

不需要這些：

```text
api/
chat.js
package.json
.env.example
```

## GitHub Pages 部署

到 GitHub repo：

```text
Settings
→ Pages
→ Deploy from a branch
→ main
→ /root
→ Save
```

網址通常是：

```text
https://你的帳號.github.io/你的repo/
```

## 重要提醒

資料存在手機瀏覽器本機 IndexedDB。清除網站資料、換手機、重裝瀏覽器前，請先到設定匯出全部備份。

## 升級後看不到新版？

手機 PWA 可能有快取。請：

```text
移除桌面上的舊 MiniAI
→ Chrome 開 GitHub Pages 網址
→ 重新整理
→ 重新新增到主畫面
```

或清除該網站資料。


## PDF 匯入說明

此版本新增 PDF 匯入。

支援：

```text
文字型 PDF
```

不支援：

```text
掃描圖片 PDF
加密 PDF
需要 OCR 的 PDF
```

PDF 匯入會在瀏覽器本機抽取文字，再切段存入 IndexedDB 知識庫。

注意：PDF 解析器會從 CDN 載入 pdf.js 程式庫，但 PDF 檔案內容是在你的瀏覽器本機解析，不會送到 OpenAI、Gemini 或 Vercel 後端。
