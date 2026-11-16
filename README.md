# ClassRunner｜課域行者

Windows 共用教室的個人帳號準備與下課登出工具。第三方帳號、密碼與必要登入憑證以密文保存在本機；每次明確開始登入服務時，再透過驗證器六位數碼取得本輪解鎖授權。

**目前是開發預覽階段，尚未發布正式版本。** 真實帳號的首次登入、憑證重用與下課登出仍需逐項驗收，請勿直接當作正式教室部署版本。

## Windows 下載

請到 [官方 Releases](https://github.com/DrizzlingNight/ClassRunner/releases) 查看實際已發布版本。預覽版會標示 Pre-release；沒有 Release 時代表尚未提供公開成品。

正式版成功發布後，Windows x64 Portable 的固定入口為：

[下載最新正式 Portable 版本](https://github.com/DrizzlingNight/ClassRunner/releases/latest/download/ClassRunner-Windows-x64.zip)

**首次正式版發布前，上面的固定入口尚未啟用。** 本專案目前沒有提供 Setup 安裝程式。

## 首次使用

1. 下載 ZIP 及同一版本的 `SHA256SUMS.txt`，核對 SHA-256 後解壓縮到可寫入的資料夾。
2. 執行 `ClassRunner.exe`，不需要管理員權限或另外安裝 .NET Runtime。
3. 使用管理員提供的邀請碼建立個人設定，設定主密碼及手機驗證器。
4. 加入需要的服務。首次由本人在官方畫面登入並確認身分，允許後才保存必要憑證的本機密文。
5. 每次按登入仍須新的六位數碼；下課先儲存工作，再使用「一鍵登出服務」，查看每項結果。

註冊時可選擇建立桌面明文的程式帳號備忘檔；請移存到自己的可信任裝置並自行刪除。不要留在共用電腦。

## 服務與系統需求

- Windows x64、可用網路及教室管理員已設定的 API；Portable 內含 .NET 桌面執行期。
- Chrome、Edge、LINE、Claude、VS Code 及其擴充功能須另外安裝，Portable 不包含這些第三方軟體。
- 登入候選涵蓋 Chrome／Edge 本身帳號、GitHub 網站、LINE、Claude Desktop／Code、VS Code 帳號及 Copilot／Claude Code／Codex 擴充功能。候選入口及合成測試不代表所有原廠版本都已真人驗收。
- Chrome／Edge 本身帳號目前限一般 Default Profile；原廠遠端連線與帳號確認必須本人允許。瀏覽器及第三方認證格式改版可能要求重新登入。
- Claude Desktop 的官方 Windows 安裝位置限制尚待解決；未完成可用性驗收。Copilot 等服務的帳號、訂閱及權限由原廠決定。

## 更新

程式在背景查詢本公開庫的最新正式 GitHub Release，有新版時顯示提示，也可從「關於／更新」手動檢查。一般使用者不需要 GitHub 帳號或 Token。

目前採官方下載入口，**不自動安裝或執行下載檔案**。先完成下課登出並關閉 ClassRunner，再將新版解壓縮到新的空資料夾。個人設定及加密憑證保留在 Windows 本機使用者資料位置，請不要刪除該資料位置。

## 安全與使用限制

本機加密保存的第三方帳密與憑證不會上傳到教室 API。共用電腦仍需由管理員維護；程式不能防止裝置上的惡意程式，也不提供百分之百安全保證。

SHA-256 用來核對下載內容，不能單獨證明發布者身分。目前成品尚未有程式碼簽章；只從本官方 Release 下載。程式不繞過 MFA、CAPTCHA、裝置綁定或原廠拒絕。關閉視窗不等於登出，請查看下課清理的逐項結果；本機登出不代表所有第三方遠端 Session 已撤銷。

[版本更新紀錄](CHANGELOG.md)
