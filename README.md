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
- 骰子是真正的 3D 立方體（CSS `preserve-3d`，六個面都實際存在、對面相加為 7），不是換貼圖
  - 姿態以四元數保存，翻滾由位移驅動：橫越一個骰子寬 = 轉四分之一圈
  - **點數不是先決定再把動作拗過去**：骰子自由翻滾，減速時倒向當下最接近的穩定姿態
    （立方體有 24 種），停止後把朝向鏡頭的面讀出來，那才是結果
  - 因此結果的公平性是物理的性質而非保證，需實測：2640 次擲骰 chi-square 2.09
    （5 df，11.07 為 5% 門檻，各點數 16.3%〜17.5%），與公平骰子一致
- 在桌面上滑動擲骰，滑越用力滾越久；或按「擲」
- 長按骰子可以「保留」，下一輪不會被擲出
- 手機按「搖一搖」開啟後，搖手機就會擲骰（iOS 需授權動作感測）
- 音效：擲出的碰撞聲、落桌與骰子互撞的聲音，用 Web Audio 即時合成，沒有外部音檔；右上角 ♪ 可開關，設定會記住
  - iOS 在響鈴關閉（實體靜音開關）時會把 Web Audio 靜音，所以頁面同時循環播放一段無聲音檔，把音訊 session 維持在可發聲的狀態
  - 音訊必須在使用者手勢的同步執行期間建立，任何延後（`setTimeout`、物理回呼）在 Safari 都會失效
- 骰子數與最近 20 筆結果會存在 localStorage

### 部署

推到 `master` 後，`.github/workflows/pages.yml` 會自動部署到 GitHub Pages。
Pages 的來源是 `gh-pages` 分支。推到 `master` 後，`.github/workflows/pages.yml` 會把該 commit
鏡像到 `gh-pages`，GitHub 接著自動重建網站，不需要手動操作。

（`gh-pages` 是自動產生的部署分支，直接改它沒有意義，下次部署就會被覆蓋——請改 `master`。）

網址：https://hongahung.github.io/test/

本機預覽：`python3 -m http.server` 然後開 http://localhost:8000
