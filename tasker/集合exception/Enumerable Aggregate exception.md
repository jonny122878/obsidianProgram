# Metadata
Qty::7
Review::
Restructure::relation、summary

#work #資訊 
# Unify

## 本質

## 衍生衝突


# Exception

1. #flashcards 
- Highlight:LINQ,新增資料進行防呆時要檢查目前此筆資料為第幾版號
- Question:使用WHERE後MAX丟出exception
?
- Answer:MAX本身並無防呆NULL情境，從**名稱直覺**並無FirstOrDefault


2. #flashcards 
- Highlight:typescript
- Question:將數值˙相加為何用此寫法有問題?
```
reduce(r => r)
```
?
- Answer:類推方式錯誤，應為Aggregate寫法而不是Sum寫法
```
reduce((res,cur) => res + cur)
```

3. #flashcards 
- Highlight:LINQ調用Aggregate
- Question:exception序列內未包含項目
?
- Answer:集合內一定要含有元素

4. #flashcards 
- Highlight:LINQ
- Question:Aggregate加總運作是每個元素往前接合，但若是第一個元素?
?
- Answer:想成和空白串接 
  ```
  List<string> insertSQLTables = new List<string>();
  var insertSQLTable = insertSQLTables.Aggregate((cur, next) => cur + next);
  ```

5. #flashcards 
- Highlight:TypeScript
- Question:畫面上呈現Object
```
reduce((cur,next) => cur.prem + next.prem)
```
?
- Answer:其本身和一般直覺用法不同，並無自帶map

6. #flashcards 
- Highlight:TypeScript
- Question:本身沒有MAX函數，但可利用聚合概念達成
?
- Answer:
```
reduce((cur,next) => cur > next ? cur:next)
```

7. #flashcards 
- Highlight:TypeScript
- Question:reduce數字陣列內中含有null元素
?
- Answer:不會丟null,typescript會將null歸納成0

8. #flashcards 
- Highlight:
- Question:
?
- Answer: