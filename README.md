# 軟體工程報告
## 11224101紀嘉欣、11224108王馨儀

---

# 題目：小說與漫畫閱讀系統（Novel & Comic Reading Platform）

隨著網路閱讀的普及，小說與漫畫已成為許多人日常娛樂的一部分。本專案希望以實際情境為例，設計一個閱讀系統，藉此練習軟體工程中需求分析與系統設計的完整流程。

## 一、專案簡介 (Project Overview)

本專案旨在設計一套小說與漫畫閱讀系統，
透過實際應用情境，練習軟體工程中
需求分析、系統架構設計與詳細設計之完整流程。

系統提供使用者瀏覽小說與漫畫作品、
閱讀章節內容、收藏作品與儲存閱讀進度等功能，
並支援管理者進行作品與章節之後台管理。

本文件著重於系統之設計與規劃，
未包含實際系統實作。

本專案作為軟體工程課程之設計練習案例。


### 1. 專案目標（Project Objectives）

本專案之主要目標如下：
- 設計一套完整的小說與漫畫閱讀系統之系統架構與功能模組。
- 透過需求分析、系統設計與詳細設計，
  熟悉軟體工程文件撰寫與系統設計流程。
- 使用 UML 圖（如 Use Case Diagram、ER Diagram、
  Component Diagram、Sequence Diagram 與 Activity Diagram）
  清楚表達系統結構與操作流程。
- 建立具備良好可維護性與擴充性的系統設計基礎，
  作為後續實作或延伸發展之依據。

### 2. 使用對象（Target Users）

- 一般使用者（訪客 / 會員）
- 系統管理者 （內容管理）

### 3. 使用對象及對應功能 (Target Users and Corresponding Functions)

<img width="378" height="737" alt="專案簡介" src="https://github.com/user-attachments/assets/bff27df3-92d5-42e5-a0d8-cda939b98dea" />


## 二、需求說明書（Software Requirements Specification,SRS）

### 2.1 使用者角色（User Roles）
| 角色 | 說明 |
|----|----|
| 訪客 | 可瀏覽、搜尋、試閱作品內容 |
| 會員 | 可收藏作品、儲存閱讀進度、留言 |
| 管理員 | 管理小說、漫畫與章節內容 |

### 2.2 功能需求（Functional Requirements）

#### 2.2.1 使用者功能（Member/Guest）

<img width="285" height="686" alt="使用者功能" src="https://github.com/user-attachments/assets/14590701-a08a-4783-9fa9-48cdfe9704fa" />


#### 2.2.2 管理者功能（Admin）

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

### 3.1 系統架構（System Architecture）

採用 三層式架構（Three-Tier Architecture）：
- 表現層（Frontend）
- 應用層（Backend API）
- 資料層（Database）

<img width="3194" height="565" alt="Three-Tier Architecture" src="https://github.com/user-attachments/assets/a4e3cd87-fe17-458b-b30f-7218ecf59229" />


### 3.2模組劃分（Module Decomposition）

| 模組 | 說明 |
|----|----|
| 使用者模組（User Module）| 登入、註冊、權限管理 |
| 內容模組（Content Module） | 小說、漫畫、章節管理 |
| 閱讀模組（Reading Module） | 閱讀器、進度記錄 |
| 收藏模組（Bookmark Module） | 書架、追蹤 |
| 管理模組（Admin Module） | 後台管理功能 |

### 3.3 系統元件圖 (System Component Diagram)

<img width="2608" height="1570" alt="Component Diagram" src="https://github.com/user-attachments/assets/fac8fb14-c7cd-4590-adcd-62e0593d5765" />

---

## 四、詳細設計說明書（Detailed Design, DDD）

### 4.1 資料庫設計（Database Design）

本系統以 ER Diagram 描述資料庫結構與實體關係。

<img width="5828" height="3673" alt="ER Diagram" src="https://github.com/user-attachments/assets/800a068d-26a0-49a2-bfb3-ffabec2ec58b" />


### 4.2 閱讀流程（Reading Activity Diagram）

本系統以 Activity Diagram 描述使用者閱讀章節時，
系統如何載入內容並自動儲存閱讀進度之流程。
本流程圖呈現使用者閱讀、章節切換與閱讀進度儲存之核心行為。

<img width="4250" height="2445" alt="Sequence Diagram" src="https://github.com/user-attachments/assets/f828ad38-45e8-4ad0-8490-cac9cd5eefbf" />



### 4.3 核心邏輯說明（範例）(Core Process Description – Example)

本系統以 Activity Diagram 描述閱讀進度儲存流程，如圖所示。
圖中應包含節點：

<img width="2062" height="5156" alt="閱讀進度儲存流程" src="https://github.com/user-attachments/assets/3bd08207-6541-4ca0-a25f-2fcbd6ed51d8" />





### 4.4 模組內部職責與設計說明 (Module Responsibilities and Design Description)

本系統於詳細設計階段，針對各功能模組之內部職責進行定義，
並以 UML 設計圖呈現模組間責任分工與互動關係，
以確保系統具備良好之可維護性與擴充性。

本系統於詳細設計階段，將各功能模組的內部職責加以明確定義，以確保系統具備良好之可維護性與擴充性。

<img width="677" height="764" alt="模組內部職責與設計說明" src="https://github.com/user-attachments/assets/a530ac3b-862d-4001-84d1-4f4c13eb60d5" />



### 4.5 詳細設計說明總結 (Detailed Design Summary)

透過前述之模組劃分與詳細設計，
本系統已明確定義各功能模組之內部職責與互動關係。
本章節搭配 ER Diagram、Component Diagram、
Sequence Diagram 與 Activity Diagram，
完整說明系統之資料結構與核心操作流程，
可作為後續系統實作與維護之設計依據。

### 4.6 收藏作品流程 — Sequence Diagram (Bookmark Process — Sequence Diagram)

本流程以 Sequence Diagram 描述使用者收藏作品時，
前端、後端與資料庫之間的互動順序與資料傳遞流程。

圖中角色：

User

Frontend

Backend

Database



<img width="5165" height="3015" alt="收藏作品流程" src="https://github.com/user-attachments/assets/e5dcd25d-4737-4e5c-8279-bbd572d7a686" />



### 4.7 管理員新增章節流程 — Activity Diagram (Administrator Add Chapter Workflow — Activity Diagram)

本流程以 Activity Diagram 描述系統管理員於後台新增章節時，
從輸入章節資料、系統驗證至資料寫入之完整流程。

<img width="2141" height="6678" alt="管理者新增章節流程圖" src="https://github.com/user-attachments/assets/173bca98-e7bf-40d0-869f-87057f22359d" />


---

## 五、測試計畫（Test Plan）

### 5.1 測試範圍 (Test Scope)

本測試計畫涵蓋系統主要功能模組與核心操作流程，
以確保系統在功能正確性、整合性與使用體驗上符合設計需求。

### 5.2 測試類型 (Test Types)

| 測試類型 | 說明 |
|----|----|
| 單元測試 (Unit Testing) | API 與模組邏輯功能測試 |
| 整合測試 (Integration Testing) | 前後端串接測試 |
| 系統測試 (System Testing) | 完整操作流程測試 |
| 使用者測試 (User Acceptance Testing (UAT)) | 使用操作流暢度測試 |

### 5.2 測試案例（範例）（Test Cases）

| 編號 | 測試項目 | 預期結果 |
|----|----|----|
| TC01 | 使用者登入功能 | 成功登入系統 |
| TC02 | 章節閱讀 | 正確顯示章節內容 |
| TC03 | 儲存進度 | 重新開啟可續讀 |
| TC04 | 收藏作品 | 收藏成功並顯示於書架 |
| TC05 | 新增章節（管理員） | 成功寫入資料庫 |

### 5.3 測試資源 (Test Resources)

- 測試人員：1–2 人
- 測試環境：一般瀏覽器環境
- 測試工具：瀏覽器、Postman

---

## 六、專案目錄結構（規劃）(Project Directory Structure – Planned)

<img width="645" height="680" alt="規劃" src="https://github.com/user-attachments/assets/a346b0e6-e43b-4828-a582-5063a75131ee" />

---

## 七、系統設計假設與限制 (System Design Assumptions and Constraints)

### 7.1 設計假設 (Design Assumptions)

- 假設使用者具備基本網頁操作能力，無需額外教學即可進行閱讀與操作。
- 假設系統主要運行於現代瀏覽器環境，不考慮過於老舊之瀏覽器相容性。
- 假設系統管理者具備基本內容管理知識，能正確上傳與維護作品與章節資料。


### 7.2 系統限制 (System Constraints)

- 本系統為課程專案設計，未實際部署於高流量或正式商業環境。
- 系統未納入金流、付費訂閱或商業交易相關功能。
- 系統安全性僅涵蓋基本帳號驗證與權限控管，未實作進階資安防護機制。

---

## 八、開發流程與方法說明 (Development Process and Methodology)

本專案於系統設計階段採用循序式（Waterfall）開發流程，
依序進行需求分析、系統設計、詳細設計與測試規劃。

在需求分析階段，先定義系統使用者角色與功能需求，
並以 Use Case Diagram 進行整理；
於系統設計階段，規劃整體系統架構與模組劃分；
於詳細設計階段，透過 ER Diagram、Component Diagram、
Sequence Diagram 與 Activity Diagram
說明系統之資料結構與核心操作流程；
最後於測試計畫中，規劃測試項目以確保系統品質。

此開發流程有助於於專案早期即明確定義系統範圍，
降低後續設計變更之風險，並提升整體設計一致性。


---

## 九、未來擴充與改進方向 (Future Enhancements and Improvements)

若本系統於未來實際進行開發與部署，
可考慮以下擴充與改進方向，以提升系統功能性與使用者體驗：

- 新增評論與評分機制，提升使用者互動性與內容參與度。
- 導入推薦系統，依使用者閱讀與收藏行為推薦相關作品。
- 增加訂閱或付費閱讀機制，以支援商業化應用情境。
- 強化系統安全性，如加強資料加密與權限驗證機制。
- 支援多語系介面，以擴展不同語言使用族群。

上述擴充方向可於不影響既有系統架構下逐步導入。


---

## 十、心得 (Reflection)

透過這次小說與漫畫閱讀系統的設計，我們學到如何從需求出發，逐步規劃系統架構與模組分工。雖然未實作成品，但對整體軟體開發流程有更清楚的理解。

