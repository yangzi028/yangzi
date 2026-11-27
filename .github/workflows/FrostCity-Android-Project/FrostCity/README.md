# 極寒新城 Android 專案

遊戲本體是 `app/src/main/assets/index.html`，由 WebView 載入，存檔放在應用內的 localStorage，離線可玩。
套件名 `com.frostcity.game`，最低 Android 8.0（API 26）。

## 方法一：Android Studio（本機）
1. 安裝 Android Studio，選 File → Open，打開本資料夾。
2. 等 Gradle 同步完成（首次需要連網下載）。
3. 選單 Build → Build Bundle(s) / APK(s) → Build APK(s)。
4. 產物在 `app/build/outputs/apk/debug/app-debug.apk`，傳到手機安裝（需允許安裝未知來源應用）。

## 方法二：GitHub Actions（不用裝任何東西）
1. 在 GitHub 新建倉庫，把本資料夾全部內容推上去（分支用 main）。
2. 打開倉庫的 Actions → Build APK → Run workflow，等待約 3 到 5 分鐘。
3. 在該次執行頁面底部的 Artifacts 下載 `FrostCity-debug-apk`，解壓得到 `app-debug.apk`。

## 備註
- 產出的是 debug 簽名 APK，可直接安裝，但不能上架應用商店。上架需自行建立簽名金鑰並用 `assembleRelease` 打包。
- 想更新遊戲內容，只需替換 `app/src/main/assets/index.html` 後重新打包。
