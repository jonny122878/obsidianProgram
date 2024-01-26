# Metadata
Qty::5
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突

# Exception



1. #flashcards 
- Highlight:MS-SQL接手別人寫aspx程式時，使用者反應並資料寫到資料庫，但當下看INSERT語句也看不出所以然來
- Question:insert into table values ()出現錯誤
?
- Answer:將程式Prase SQL貼到MS-SQL後，發現是**直覺理解**有問題，若不打欄位情況下每個欄位值都必須要塞值

2. #flashcards 
- Highlight:在Oracle SQL Developer中調用SQL語句
- Question:明明資料庫訊息已經呈現刪除筆數完畢，用EF撈取卻還有資料?
?
- Answer:在Oracle SQL Developer要**確認變更**

3. #flashcards 
- Highlight:AP在建檔寫入資料時丟出**資料行數量<欄位數**訊息
- Question:訊息判別是組合SQL字串時出了問題
?
- Answer:從數量這個線索可以推估，在AP使用者互動框內含有,或'特殊符號，INSERT INTO子句會變成多個欄位

4. #flashcards 
- Highlight:MS-SQL
- Question:UPDATE INNER JOIN 副表A 100 副表B 105 主表其會如何替換?
?
- Answer:最後表B為數量基準

5. #flashcards 
- Highlight:MS-SQL
- Question:UPDATE INNER JOIN 副表與主表為1-M關係,其會如何替換?
?
- Answer:只替換M數量表格第一筆
