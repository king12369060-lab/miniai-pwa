# MiniAI Local v8

完全本機版，不接 OpenAI，不接 Gemini，不需要 API Key，也不需要後端函式。

## 保留功能

- PWA 安裝
- 離線快取
- 本機知識庫 IndexedDB
- TXT / Markdown / JSON 匯入
- 本機搜尋
- 新增問答知識
- 任務管理
- 任務提醒時間
- 本機通知
- 任務匯出 `.ics`
- 聊天紀錄
- 匯出 / 匯入備份

## 移除功能

- OpenAI 連線
- Gemini 連線
- `/api/chat.js`
- `package.json`
- Vercel 後端
- API Key 設定

## 部署

這版可以用 GitHub Pages 部署即可，不需要 Vercel。

GitHub Pages：

```text
Settings
→ Pages
→ Deploy from branch
→ main / root
```

## 升級方式

把本資料夾裡的檔案上傳到 GitHub repo 最外層：

```text
index.html
manifest.json
service-worker.js
icon-192.svg
icon-512.svg
README.md
```

如果 repo 裡還有舊的：

```text
api/
package.json
.env.example
```

可以刪掉，因為本機版不用。

## 注意

這版不是大型模型，所以回答能力是本機搜尋與簡單整理，不會像 ChatGPT 或 Gemini 一樣深度推理。

但優點是：

- 不花 API 費
- 不需要 API Key
- 不會自動把資料送到模型
- 比較簡單穩定


## v8.1 手機螢幕適配修正

- 工具列按鈕改成自動換行 / 手機雙欄
- 快捷按鈕改成自動換行 / 手機雙欄
- 移除主要區塊的左右滑動
- 長文字、網址、錯誤訊息會自動斷行
- 對話框限制在螢幕寬度內
- 手機輸入框與送出按鈕改為上下排列
