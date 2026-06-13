# Ultimate Ideology Test

這個小站提供一個 8 維度、40 題的思想偏好測驗（終極思想流派測試），會輸出一組代號並以雷達圖視覺化你的傾向。

快速上手

- 本地預覽：

```bash
cd /workspaces/Ultimate-Ideology-Test
python3 -m http.server 8000
# 在瀏覽器打開 http://localhost:8000/index.html
```

- 部署到 GitHub Pages（推薦）：
	1. 將專案推到 GitHub（已包含 `index.html` 與 `favicon.svg`）。
	2. 將 `main` 分支推到 `gh-pages`（或直接使用 `main` 作為 Pages 分支）：

```bash
git push origin main:gh-pages
```

	3. 在 GitHub repository 的 Settings → Pages 檢查來源(branch) 與狀態，網站應該會顯示於 `https://<你的帳號>.github.io/<repo>/`。

自訂網域（CNAME）說明

- 若要使用自訂網域（例如 `ultimateideologytest.example`），請先在你的 DNS 管理頁面新增 A 紀錄到 GitHub Pages 的 IP，或使用 CNAME 指向 `<你的帳號>.github.io`：

	- A 紀錄（頂級域名）：
		- 185.199.108.153
		- 185.199.109.153
		- 185.199.110.153
		- 185.199.111.153

	- 或在子域（如 `www`）使用 CNAME 指向： `lrena-shuiyue.github.io`。

- 在 repo 根目錄新增 `CNAME` 檔案，內容為你的自訂網域（例如 `ultimateideologytest.example`），然後重新推送，GitHub Pages 會自動綁定（需 DNS 生效）。

我可以代你處理的事：
- 把 `CNAME` 檔案加入 repo（請提供欲綁定的網域）。
- 幫你微調樣式、提供不同尺寸的 favicon 或加入社群分享預覽圖（Open Graph image）。

目前部署網址： https://lrena-shuiyue.github.io/Ultimate-Ideology-Test/

安全性（CSP）提醒

- 如果你在托管或第三方檢測看到類似「Content Security Policy blocks 'eval'」的錯誤，這代表伺服器對 `script-src` 設定了更嚴格的限制，阻止了像 `eval()`、`new Function()` 或某些第三方套件在執行時建立函式的行為。解決選項：
  1. 最安全：更新應用程式以避免使用 `eval` / `new Function` / 字串型的 `setTimeout`（本專案程式碼未直接使用這些 API）。
  2. 若必須使用第三方函式庫（例如某些舊版視覺化套件），可在伺服器的 CSP `script-src` 中加入 `unsafe-eval`（風險較高，可能允許惡意內聯腳本執行）。
  3. 替代方式：改用不依賴 `eval` 的套件或自行打包相依（把 library 複製到 repo，避免外部執行時動態評估）。

我可以幫你：
- 檢查是否是 Chart.js 或其他外部庫導致的 CSP 警告，並協助改用不需 `unsafe-eval` 的版本或把相關庫內嵌到專案中。

