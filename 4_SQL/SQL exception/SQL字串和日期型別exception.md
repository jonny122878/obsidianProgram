---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::租貸、金財通
Author::
Note Type::
Topics::SQL
#資訊 #金財通 
# Unify




1. #flashcards 
- Highlight:Oracle中日期型態
- Question:Oracle中進行WHERE述句條件日期型別比較該如何處理
?
- Answer:其自身並無MS-SQL一樣默認語法轉型，因此必須要特別將日期型別轉成字串來處理
```
and '2023-01-01' <= TO_CHAR(a.EXP_DATE,'YYYY-MM-DD') 
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
- Highlight:
- Question:
?
- Answer:

