---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
資料庫內有有許多表單且其編碼單號都有其自訂規則,任務是要按照單號編碼移轉到指定資料庫
# Question:
執行出現exception,發現是資料表單號欄位**有NULL**
# Answer:
在C#內的Regex只能**處理空字元**,是null時就會丟exception
[[Reg C語言]]實作