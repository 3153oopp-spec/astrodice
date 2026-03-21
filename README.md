# 🎲 AstroDice｜占星骰互動工具

> 為占星師與學習者設計的線上占星骰子工具，模擬投擲三顆骰子（行星 × 星座 × 宮位），即時產生星盤圖示與占星關鍵字解析。

🔗 **[Live Demo — 立即體驗](https://eclipsia-astrology.com/astrodice/)**

---

## ✨ 主要功能

- 🎲 **動態擲骰**：流暢動畫 + `crypto.getRandomValues()` 確保公正隨機
- 🪐 **即時星盤繪製**：根據結果動態渲染 SVG 星盤示意圖
- 📖 **深度關鍵字解析**：標記元素（火土風水）與宮位性質（角/續/果宮）
- 📋 **歷史紀錄**：自動儲存最近 10 次擲骰（localStorage）
- 📤 **彈性分享**：支援 Web Share API 與 Clipboard API 雙重回退機制

---

## 🛠️ 技術架構

| 項目 | 說明 |
|------|------|
| 核心技術 | Vanilla HTML5 / CSS3 / ES6+ JavaScript（零框架依賴） |
| 繪圖引擎 | 原生 JavaScript 操作 SVG DOM，動態計算角度與渲染 |
| 設計系統 | CSS Variables 構建品牌色彩與字體系統 |
| 字體 | Google Fonts + 自定義占星符號字型 AstroSymbol |
| 部署環境 | WordPress iframe 嵌入，針對嵌入式環境優化 |

---

## 🧠 開發背景

身為執業占星師（NCGR PAA Level I 認證），發現市面缺乏符合執業邏輯、中文化的占星骰子工具。因此以 Antigravity 完成從需求定義、功能設計到部署上線的完整流程。

---

*Designed & built for [蝕光占星 Eclipsia Astrology](https://eclipsia-astrology.com/)*
