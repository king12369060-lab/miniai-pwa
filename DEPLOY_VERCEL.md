# MiniAI v7 部署到 Vercel

## 1. 上傳到 GitHub

把 v7 解壓縮後的所有檔案上傳到 GitHub repository。

至少包含：

```text
index.html
manifest.json
service-worker.js
icon-192.svg
icon-512.svg
api/chat.js
package.json
```

## 2. Vercel 匯入 GitHub repo

```text
Vercel
→ Add New Project
→ Import Git Repository
→ Deploy
```

## 3. 設定環境變數

在 Vercel Project Settings → Environment Variables 新增：

```text
OPENAI_API_KEY = 你的 OpenAI API Key
OPENAI_MODEL = gpt-5.4-mini
```

## 4. Redeploy

設定環境變數後重新部署。

## 5. 手機安裝

用 Android Chrome 開 Vercel 網址：

```text
右上角三點
→ 新增到主畫面
→ 安裝
```
