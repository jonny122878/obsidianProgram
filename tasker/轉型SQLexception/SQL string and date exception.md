# Metadata
Qty::
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突



- 型態本身可以再按似不同儲存特性細分
- 日期儲存可能有日期型態或用字串日期格式表示，衍生查詢是否語法糖、是否要轉型或特定日期格式
- 字串本身會有類似無限長度，衍生出集合結合操作
- 字串本身有不同長度儲存，衍生出集合結合操作和亂碼


1. #flashcards 
- Highlight:
- Question:型別本身會有疊加態，在字串上呈現特性，以及預設轉型
?
- Answer:
- 資料庫定序就是疊加態之間互相轉型
- ntext、varbinary(max)因為過長已經跳脫出平常string能運算範圍

2. #flashcards 
- Highlight:
- Question:日期型別目前統整觀察發現日期型別有的是類似字串疊加態概念，並且有的無語法糖
?
- Answer:
- MS-SQL特有日期和字元語法糖，目前觀察Oracle、SQLite並不存在
- 日期型態目前已知只有在MS-SQL有語法糖



# Exception

1. #flashcards 
- Highlight:Oracle中日期型態
- Question:Oracle中進行WHERE述句條件日期型別比較該如何處理
?
- Answer:其自身並無MS-SQL一樣默認語法轉型，因此必須要特別將日期型別轉成字串來處理，或是特別用日期函數處理
```
and '2023-01-01' <= TO_CHAR(a.EXP_DATE,'YYYY-MM-DD') 
and to_date(:EffDate,'yyyy/mm/dd') <= exp_date
TO_CHAR(SYSDATE, 'YYYY-MM-DD HH24:MI:SS') //時分秒
```

2. #flashcards 
- Highlight:MS-SQL做PROCEDUCE計算
- Question:CASE WHEN對二個指定欄位做判別時若為二者空白與NULL均為一種情況，最後將呈現結果將二個欄位給相加
```
CASE ISNULL(,'') + '|' + ISNULL(,'') THEN 'Y'
ELSE 'N'
```
?
- Answer:欄位做串接Aggregate時，忽略default 符號中間串接符號，導致異常

3. #flashcards 
- Highlight:MS-SQL
- Question:在INSERT中文字時，會因為特殊字元而造成亂碼情況
?
- Answer:在insert值前面加入N修飾子即可

4. #flashcards 
- Highlight:MS-SQL 
- Question:資料類型ntext不可用UNION、INTERSECT 或EXCEPT運算子的運算元，因為不相容
?
- Answer:型別規範問題**text**只拿來記錄,若要運算nvarcahar(max)可解決

5. #flashcards 
- Highlight:MS-SQL
- Question:PROCEDUCE進行將計算結果寫入時出現**資料庫定序**問題，何謂資料庫定序?
?
- Answer:varchar => nvarcahar，不同字串型態不會**自動轉型**

6. #flashcards 
- Highlight:INSERT INTO SQL下丟出**字串或二進位會被截斷**
- Question:肉眼上看文本算字數是沒有超過的
?
- Answer:很明顯欄位**長度不足**,下方為各種型別儲存容量
- char、varchar(**2**) 中字只能塞一個,英字可以塞二個
- nchar、nvarchar(**2**) 中英都能塞二個
- **換行符號**會佔2字元


7. #flashcards 
- Highlight:MS-SQL
- Question:INSERT SQL用 'result' 寫到varbinary(max)丟出不允許資料類型varchar隱含轉到varbinary(max),請使用CONVET function，應都是string型態,為何丟出如上訊息?
?
- Answer:varbinary本質已經**跳脫** char、nchar、varchar、nvarchar這些規則,可以想成是另種類似string型態了

8. #flashcards 
- Highlight: SQLLite
- Question:如何對日期型態操作
?
- Answer:[SQLITE沒有日期型態或時間型態](http://coding-warehouse.logdown.com/posts/7329105-sqlite-date-and-time-functions)

9. #flashcards 
- Highlight:Oracle
- Question:ORA-01722: 無效的數字 
?
- Answer:
```
SELECT QUOTE_NO + ' ' + ID_NO FROM NC_QUOTE_INSURED //error 無語法糖
SELECT QUOTE_NO || ' ' || ID_NO FROM NC_QUOTE_INSURED
```
10. #flashcards 
- Highlight:Oracle
- Question:如何寫入目前系統時間
?
- Answer:SYSDATE

11. #flashcards 
- Highlight:Oracle
- Question:Code First之後comments都是亂碼
?
- Answer:
```
自動生成SQL指令N修飾子造成
COMMENT ON COLUMN "NC_POLICY_TALK"."UPDATED_USER" is N'更新人員' 
```

12. #flashcards 
- Highlight:
- Question:
?
- Answer:


