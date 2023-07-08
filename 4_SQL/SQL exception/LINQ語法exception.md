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
#資訊 
# Unify




1. #flashcards 
- Highlight:
- Question:為何DataTable要用複合key都呈現紅字
?
- Answer:語法規範，DataTable AsEnumerable表達和陳述式都不能用複合key
```
on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }
```

2. #flashcards 
- Highlight:
- Question:匿名型別無法用陳述式JOIN
?
- Answer:語法規範

3. #flashcards 
- Highlight:EF操作
- Question:There is already an open DataReader associated with this Command which must be closed first?
?
- Answer:EF集合沒有用Extension讓其支援標準運算，ex:ToList() 

4. #flashcards 
- Highlight:建立一個DB參數集合與UI元件集合要將二者關聯後UI值填入參數
- Question:JOIN不出結果
?
- Answer:檢查後面是否有ToList之類實體化,因LINQ有**延遲效果**

5. #flashcards 
- Highlight:在調用自訂義RowCommand時其為一組string[]，將其
```
arr.Select(r => r[0])
```
- Question:產出結果很奇怪都為**數字**
?
- Answer:因為當在做單一string時會自動理解成
```
IEnumerable<char>
```
因此產出原本產出數字結果為字元

6. #flashcards 
- Highlight:
- Question:
?
- Answer:


