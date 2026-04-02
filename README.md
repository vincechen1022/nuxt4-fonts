# nuxt4-fonts

以 Nuxt 4 與 `@nuxt/fonts` 為主的實驗專案，用來觀察加入 **Noto Sans**／**Noto Sans TC** 後，建置產物與瀏覽器端資源行為。

## 專案目的

本專案建立的主要原由，是**測試在專案中接入 Noto Sans 系列字型後，相關資源的大小與載入情形**（含 `@nuxt/fonts` 產生的 CSS／字型檔等），方便與未接入或不同設定的情況對照。

## 字體設定

字型於 `nuxt.config.ts` 的 `fonts.families` 中設定（Google：`Noto Sans`、`Noto Sans TC`）。全域字族與 Tailwind `font-sans` 見 `app/assets/css/global.css` 與 `tailwind.config.js`。

## 測試方式與觀察 Coverage

建議流程：

1. **`pnpm build`**：產出正式建置。
2. **`pnpm preview`**：以接近上線的方式在本機預覽。
3. 開啟**瀏覽器開發者工具 → Coverage**，在錄製一段操作後檢視 **JS／CSS 的使用與未使用比例**。

## 測試結論

依上述方式實測，**接入 Noto Sans（含 Noto Sans TC 等設定）後，整體下載與打包出來的相關資源明顯變成很大一包**（字型檔分片、`@font-face` 與對應 CSS 等加總後體積顯著上升）。

---

## Nuxt Font 配置

參考: https://stackblitz.com/github/nuxt/fonts/tree/main/playgrounds/basic?file=tsconfig.json

