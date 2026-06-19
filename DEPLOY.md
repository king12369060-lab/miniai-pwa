# MiniAI PWA v2 部署說明

## 結論

要讓手機完整支援「安裝到桌面」和「離線快取」，請把這個資料夾放到 HTTPS 網站。

最省事的方式是：

1. Cloudflare Pages
2. Netlify
3. Vercel
4. GitHub Pages

## 手機直接開檔案可以嗎？

可以測試基本功能，但通常不能完整啟用 PWA。

原因是瀏覽器通常要求 PWA 的 Service Worker 必須在安全來源下運作：

```text
HTTPS 網址
```

或本機開發環境：

```text
localhost
```

手機檔案路徑通常不是安全來源，所以不一定能安裝。

## 建議部署方式：Cloudflare Pages

步驟概念：

1. 建立一個 GitHub repo
2. 把這些檔案上傳到 repo
3. 到 Cloudflare Pages 選擇該 repo
4. 建置設定留空或使用靜態網站預設
5. 部署完成後，用手機開啟網址
6. 點瀏覽器選單，選「新增到主畫面」

## GitHub Pages

步驟概念：

1. 建立 repo
2. 上傳這些檔案
3. 到 repo 的 Settings
4. 找 Pages
5. Source 選 main branch
6. 儲存後等待網址產生
7. 用手機開啟網址並新增到主畫面

## 本機電腦測試方式

如果你有 Python，可以在資料夾裡執行：

```bash
python -m http.server 8000
```

然後用瀏覽器開：

```text
http://localhost:8000
```

這可以測試 Service Worker 與基本 PWA 行為。

## 重要安全提醒

不要把大模型 API Key 直接寫在 `index.html` 裡。

如果未來要接大模型，正確做法是：

```text
PWA 前端 → 你的後端代理 → 大模型服務
```

這樣 API Key 才不會暴露在手機瀏覽器裡。
