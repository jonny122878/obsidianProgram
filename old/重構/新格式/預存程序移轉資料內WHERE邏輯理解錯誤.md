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
排程每日都會執行預存程序,但隨著時間推移導致資料庫內資料量爆炸,規劃只留存**每月最後一日**資料,並且**當月資料都不刪除**
結構:
CrDate|datetime|移轉當下日期
Question:
1.**每月最後一日**所帶有特性為集合中最大值,因此利用此特性先進行GROUP BY處理做出年、月、日欄位
2.上述處理後欄位表進行GROUP MAX,並搭配WHERE過濾當月情況
SQL:WHERE year <> YEAR(GETDATE()) AND month <> MONTH(GETDATE())
Answer:
將SQL的WHERE 錯誤理解成**if短路條件**,但實際的情況是:
year <> YEAR(GETDATE())  => 符合條件表 => month <> MONTH(GETDATE()) => 符合條件表
# Summary

# Note
