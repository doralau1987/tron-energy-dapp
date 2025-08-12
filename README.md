# TRON Energy Rental dApp

這是一個用於繞過 TronLink 2023年深層鏈接限制的 Web dApp。

## 🚀 快速部署到 GitHub Pages

### 步驟 1: 創建 GitHub 儲存庫

1. 登錄 [GitHub](https://github.com)
2. 點擊右上角的 `+` 按鈕，選擇 "New repository"
3. 儲存庫名稱設置為：`tron-energy-dapp`
4. 設置為 Public（GitHub Pages 免費版需要公開儲存庫）
5. 勾選 "Add a README file"
6. 點擊 "Create repository"

### 步驟 2: 上傳文件

1. 在新創建的儲存庫中，點擊 "uploading an existing file"
2. 將 `index.html` 文件拖拽到上傳區域
3. 在 "Commit changes" 部分填寫：
   - Commit message: `Add TRON Energy Rental dApp`
   - Description: `Initial dApp deployment for bypassing TronLink deeplink restrictions`
4. 點擊 "Commit changes"

### 步驟 3: 啟用 GitHub Pages

1. 在儲存庫頁面，點擊 "Settings" 標籤
2. 在左側菜單中找到 "Pages"
3. 在 "Source" 部分選擇 "Deploy from a branch"
4. Branch 選擇 "main"，文件夾選擇 "/ (root)"
5. 點擊 "Save"
6. 等待幾分鐘，您的 dApp 將可在以下地址訪問：
   ```
   https://yourusername.github.io/tron-energy-dapp
   ```

### 步驟 4: 更新機器人配置

1. 打開 `bot/web_dapp_connector.py` 文件
2. 找到第 36 行，將 `yourusername` 替換為您的 GitHub 用戶名：
   ```python
   self.dapp_base_url = "https://yourusername.github.io/tron-energy-dapp"
   ```

## 📱 使用方法

### TronLink 移動端（推薦）
1. 打開 TronLink 應用
2. 點擊右上角瀏覽器圖標 🌐
3. 複製並粘貼 dApp 鏈接
4. 確認交易並簽署

### TronLink 桌面端
1. 安裝 TronLink 瀏覽器擴展
2. 直接訪問 dApp 鏈接
3. 確認錢包連接
4. 確認交易並簽署

### 其他錢包
- **Trust Wallet**: 更好的深層鏈接支援
- **TokenPocket**: TRON 生態專用
- **Klever Wallet**: 移動端友好

## 🔧 自定義配置

如果您想使用自己的域名：

1. 購買域名並設置 CNAME 指向 `yourusername.github.io`
2. 在 GitHub 儲存庫的 Settings > Pages 中設置 Custom domain
3. 更新 `bot/web_dapp_connector.py` 中的 `dapp_base_url`

## 🛠️ 技術說明

### 為什麼需要 Web dApp？

2023年8月後，TronLink 限制了第三方應用的深層鏈接功能，導致直接使用 `tronlink://` 協議會出現"external request error"。

### 解決方案

通過託管 Web dApp，使用 TronWeb 庫直接與注入的 TronLink provider 交互，繞過深層鏈接限制。

### 支持的功能

- ✅ 合約函數調用
- ✅ 參數傳遞
- ✅ 交易簽署
- ✅ 回調處理
- ✅ 錯誤處理

## 🔍 故障排除

### 常見問題

1. **頁面無法訪問**
   - 確保 GitHub Pages 已正確啟用
   - 等待 5-10 分鐘讓 DNS 生效

2. **錢包無法連接**
   - 確保在 TronLink 內置瀏覽器中打開
   - 檢查錢包是否已解鎖

3. **交易失敗**
   - 確保錢包有足夠的 TRX 支付手續費
   - 確認合約地址和參數正確

### 測試建議

1. 首先在測試網（Nile）上測試
2. 確認所有功能正常後再切換到主網
3. 小額測試確認無誤後進行正式使用

## 📞 支持

如遇問題，請檢查：
1. 瀏覽器控制台錯誤信息
2. TronLink 錢包狀態
3. 網絡連接狀況 