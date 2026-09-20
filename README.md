hello honga

update 1
update git hub
update git lab

update merge
<<<<<<< HEAD
update 2 git lab
update 2 git hub

update merge by test 2

update 2 git hub
update 2 git lab

update merge by test 1

## 擲骰子 (index.html)

純前端的擲骰子網頁，單一檔案、不需要任何建置工具。

- 1〜6 顆骰子，右上角 +／− 調整
- 在桌面上滑動擲骰，滑越用力滾越久；或按「擲」
- 長按骰子可以「保留」，下一輪不會被擲出
- 手機按「搖一搖」開啟後，搖手機就會擲骰（iOS 需授權動作感測）
- 骰子數與最近 20 筆結果會存在 localStorage

### 部署

推到 `master` 後，`.github/workflows/pages.yml` 會自動部署到 GitHub Pages。
workflow 內的 `enablement: true` 會在第一次執行時自動啟用 Pages 並設定為 GitHub Actions 來源，
不需要先到設定頁手動開啟。

網址：https://hongahung.github.io/test/

本機預覽：`python3 -m http.server` 然後開 http://localhost:8000
