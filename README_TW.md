# TechKids

TechKids 是一個面向 5 至 12 歲兒童的技術啟蒙 App Demo，透過「程式探險」「AI 小夥伴」「創意工坊」「家長中心」四個模組，展示兒童友善的遊戲化程式學習與 AI 互動產品原型。

目前版本定位為 **V1.0.4 產品 Demo**：主程式以單一 HTML 檔案呈現，PRD 已涵蓋後端代理、安全 Prompt、Few-Shot 方向與創意工坊增強。V1.0.5 的下一步需求分析請參考 [GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5需求分析.md)。

[English](README_EN.md) | [简体中文](README_CN.md) | [繁體中文](README_TW.md)

📖 目錄
- [專案亮點](#專案亮點)
- [技術架構](#技術架構)
- [快速開始](#快速開始)
  - [直接開啟](#直接開啟)
  - [使用本機伺服器](#使用本機伺服器)
  - [AI 代理說明](#ai-代理說明)
- [專案結構](#專案結構)
- [版本脈絡](#版本脈絡)
- [文件入口](#文件入口)
- [安全與兒童體驗原則](#安全與兒童體驗原則)
- [License](#license)

## 專案亮點

| 模組 | 目前能力 |
|---|---|
| 程式探險島 | 網格座標關卡、前進/左轉/右轉指令、執行日誌、星級獎勵、激勵廣告演示 |
| AI 小夥伴實驗室 | 小智 Bot 養成、兒童安全過濾、DeepSeek 代理呼叫設定、失敗兜底回覆、ML 分類小遊戲 |
| 創意工坊 | 我的作品、範本庫、每週挑戰、作品詳情頁、預覽動畫、localStorage 草稿保存 |
| 家長中心 | 學習時長、關卡進度、模組進度、廣告與使用時間控制 |
| 個人與排行 | 使用者等級、金幣/星星、成就入口、Top3 頒獎台與排行榜列表 |

## 技術架構

| 技術 | 用途 |
|---|---|
| HTML5 | 單檔 Demo 架構 |
| CSS3 | iPad 裝置框、版面、動畫與主題樣式 |
| Vanilla JavaScript | 頁面切換、遊戲邏輯、AI 聊天、草稿儲存、挑戰進度 |
| localStorage | 儲存草稿作品與挑戰進度 |
| DeepSeek API 代理設定 | 前端指向本機代理位址，避免 API Key 出現在瀏覽器程式碼中 |

## 快速開始

### 直接開啟

雙擊 `TechKids_Demo.html` 即可在現代瀏覽器中體驗 Demo。若本機代理未啟動，AI 聊天會自動使用內建兜底回覆。

### 使用本機伺服器

```bash
python -m http.server 8080
```

接著開啟：

```text
http://localhost:8080/TechKids_Demo.html
```

### AI 代理說明

Demo 中的 AI 請求預設指向：

```javascript
endpoint: 'http://127.0.0.1:8765/chat'
```

PRD V1.0.4 已定義 `server.py` 後端代理方案，但目前倉庫尚未包含實際 Python 代理腳本。建議在 V1.0.5 補齊 `server.py`、`.env.example`、`start_proxy.bat` 與 `README_PROXY.md`，並確保 API Key 只存在於服務端環境變數中。

## 專案結構

```text
TechKid/
├── TechKids_Demo.html                 # 主 Demo，包含 HTML/CSS/JS
├── TechKids_PRD_V1.0.4.md             # 目前產品需求文件
├── README_CN.md                       # 簡體中文 README
├── README_TW.md                       # 繁體中文 README
├── README_EN.md                       # English README
├── LICENSE
└── GIt TechKid/
    ├── 海外市场App投资价值分析报告.md
    ├── 部分要求.md
    └── v1.0.5需求分析.md
```

## 版本脈絡

| 版本 | 狀態 | 主要內容 |
|---|---|---|
| V1.0.1 | 已完成 | 排行榜、個人中心、基礎 UI 與返回邏輯 |
| V1.0.2 | 已完成 | 網格座標重構、Bot 黏滯佈局、執行日誌 |
| V1.0.3 | 已完成 | DeepSeek 對話、內容過濾、創意工坊增強 |
| V1.0.4 | 已寫入 PRD / Demo 部分體現 | 後端代理架構、Prompt 強化、安全初始化 |
| V1.0.5 | 待開發 | 代理交付閉環、顯式 Few-Shot、學習路徑、家長報告、創作閉環、海外化準備 |

## 文件入口

- 產品需求文件：[TechKids_PRD_V1.0.4.md](./TechKids_PRD_V1.0.4.md)
- 海外市場分析：[GIt TechKid/海外市场App投资价值分析报告.md](./GIt%20TechKid/%E6%B5%B7%E5%A4%96%E5%B8%82%E5%9C%BAApp%E6%8A%95%E8%B5%84%E4%BB%B7%E5%80%BC%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A.md)
- V1.0.5 需求分析：[GIt TechKid/v1.0.5需求分析.md](./GIt%20TechKid/v1.0.5%E9%9C%80%E6%B1%82%E5%88%86%E6%9E%90.md)

## 安全與兒童體驗原則

- 不在前端保存真實 API Key。
- AI 對話預設經過越獄、隱私、成人敏感內容與主題相關性過濾。
- 不要求兒童提供真實姓名、學校、地址、電話、照片或帳號密碼。
- 廣告、分享、排行榜、家長設定等能力應優先使用家長門檻與兒童安全提示。
- 後續若面向海外市場，需要進一步補齊 COPPA/GDPR-K 合規、家長同意、資料匯出與刪除流程。

## License

MIT License. See [LICENSE](./LICENSE).
