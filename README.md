# 台股投資助理

單一 HTML 檔案的台股投資分析 Web App，可在手機瀏覽器直接開啟，支援加入桌面主畫面像 App 一樣使用。

## 功能

- **首頁**：加權指數即時報價、短期波段推薦（3支）、長期存股推薦（3支）
- **搜尋**：輸入股票代碼或中文名稱搜尋，即時顯示股價漲跌
- **自選股**：新增/刪除自選股，自動載入即時股價
- **個股詳情**：K線圖（1個月～5年）、MA/RSI/MACD 技術指標、AI 分析、存股試算、相關新聞
- **設定**：推薦模式切換（技術面/存股優先）、手動重整、清除自選股

## 使用說明

直接以瀏覽器開啟 `index.html` 即可。如遇 CORS 限制，程式會自動透過 proxy 抓取資料。

---

## 部署到 GitHub Pages

### 步驟一：建立 Repository

1. 前往 [github.com](https://github.com) 登入
2. 點右上角 **+** → **New repository**
3. Repository name 填入：`stock-assistant`
4. 設定為 **Public**
5. 按 **Create repository**

### 步驟二：上傳 index.html

**方法 A：網頁拖曳（最簡單）**
1. 進入剛建立的 repository 頁面
2. 點 **Add file** → **Upload files**
3. 將 `index.html` 拖曳進去
4. 填寫 commit message，按 **Commit changes**

**方法 B：Git 指令**
```bash
cd D:/AI/stock-assistant
git init
git add index.html
git commit -m "初始版本：台股投資助理"
git branch -M main
git remote add origin https://github.com/你的帳號/stock-assistant.git
git push -u origin main
```

### 步驟三：開啟 GitHub Pages

1. 進入 repository → 上方 **Settings**
2. 左側選單找 **Pages**
3. Source 選 **Deploy from a branch**
4. Branch 選 **main**，資料夾選 **/ (root)**
5. 按 **Save**
6. 等約 1～2 分鐘，頁面顯示：
   ```
   Your site is live at https://你的帳號.github.io/stock-assistant/
   ```

### 步驟四：手機加入主畫面

**iOS（Safari）**
1. 用 Safari 開啟網址
2. 點下方工具列的 **分享** 按鈕（方形加箭頭）
3. 滑動選單，找到 **加入主畫面**
4. 名稱改為「台股助理」，按 **新增**

**Android（Chrome）**
1. 用 Chrome 開啟網址
2. 點右上角 **⋮** → **新增至主畫面**
3. 確認名稱，按 **新增**

---

## 技術規格

| 項目 | 說明 |
|------|------|
| 形式 | 單一 HTML 檔案（HTML + CSS + JS 整合） |
| 圖表 | TradingView Lightweight Charts 4.x（CDN） |
| 股票資料 | Yahoo Finance 非官方 API（`query1.finance.yahoo.com`） |
| CORS 處理 | 先嘗試直連，失敗自動 fallback 至 allorigins.win proxy |
| 財經新聞 | RSS2JSON API + 鉅亨網台股 RSS |
| 本地儲存 | localStorage（自選股、設定、首次提示） |
| 色彩慣例 | 台灣：**紅色 = 上漲**，**綠色 = 下跌** |

## 免責聲明

本程式所有股票推薦、技術指標分析及 AI 分析內容，均為基於公開資料之自動化運算結果，**不構成任何形式之投資建議**。股票市場具有高度風險，過去表現不代表未來結果。投資人應自行評估風險，獨立做出投資決策。
