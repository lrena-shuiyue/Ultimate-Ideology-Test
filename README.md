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
