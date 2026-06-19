# MiniAI PWA v2 架構

## 現在架構

```text
使用者
  ↓
MiniAI PWA 前端
  ↓
IndexedDB 本機知識庫
  ↓
本機相似度搜尋
  ↓
回答
```

## 優點

- 隱私高
- 不需要伺服器
- 不需要 API Key
- 可離線使用
- 可以安裝到手機桌面
- 適合做個人知識庫雛形

## 限制

這版不是大型語言模型，所以它不會真正推理或生成複雜內容。

它的回答來自：

1. 你教過它的知識
2. 預設知識
3. 本機相似度搜尋

## 為什麼不用前端直接接大模型 API？

因為前端程式碼會被使用者看到。

如果你把 API Key 寫進 `index.html`：

```text
任何人都可能看到你的 Key
```

比較安全的做法是：

```text
PWA → 後端代理 → 大模型 API
```

## v3 建議方向

### 方向 A：文件問答版

新增：

- 匯入 TXT
- 匯入 Markdown
- 自動切段
- 每段建立索引
- 問問題時找出相關段落

### 方向 B：大模型版

新增：

- 後端代理
- 使用者登入，可選
- API Key 放後端
- PWA 只送問題與相關知識片段

### 方向 C：Android APK 版

使用：

- Bubblewrap
- Capacitor
- 或 Trusted Web Activity

把 PWA 包成真正 APK。
