# 午茶時光 — 辦公室飲料訂購系統

辦公室團購飲料的輕量訂單管理工具，支援即時新增、修改、刪除訂單，並提供統計與匯出功能。

## 功能

- 瀏覽飲料菜單（分類、品項、價格）
- 新增訂單，可選擇糖度、冰塊、數量
- 修改 / 刪除既有訂單
- 依姓名搜尋訂單
- 即時統計：人數、杯數、總金額、人氣排行
- 匯出 CSV（Excel 可讀）
- 複製 LINE / Slack 格式摘要

## 技術架構

| 項目 | 說明 |
|------|------|
| 前端 | React 18（CDN）、Tailwind CSS（CDN）、Babel Standalone |
| 後端 | Google Sheets + Apps Script Webhook |
| 建置工具 | Vite |

## 本地開發

```bash
npm install
npm run dev
```

開啟瀏覽器，前往 `http://localhost:3000`。

## 部署到 GitHub Pages

### 一次性設定（只需做一次）

1. 前往 GitHub 倉庫的 **Settings > Pages**
2. 在 **Source** 選擇 **GitHub Actions**
3. 儲存設定

### 自動部署

之後每次推送到 `main` 分支，GitHub Actions 會自動執行 build 並部署。

部署完成後，應用程式將發布於：
```
https://isaactwtv.github.io/20260528_DrinkOrder/
```

## 後端設定

訂單資料透過 Google Apps Script Webhook 存取 Google Sheets。  
若需替換為自己的試算表，請修改 `index.html` 中的 `APPS_SCRIPT_URL` 常數，指向你自己發布的 Apps Script 網址。
