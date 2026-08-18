# 📟 HK Smart Home Dashboard (舊 iPad 活化計劃)

將閒置嘅舊款 iPad 轉化為專屬的「智能玄關資訊站」。透過整合香港政府的開放數據 (Open Data)，出門前只需一眼，即可掌握即時天氣與常用交通工具的到站時間。

專為舊設備設計：無須安裝任何第三方 App，採用極輕量化純前端代碼，完美兼容舊版 iOS Safari。

## ✨ 核心功能 (Features)

*   **🌤️ 實時天氣看板**：串接香港天文台 API，自動顯示天水圍區即時氣溫、濕度及今日最高/最低溫預測。
*   **🚌 智能交通樞紐**：
    *   支援跨公司交通網絡：**港鐵 (屯馬線)、輕鐵、九巴 (KMB)、港鐵巴士及大嶼山巴士 (NLB)**。
    *   **🤖 自動尋站引擎**：內建智能配對算法，只需設定關鍵字（如：`天慈`），系統會在首次載入時自動從過萬個巴士站中，尋獲對應的正確 Stop ID，無須手動查閱代碼。
*   **📱 舊機友善 (Legacy Device Friendly)**：
    *   單一 HTML 檔案運作，無任何沉重框架 (React/Vue)。
    *   內建 Date 格式修復代碼，解決舊版 iOS Safari 無法渲染時間的 Bug。
    *   支援全螢幕 Web App 模式。

## 🛠️ 技術棧 (Tech Stack)

*   **前端**：Vanilla JavaScript (ES6), HTML5, CSS3
*   **數據來源**：[資料一線通 (DATA.GOV.HK)](https://data.gov.hk/) 
    *   香港天文台 API (HKO)
    *   九巴開放數據 API (KMB)
    *   港鐵實時車務 API (MTR)
*   **部署**：GitHub Pages (靜態網頁託管)

## 🚀 部署指南 (Deployment)

只需 3 分鐘，即可免費將此專案部署到你的設備上：

1. Fork 或 Clone 此專案到你的 GitHub 帳號。
2. 進入專案庫 `Settings` > `Pages`。
3. 將 `Build and deployment` 的 Source 設為 `main` branch 並儲存。
4. 獲取你的專屬 GitHub Pages 連結。
5. 在你的 iPad Safari 開啟該連結，點擊 **「分享」** ➜ **「加入主畫面 (Add to Home Screen)」**，即可進入無邊框全螢幕模式。

## ⚙️ 自訂設定 (Customization)

你可以透過修改 `index.html` 內的 `<script>` 頂部變數，來更改你所在的屋苑或車站：

```javascript
// ==========================================
// 用戶設定區 (自動尋站引擎)
// ==========================================
const MY_STOP_NAME = '天慈'; // 修改為你樓下的巴士站名稱
const MTR_TML_STATION = 'TIS'; // 屯馬線車站代碼
const LRT_STATION = '435'; // 輕鐵站代碼

const KMB_ROUTES = [
  { route: '276B', dir: 'O', dest: '上水' },
  { route: '269M', dir: 'O', dest: '祖堯' },
  { route: 'B1',   dir: 'O', dest: '落馬洲' }
];
