---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
#資料 
# Unify


1. #flashcards 
- Highlight:MS-SQL
- Question:SUBSTRING('test',0,1) 
?
- Answer:其都為字串,因此return **空字元**

2. #flashcards 
- Highlight:MS-SQL
- Question:當欄位為空字元調用SUBSTRING
?
- Answer:其都為字串,因此return **空字元**



3. #flashcards 
- Highlight:MS-SQL
- Question:如何進行內建日期加減與轉型
?
- Answer:DATEADD參數不須加引號，0表示基准點 1900...
```
DECLARE @LAST_LAST_MONTH As DateTime;
SET @LAST_LAST_MONTH = DATEADD(mm,-2,GETDATE());
CONVERT(CHAR(8),GETDATE(),112)
CONVERT(CHAR(10),GETDATE(),111)
```

4. #flashcards 
- Highlight:MS-SQL
- Question:四捨五入、無條件進位、無條件捨去
?
- Answer:
```
SELECT FLOOR(4.9)
SELECT CEILING(3.05)
SELECT ROUND(3.4,0)
```

5. #flashcards 
- Highlight:MS-SQL
- Question:寫PROCEDUCE計算中要將資料存到暫存表，如何判別暫存表是否存在
?
- Answer:OBJECT_ID(搭配暫存表)
```
IF OBJECT_ID('tempdb..#name') IS NOT NULL
BEGIN
DROP TABLE #name
END
```

6. #flashcards 
- Highlight:
- Question:
?
- Answer:
