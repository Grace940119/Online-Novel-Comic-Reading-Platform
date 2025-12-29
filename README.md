# 軟體工程報告
## 11224101紀嘉欣、11224108王馨儀

---

# 題目：小說與漫畫閱讀系統（Novel & Comic Reading Platform）

隨著網路閱讀的普及，小說與漫畫已成為許多人日常娛樂的一部分。本專案希望以實際情境為例，設計一個閱讀系統，藉此練習軟體工程中需求分析與系統設計的完整流程。

## 一、專案簡介

### 1. 專案目標
建立一個可於瀏覽器上使用的閱讀平台，讓使用者能夠：
- 線上閱讀小說與漫畫
- 管理個人書架與閱讀進度
- 進行作品搜尋、分類瀏覽與收藏
- 提供管理者後台維護與內容管理

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
- 使用者註冊 / 登入 / 登出
- 瀏覽小說 / 漫畫列表
- 依分類、作者、關鍵字搜尋
- 章節閱讀（小說文字 / 漫畫圖片）
- 自動記錄閱讀進度
- 收藏作品至個人書架

#### 2.2.2 管理者功能
- 新增 / 編輯 / 刪除作品
- 上傳章節內容（文字 / 圖片）
- 管理使用者帳號

### 2.3 非功能需求（Non-functional Requirements）
- 效能：頁面載入時間 < 3 秒
- 可用性：支援桌機與行動裝置瀏覽（RWD）
- 安全性：使用者資料具備基本安全保護
- 擴充性：系統具備未來功能擴充彈性

### 2.4 使用案例圖（Use Case Diagram）

<img width="600" height="476" alt="Use Case Diagram" src="https://github.com/user-attachments/assets/0024acb7-41a9-4793-9843-d4fb4afc9031" />


---

## 三、概要設計說明書（High-Level Design, HLD）

### 3.1 系統架構
採用 三層式架構（Three-Tier Architecture）：
- 表現層（Frontend）
- 應用層（Backend API）
- 資料層（Database）

<img width="638" height="601" alt="Three-Tier Architecture" src="https://github.com/user-attachments/assets/84725028-d4df-4c0a-8de0-1fb7c5244ba6" />



### 3.2模組劃分
| 模組 | 說明 |
|----|----|
| 使用者模組 | 登入、註冊、權限管理 |
| 內容模組 | 小說、漫畫、章節管理 |
| 閱讀模組 | 閱讀器、進度記錄 |
| 收藏模組 | 書架、追蹤 |
| 管理模組 | 後台管理功能 |

### 3.3 系統元件圖 （Component Diagram）

<img width="603" height="432" alt="Component Diagram" src="https://github.com/user-attachments/assets/a62c500b-fc78-4873-b505-edb6b741bf32" />

---

## 四、詳細設計說明書（Detailed Design, DDD）

### 4.1 資料庫設計（ER Diagram）

<img width="606" height="586" alt="ER Diagram" src="https://github.com/user-attachments/assets/0889dc90-4219-4690-aeb4-65feb31df9b1" />


關聯說明

- USER 1 ─── * BOOKMARK

- USER 1 ─── * READING_PROGRESS

- WORK 1 ─── * CHAPTER

- WORK 1 ─── * BOOKMARK

### 4.2 閱讀流程（Sequence Diagram）

<img width="605" height="457" alt="Sequence Diagram" src="https://github.com/user-attachments/assets/a56fc008-a4c0-44ec-9e81-ac0d62876ce8" />


### 4.3 核心邏輯說明（範例）

本系統以 Activity Diagram 描述閱讀進度儲存流程，如圖所示。
圖中應包含節點：

<img width="727" height="542" alt="閱讀進度儲存流程" src="https://github.com/user-attachments/assets/52e50c1d-53d4-4a0e-a10a-debc77299f6c" />




### 4.4 模組內部職責與設計說明

本系統於詳細設計階段，將各功能模組的內部職責加以明確定義，以確保系統具備良好之可維護性與擴充性。

<img width="638" height="577" alt="Class Diagram(1)" src="https://github.com/user-attachments/assets/97de46a0-28bd-4cc5-83b7-6887f0c28757" />
<img width="642" height="595" alt="Class Diagram(2)" src="https://github.com/user-attachments/assets/88ef171e-9de8-48d4-8045-c7991120ffe1" />

模組關係說明


<img width="648" height="192" alt="Class Diagram(3)" src="https://github.com/user-attachments/assets/18856779-30a8-468c-8294-1d6480f6392f" />


### 4.5 詳細設計說明總結

透過上述模組職責劃分，本系統在詳細設計階段已明確定義各功能單元之行為與責任，
並搭配 ER Diagram 與 Sequence Diagram 說明資料結構與操作流程，
可作為後續系統實作與維護之設計依據。

### 4.6 收藏作品流程 — Sequence Diagram

圖中角色：

User

Frontend

BookmarkController

BookmarkService

Database


<img width="725" height="465" alt="Sequence Diagram" src="https://github.com/user-attachments/assets/a3afe91f-fcbe-44dd-8fce-8924e70daf9e" />



### 4.7 管理員新增章節流程 — Activity Diagram

<img width="637" height="617" alt="管理員新增章節流程" src="https://github.com/user-attachments/assets/9bfe81e9-313c-4a7e-91ca-5cfed229fd85" />

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

<img width="593" height="226" alt="規劃" src="https://github.com/user-attachments/assets/f5a8a38f-48cb-44b7-856b-339862ce397e" />

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

