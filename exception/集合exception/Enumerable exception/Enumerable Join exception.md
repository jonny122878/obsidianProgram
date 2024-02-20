# Metadata
Qty::5
Review::
Restructure::relation 1 2 4 5

### Think


# Exception


1. #flashcards 
- Highlight:LINQ
- Question:為何DataTable要用複合key都呈現紅字
?
- Answer:語法規範，DataTable AsEnumerable表達和陳述式都不能用複合key
```
on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }
```

2. #flashcards 
- Highlight:LINQ
- Question:匿名型別無法用陳述式JOIN
?
- Answer:語法規範

3. #flashcards 
- Highlight:建立一個DB參數集合與UI元件集合要將二者關聯後UI值填入參數
- Question:JOIN不出結果
?
- Answer:檢查後面是否有ToList之類實體化,因LINQ有**延遲效果**

4. #flashcards 
- Highlight:LINQ
- Question:陳述式left join中into含意?
?
- Answer:into為二張表交集所產出結果集合， 因此**多張表**就要有**多個into** 

5. #flashcards 
- Highlight:LINQ
- Question:DefaultIfEmpty()內參數都不放任何值
?
- Answer:default 產出一個Enumerable含有1個null element 