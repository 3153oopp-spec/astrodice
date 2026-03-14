# Eclipsia Astrology 視覺風格與設計系統指引 (AI Prompt Guideline)

這是一份設計系統與視覺風格的約定指引。當你在新的網頁應用程式或專案中生成代碼時，請**嚴格遵守**以下的 CSS 變數設計、字體排版規則以及 UI 元件風格，以確保所有專案維持「Eclipsia Astrology（蝕光占星）」一致的品牌體驗。

## 1. 核心設計理念 (Design Philosophy)
- **極簡、現代、乾淨**：以大量的留白（Whitespace）和淡雅的灰色調背景來突顯內容。
- **神祕與質感的揉合**：使用無襯線字體（Plus Jakarta Sans）作為現代感的主體，搭配襯線字體（Crimson Text）來強調標題的神祕學與儀式感。
- **品牌藍色點綴**：以 `Eclipsia Blue (#0071b7)` 作為唯一的強烈引導色，其餘色彩保持克制與低調。

---

## 2. CSS 變數 (CSS Variables)

請在你的 CSS 檔案中的 `:root` 層級直接套用以下變數，並在各個 class 中調用它們：

```css
:root {
  /* ================= 背景色彩 (Backgrounds) ================= */
  --bg-primary: #ffffff;         /* 主要整體頁面背景 */
  --bg-section: #f7f8fa;         /* 區塊背景、底色區域 (如骰子面、結果摘要) */
  --bg-card: #ffffff;            /* 卡片內部背景 */

  /* ================= 文字色彩 (Typography Colors) ================= */
  --text-heading: #2c2c2c;       /* 標題文字 (H1~H6, 亮點數據) */
  --text-body: #4b4b4b;          /* 內文文字 (段落) */
  --text-secondary: #6e7a8a;     /* 次要資訊說明、標籤 */
  --text-muted: #9ca8b7;         /* 提示文字、Placeholder、較弱的附註 */

  /* ================= 品牌與強調色 (Accent Colors) ================= */
  --accent-blue: #0071b7;        /* 品牌主色 (Eclipsia Blue) - 用於主要按鈕、重點高亮 */
  --accent-blue-hover: #005a93;  /* 品牌主色 (Hover 狀態) */
  --accent-blue-light: rgba(0, 113, 183, 0.08); /* 品牌主色 (極淺，用於次要背景或 Hover 底色) */

  /* ================= 占星專屬色系 (Astrology Specific) ================= */
  --planet-color: #2c2c2c;       /* 行星強調色 */
  --sign-color: #0071b7;         /* 星座強調色 */
  --house-color: #b08d3e;        /* 宮位強調色 */
  --highlight-sign: rgba(0, 113, 183, 0.12);    /* 星座背景高亮 */
  --highlight-house: rgba(186, 155, 93, 0.15);  /* 宮位背景高亮 */

  /* ================= 邊框與陰影 (Borders & Shadows) ================= */
  --border-color: #e5e8ed;       /* 一般元件邊框、卡片邊框 */
  --border-light: #eef0f4;       /* 更細微的分割線 */
  
  --radius: 12px;                /* 大部分卡片與容器的圓角 */
  --radius-sm: 8px;              /* 小型元件 (如標籤、列表項目) 的圓角 */
  
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.06);   /* 卡片基礎層次陰影 */
  --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.08);  /* 懸浮或強調時的陰影層次 */

  /* ================= 字體設定 (Fonts) ================= */
  --font-heading: 'Crimson Text', Georgia, serif; 
  --font-body: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif;
}
```

---

## 3. 字體排版 (Typography Rules)

- **標題 (Headings)**：一律使用 `--font-heading`。對於大標題（如 H1），設定 `font-weight: 700`，字距 `letter-spacing: 0.02em`，行高 `line-height: 1.3`。
- **內文 (Body)**：使用 `--font-body`。預設字級以 `16px` (1rem) 為主，行高須維持在 `1.7` 以確保良好的可讀性。
- **標籤 / 次要文字 (Labels / Secondary)**：字體縮小至 `0.8rem` ~ `0.9rem`，使用 `--text-secondary`，並可適度加粗 (如 `font-weight: 600`) 以及設定稍寬的字母間距 (`letter-spacing: 0.06em`)。

*(必須在 `<head>` 中引入 Google Fonts)*
```html
<link href="https://fonts.googleapis.com/css2?family=Crimson+Text:ital,wght@0,400;0,600;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

---

## 4. UI 元件風格實作規範 (Component Guidelines)

### A. 卡片 (Cards)
- **基礎樣式**：背景設為 `--bg-card`，邊框為 `1px solid var(--border-color)`，並帶有 `--shadow-sm` 及預設圓角 `--radius` (12px)。
- **互動提示 (Hover / Active)**：當卡片具有互動性（例如點擊選取）時，將邊框顏色切換為 `--accent-blue`，並加入外發光陰影（例：`box-shadow: 0 0 0 3px rgba(0, 113, 183, 0.1)` 或者是 `0 0 0 3px rgba(0, 113, 183, 0.06)` 作為輕量提示）。

### B. 主按鈕 (Primary Button/Pill Hover Style)
- **形狀**：使用藥丸形狀（Pill style），設定 `border-radius: 50px`。
- **色彩**：背景為 `--accent-blue`，文字為 `#ffffff`。不可以有邊框。
- **字體**：使用 `--font-body`，粗細為 `600`。
- **Hover 動畫**：滑鼠懸浮時，背景變為 `--accent-blue-hover`，並產生極微小的位移 `transform: translateY(-1px)`，搭配陰影放大 `box-shadow: 0 4px 16px rgba(0, 113, 183, 0.3)`。
- **Disabled 狀態**：設定 `opacity: 0.5; cursor: not-allowed;` 並移除 hover 效果。

### C. 列表項目 (List Items / History)
- 作為條列式的卡片（如歷史紀錄），縮小圓角至 `--radius-sm` (8px)。背景白底、帶有標準細邊框，Hover 時只需簡單切換邊框顏色即可，不必太過喧賓奪主。

### D. 標籤與副標題 (Tags / Sub-titles)
- 若具有分類性質的標籤（例如星座的「#火象 #開創」），文字顏色請使用 `--text-muted` 並且適度縮小字級 (約 `0.8rem`)，確保其視覺層級低於卡片主角。

---

## 給 AI 模型的執行指令 (Instruction for AI Model)

在接收到以此份指引為前提的新需求時，請你：
1. **嚴格不產生突兀的顏色**：除上述色彩外，原則上不允許使用預設的純紅、純綠等搶眼顏色，所有警示或成功狀態須轉化為低飽和的輔助色，搭配適當的 ICON 來表示。
2. **遵守空間幾何**：以 `padding` 為主控制內部留白，多用 `gap` 控制網格（Grid）和彈性盒子（Flex）元素間距，以避免不當的邊距重疊。
3. **支援 RWD**：桌面端若有複雜資訊，預設使用非對稱之雙欄佈局（例 `grid-template-columns: 2fr 1fr`），在 `max-width: 768px` 時折疊成 `1fr` 的單欄響應式排版。
4. **HTML 結構語意化**：遵循上述 CSS Classes 的命名邏輯（如 `.app-container`, `.card`, `.roll-btn`, `.text-muted` 等）來組織你的 HTML 模板。
