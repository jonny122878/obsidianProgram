---
data:2023-02-23
aliases:
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:租貸
Author:
Note Type:筆記
Topics:MS-SQL

# Evergreen Note
Highlight:
AP在建檔寫入資料時丟出**資料行數量<欄位數**訊息
Question:
訊息判別是組合SQL字串時出了問題
Answer:
從數量這個線索可以推估，在AP使用者互動框內含有,或'特殊符號，INSERT INTO子句會變成多個欄位
# Summary

# Note
