# 🏰《米奇奇幻專注工作站》產品規格書 (PRD)

## 一、 專案簡介 (Project Overview)
* **專案名稱：** Mickey's Magical Focus Station（米奇奇幻專注工作站）
* **專案目標：** 結合迪士尼米奇視覺元素與沉浸式音效，打造一款兼具實用性與樂趣的單頁式互動專注計時器（Pomodoro Timer）與白噪音混音器（Soundboard）。
* **使用者體驗：** **免登入、免安裝**，終端使用者開啟網頁連結即可直接免費使用。
* **交付格式：** **單一 `index.html` 檔案**（所有 HTML 結構、Tailwind CSS 樣式與 JavaScript 邏輯皆封裝於單一檔案中）。
* **網站架設：** 使用 GitHub Pages 代管發布成公開網頁。

---

## 二、 視覺風格與主題 (Visual Vibe & UI Design)
* **整體氣氛：** 深邃夜空與迪士尼慶典風格。
* **背景視覺：** 深藍色漸層夜空（`#1B263B` 至 `#0D1B2A`），搭配 CSS 動態閃爍微光星星，頁面底部呈現黑色迪士尼城堡剪影。
* **配色系統：**
  * 主視覺色：迪士尼金色（`#FFD700`）
  * 強調按鈕：米奇經典紅（`#E60012`）
  * 卡片風格：半透明玻璃擬物風格（Glassmorphism Card）

---

## 三、 畫面區塊與元件規格 (UI Components & Functional Spec)

### 1. 頂部標題區 (Header)
* **主標題：** 🏰 `Mickey's Magical Focus Station`（金色發光字體）
* **副標題：** 「開啟專注魔法，與米奇一起完成今日任務！」

---

### 2. 中央區域：米奇拉霸造型專注計時器 (Timer & Slot Machine Section)
* **主體結構：**
  * 畫面中央為米奇輪廓造型（1 個中央大圓形 + 左右上方各 1 個小圓形作為大耳朵）。
* **拉霸計時元件 (Slot Machine Roller)：**
  * 大圓形中央顯示「分（Minutes）」與「秒（Seconds）」兩個動態滾輪。
  * **數值範圍規範：**
    * **「分」滾輪：** `00 ~ 59` 分鐘
    * **「秒」滾輪：** 嚴格限制為 `00 ~ 59` 秒（最大時間設定為 59 分 59 秒）
  * **互動方式：** 未啟動計時時，使用者可以透過滑鼠滾輪或手指/觸控板上下滑動滾輪，自由設定時間。
* **米奇機關搖桿 (Mickey Lever)：**
  * 計時器右側設有一座米奇紅黃配色的拉桿，點擊時會呈現下壓動畫，代表鎖定時間並啟動計時。
* **按鈕與控制項：**
  * **預設快速鍵 (Quick Presets)：**
    * `[ 魔法專注 (25m) ]` 按鈕：點擊後拉霸自動滾動並定格在 `25:00`。
    * `[ 奇幻休息 (5m) ]` 按鈕：點擊後拉霸自動滾動並定格在 `05:00`。
  * **控制按鈕：**
    * **`[ ▶ 開始 / 拉搖桿 ]` 按鈕：** 米奇紅底白字圓角按鈕。點擊後啟動倒數，按鈕切換為 `[ ⏸ 暫停 ]`，此時拉霸數值鎖定。
    * **`[ ↺ 重置 ]` 按鈕：** 灰色邊框半透明按鈕。點擊後停止計時並解鎖拉霸滾輪。
* **完成反饋：**
  * 倒數歸零（`00:00`）時，數字觸發跳動動畫，全螢幕發射迪士尼煙火粒子效果（Canvas Confetti），並播放歡慶音效。

---

### 3. 下方區域：奇幻環境音效混音面板 (Soundboard Section)
* **介面呈現：** 半透明卡片，內含 3 組可獨立開關與混合音量的白噪音列：
  1. 🎆 **城堡煙火聲 (Castle Fireworks)**：靜音切換按鈕 `[ 🔊 / 🔇 ]` + 音量滑桿（Slider, 0%-100%）。
  2. 🌧️ **樂園雨聲 (Rainy Disneyland)**：靜音切換按鈕 `[ 🔊 / 🔇 ]` + 音量滑桿（Slider, 0%-100%）。
  3. ☕ **米奇咖啡館 (Mickey's Cafe)**：靜音切換按鈕 `[ 🔊 / 🔇 ]` + 音量滑桿（Slider, 0%-100%）。

---

### 4. 底部區域：迪士尼金句卡片 (Footer Quote Section)
* **功能說明：** 隨機顯示華特迪士尼或迪士尼動畫經典勵志名言。
* **互動按鈕：** 右側設置 `[ 🎲 換一句 ]` 按鈕，點擊後更換顯示名言。

---

## 四、 Vibe Coding 單一檔案生成提示詞 (Single-file Prompt)

```text
Please generate a complete, standalone, single HTML file named "index.html" for "Mickey's Magical Focus Station". 

CRITICAL REQUIREMENT: 
- Everything (HTML structure, CSS styles, JavaScript logic, inline Web Audio/effects, and external CDN scripts) MUST be inside this single index.html file. Do NOT use separate files or folders.

Key UI & Vibe Specifications:
1. Styling: Use Tailwind CSS via CDN (<script src="[https://cdn.tailwindcss.com](https://cdn.tailwindcss.com)"></script>) and Canvas Confetti CDN for fireworks (<script src="[https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js](https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js)"></script>).
2. Background: Deep navy blue gradient (#1B263B to #0D1B2A) with animated subtle twinkling CSS stars and a dark silhouette of a Disney castle at the bottom.
3. Palette: Golden yellow (#FFD700), Mickey Red (#E60012), and glassmorphism cards.

Component Specs inside single index.html:
- Header: Title "Mickey's Magical Focus Station" in glowing gold with subtitle "開啟專注魔法，與米奇一起完成今日任務！".
- Slot Machine Timer Section:
  - Mickey shape (1 big center circle + 2 ear circles at top-left/top-right).
  - Slot Machine Rollers inside center circle: Minutes roller (00 to 59) and Seconds roller (00 to 59). Allow mouse drag/scroll to change numbers when idle.
  - Animated Mickey Lever on the right side that pulls down on start.
  - Quick Presets: "[ 25m Focus ]" and "[ 5m Break ]" buttons that spin slots to 25:00 and 05:00.
  - Controls: Red "[ ▶ Start ]" (toggles Pause) and gray "[ ↺ Reset ]".
  - On 00:00: Trigger confetti fireworks and play an audio chime using Web Audio API oscillator.
- Soundboard Section:
  - 3 rows: 🎆 Castle Fireworks, 🌧️ Rainy Disneyland, ☕ Mickey's Cafe.
  - Each has a mute toggle button and a volume slider (0-100%). Use synthetic Web Audio noise or HTML5 audio nodes.
- Footer Quote:
  - Disney quote card with a "[ 🎲 換一句 ]" button to cycle through quotes.

Output ONLY the raw executable index.html code.
