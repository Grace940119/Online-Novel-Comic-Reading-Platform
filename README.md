# 軟體工程報告
## 11224101紀嘉欣、11224108王馨儀

---

# 題目：小說與漫畫閱讀系統（Novel & Comic Reading Platform）

隨著網路閱讀的普及，小說與漫畫已成為許多人日常娛樂的一部分。本專案希望以實際情境為例，設計一個閱讀系統，藉此練習軟體工程中需求分析與系統設計的完整流程。

## 一、專案簡介

### 1. 專案目標

<img width="378" height="737" alt="專案簡介" src="https://github.com/user-attachments/assets/f6416264-a2cc-400e-8c14-582b5ab871fb" />



### 2. 使用對象
- 一般使用者（訪客 / 會員）
- 系統管理者 （內容管理）

---

## 二、需求說明書（Software Requirements Specification,SRS）

### 2.1 使用者角色（User Roles）
| 角色 | 說明 |
|----|----|
| 訪客 | 可瀏覽、搜尋、試閱作品內容 |
| 會員 | 可收藏作品、儲存閱讀進度、留言 |
| 管理員 | 管理小說、漫畫與章節內容 |

### 2.2 功能需求（Functional Requirements）
#### 2.2.1 使用者功能

<img width="285" height="686" alt="使用者功能" src="https://github.com/user-attachments/assets/14590701-a08a-4783-9fa9-48cdfe9704fa" />


#### 2.2.2 管理者功能

<img width="273" height="425" alt="管理者功能" src="https://github.com/user-attachments/assets/35ca1a1a-29d1-4c5c-b8bd-5a66d0d5f86f" />


### 2.3 非功能需求（Non-functional Requirements）
- 效能：頁面載入時間 < 3 秒
- 可用性：支援桌機與行動裝置瀏覽（RWD）
- 安全性：使用者資料具備基本安全保護
- 擴充性：系統具備未來功能擴充彈性

### 2.4 使用案例圖（Use Case Diagram）

<img width="442" height="642" alt="Use Case Diagram" src="https://github.com/user-attachments/assets/7359523c-ba5c-454d-9669-e0afb080736e" />

---


## 三、概要設計說明書（High-Level Design, HLD）

### 3.1 系統架構
採用 三層式架構（Three-Tier Architecture）：
- 表現層（Frontend）
- 應用層（Backend API）
- 資料層（Database）

<img width="3194" height="565" alt="Three-Tier Architecture" src="https://github.com/user-attachments/assets/a4e3cd87-fe17-458b-b30f-7218ecf59229" />


### 3.2模組劃分
| 模組 | 說明 |
|----|----|
| 使用者模組 | 登入、註冊、權限管理 |
| 內容模組 | 小說、漫畫、章節管理 |
| 閱讀模組 | 閱讀器、進度記錄 |
| 收藏模組 | 書架、追蹤 |
| 管理模組 | 後台管理功能 |

### 3.3 系統元件圖 （Component Diagram）

<img width="2608" height="1570" alt="Component Diagram" src="https://github.com/user-attachments/assets/fac8fb14-c7cd-4590-adcd-62e0593d5765" />

---

## 四、詳細設計說明書（Detailed Design, DDD）

### 4.1 資料庫設計（ER Diagram）

<img width="5828" height="3673" alt="ER Diagram" src="https://github.com/user-attachments/assets/800a068d-26a0-49a2-bfb3-ffabec2ec58b" />


### 4.2 閱讀流程（Sequence Diagram）

<img width="4250" height="2445" alt="Sequence Diagram" src="https://github.com/user-attachments/assets/f828ad38-45e8-4ad0-8490-cac9cd5eefbf" />



### 4.3 核心邏輯說明（範例）

本系統以 Activity Diagram 描述閱讀進度儲存流程，如圖所示。
圖中應包含節點：

<img width="2062" height="5156" alt="閱讀進度儲存流程" src="https://github.com/user-attachments/assets/3bd08207-6541-4ca0-a25f-2fcbd6ed51d8" />





### 4.4 模組內部職責與設計說明

本系統於詳細設計階段，將各功能模組的內部職責加以明確定義，以確保系統具備良好之可維護性與擴充性。

<img width="677" height="764" alt="模組內部職責與設計說明" src="https://github.com/user-attachments/assets/a530ac3b-862d-4001-84d1-4f4c13eb60d5" />



### 4.5 詳細設計說明總結

透過上述模組職責劃分，本系統在詳細設計階段已明確定義各功能單元之行為與責任，
並搭配 ER Diagram 與 Sequence Diagram 說明資料結構與操作流程，
可作為後續系統實作與維護之設計依據。

### 4.6 收藏作品流程 — Sequence Diagram

圖中角色：

User

Frontend

Backend

Database



<img width="5165" height="3015" alt="收藏作品流程" src="https://github.com/user-attachments/assets/e5dcd25d-4737-4e5c-8279-bbd572d7a686" />



### 4.7 管理員新增章節流程 — Activity Diagram

<img width="2141" height="6678" alt="管理者新增章節流程圖" src="https://github.com/user-attachments/assets/173bca98-e7bf-40d0-869f-87057f22359d" />


---

## 五、測試計畫（Test Plan）

### 5.1 測試範圍
| 測試類型 | 說明 |
|----|----|
| 單元測試 | API 與模組邏輯功能測試 |
| 整合測試 | 前後端串接測試 |
| 系統測試 | 完整操作流程測試 |
| 使用者測試 | 使用操作流暢度測試 |

### 5.2 測試案例（範例）
| 編號 | 測試項目 | 預期結果 |
|----|----|----|
| TC01 | 使用者登入功能 | 成功登入 |
| TC02 | 章節閱讀 | 正確顯示內容 |
| TC03 | 儲存進度 | 重新開啟可續讀 |

### 5.3 測試資源
- 測試人員：1–2 人
- 測試工具：瀏覽器、Postman

---

## 六、專案目錄結構（規劃）

<img width="645" height="680" alt="規劃" src="https://github.com/user-attachments/assets/a346b0e6-e43b-4828-a582-5063a75131ee" />

---

## 七、系統設計假設與限制

### 7.1 設計假設
- 假設使用者具備基本網頁操作能力，無需額外教學即可進行閱讀操作
- 假設系統主要使用於一般瀏覽器環境，不考慮極舊版本瀏覽器的相容性
- 假設管理者具備基本內容管理知識，能正確上傳與維護作品資料

### 7.2 系統限制
- 本系統為課程專案設計，未實際部署於高流量環境
- 未納入金流、付費訂閱等商業機制
- 系統安全性僅涵蓋基本帳號與權限控管，未實作進階防護機制

---

## 八、開發流程與方法說明

本專案於設計階段採用循序式（Waterfall）開發流程，依序進行需求分析、系統設計、詳細設計與測試規劃。

在需求分析階段，先定義系統使用者角色與功能需求，並以 Use Case Diagram 進行整理；
在系統設計階段，規劃整體系統架構與模組分工；
於詳細設計階段，透過 ER Diagram 與 Sequence Diagram 說明資料結構與行為流程；
最後於測試計畫中，規劃測試項目以確保系統品質。

此流程有助於在專案早期即明確定義系統範圍，降低後續設計修改之風險。

---

## 九、未來擴充與改進方向

若本系統於未來實際實作與部署，可考慮以下擴充方向：

- 新增評論與評分機制，提升使用者互動性
- 增加推薦系統，依使用者閱讀習慣推薦作品
- 導入訂閱或付費閱讀機制
- 提升系統安全性，如加強資料加密與權限驗證
- 支援多語系介面，擴展使用族群

---

## 十、心得
透過這次小說與漫畫閱讀系統的設計，我們學到如何從需求出發，逐步規劃系統架構與模組分工。雖然未實作成品，但對整體軟體開發流程有更清楚的理解。

