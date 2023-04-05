---
data
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:
Author:
Note Type:
Topics:

# Evergreen Note
Highlight:
Question:
Answer:
# Summary
#### 流程所跑模塊
- 使用者造訪頁面權限或編輯狀態(ex:用全域變數紀錄頁面狀態)
- 將使用者會造訪流程給列出
- 每個流程掛上會跑過模塊(ex:Model、View)
- 模塊上再去選模塊之間會跑AOP(如下)、全區域變數變化
#### AOP視角下Web Client
- 外部IO溝通提鍊readonly
- 將特別業務邏輯給提煉成readonly class or extension method
- 參數模塊建置
  - 提鍊到App.config
  - 內部調用匿名物件
- 將其分割成一個個模塊
- 模塊間從全域變數獲取能量
- 模塊之間用AOP規範
  - init
  - valid
  - commit
  - rollback
  - log
- 將所有模塊都用try-catch給包覆，參考[[exception設計準則]]
# Note
