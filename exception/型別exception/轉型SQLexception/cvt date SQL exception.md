# Metadata
Qty::3
Review::
Restructure::

### Think



# Exception


1. #flashcards 
- Highlight: SQLLite
- Question:如何對日期型態操作
?
- Answer:[SQLITE沒有日期型態或時間型態](http://coding-warehouse.logdown.com/posts/7329105-sqlite-date-and-time-functions)

2. #flashcards 
- Highlight:Oracle中日期型態
- Question:Oracle中進行WHERE述句條件日期型別比較該如何處理
?
- Answer:其自身並無MS-SQL一樣默認語法轉型，因此必須要特別將日期型別轉成字串來處理，或是特別用日期函數處理
```
and '2023-01-01' <= TO_CHAR(a.EXP_DATE,'YYYY-MM-DD') 
and to_date(:EffDate,'yyyy/mm/dd') <= exp_date
TO_CHAR(SYSDATE, 'YYYY-MM-DD HH24:MI:SS') //時分秒
```

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
