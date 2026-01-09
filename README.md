# TEST 靜態資產部署說明

這個專案使用 Cloudflare Workers 搭配 Wrangler 發佈靜態資產，預設會將 `dist/` 目錄下的檔案提供給使用者，範例頁面位於 `dist/index.html`。

## 環境需求
- Node.js（用於安裝 Wrangler）
- Cloudflare 帳號與 API 權限
- Wrangler CLI（`npm i -g wrangler` 或使用 `npx wrangler`）

## 本機預覽
在專案根目錄執行：

```bash
npx wrangler dev
```

這會啟動本機開發伺服器，並從 `dist/` 提供靜態檔案。

## 部署
確認已登入 Cloudflare 後執行：

```bash
npx wrangler deploy
```

Wrangler 會讀取 `wrangler.toml` 設定，將 `dist/` 內的檔案部署到 Cloudflare。

## 專案結構
- `dist/`：靜態資產目錄（目前包含一個占位頁面 `index.html`）。
- `wrangler.toml` / `wrangler.jsonc`：Cloudflare Workers 設定，指定專案名稱與資產目錄。

> Wrangler 會優先讀取 `wrangler.toml`；`wrangler.jsonc` 內容相同，供偏好 JSON 格式時參考。
