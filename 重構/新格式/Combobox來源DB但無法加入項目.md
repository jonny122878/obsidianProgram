---
data:2023-02-22
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project租貸
Author:
Note Type:
Topics:MS-SQL

# Evergreen Note
Highlight:
前台combobox來源項目從**DB撈出**,客戶需求要多增加一個項目
Question:
因DB表格**欄位過多**,所以透過既有的表撈取欄位,並修改特定要的某些值塞入
SQL:
INSERT INTO APCodeMap
SELECT TabName,'01',........
FROM APCodeMap
WHERE TabName = ''
Answer:
MS-SQL丟出**重複PK值無法寫入**,原因SELECT FROM 本質是**集合**,INSERT INTO本身是單一元素,要注意集合內只能有一筆,將其本質轉成元素
# Summary

# Note
