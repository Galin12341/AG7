v=# 設定指南

## 🔧 初始設定

### 1. 建立 Personal Access Token (PAT)

1. 點擊 GitHub 右上角頭像 → **Settings**
2. 左側選單最下方 → **Developer settings**
3. **Personal access tokens** → **Tokens (classic)**
4. **Generate new token (classic)**
5. 設定：
   - Note: `DevOps Lab Activity Token`
   - Expiration: `90 days`（或更長）
   - 勾選權限：`repo`（完整權限）
6. 點擊 **Generate token**
7. **立即複製 token**（離開頁面後無法再次查看）

### 2. 設定 Repository Secret

1. 到你的儲存庫
2. **Settings** → **Secrets and variables** → **Actions**
3. 點擊 **New repository secret**
4. Name: `TOKEN`
5. Secret: [貼上剛才複製的 PAT]
6. 點擊 **Add secret**

### 3. 啟用 GitHub Pages

1. **Settings** → **Pages**
2. Source:
   - Branch: `main`
   - Folder: `/root`
3. 點擊 **Save**
4. 等待 1-2 分鐘
5. 重新整理頁面，會看到網站網址

### 4. 手動觸發 Workflow

1. 到 **Actions** 標籤
2. 選擇 **Update Activity Log**
3. 點擊 **Run workflow** → **Run workflow**
4. 等待執行完成（約 30 秒）

## ✅ 驗證清單

- [ ] PAT 已建立並儲存
- [ ] Repository Secret 已設定
- [ ] GitHub Pages 已啟用
- [ ] Workflow 執行成功
- [ ] README.md 已更新活動日誌
- [ ] 網站可正常訪問

## 🐛 故障排除

### Workflow 執行失敗

**可能原因 1**: Token 權限不足
- **解決**: 確認 PAT 有 `repo` 完整權限

**可能原因 2**: Secret 名稱錯誤
- **解決**: 確認 secret 名稱為 `TOKEN`（大寫）

**可能原因 3**: Repository 權限問題
- **解決**: Settings → Actions → General → Workflow permissions → 選擇 "Read and write permissions"

### 活動日誌未顯示

**可能原因**: Workflow 尚未執行
- **解決**: 手動觸發一次 workflow

### 網站 404 錯誤

**可能原因**: Pages 設定錯誤
- **解決**: 確認 Source 設定為 `main` 分支和 `/root` 資料夾

## 📞 需要協助？

查看 [GitHub Actions logs](../../actions) 了解詳細錯誤訊息。