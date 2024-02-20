# Metadata
Qty::6
Review::
Restructure::relation 2

### Think


# Exception



1. #flashcards 
- Highlight:LINQ調用Aggregate
- Question:exception序列內未包含項目
?
- Answer:集合內一定要含有元素

2. #flashcards 
- Highlight:LINQ
- Question:Aggregate加總運作是每個元素往前接合，但若是第一個元素?
?
- Answer:想成和空白串接 
  ```
  List<string> insertSQLTables = new List<string>();
  var insertSQLTable = insertSQLTables.Aggregate((cur, next) => cur + next);
  ```

3. #flashcards 
- Highlight:TypeScript
- Question:畫面上呈現Object
```
reduce((cur,next) => cur.prem + next.prem)
```
?
- Answer:其本身和一般直覺用法不同，並無自帶map

4. #flashcards 
- Highlight:TypeScript
- Question:reduce數字陣列內中含有null元素
?
- Answer:不會丟null,typescript會將null歸納成0

5. #flashcards 
- Highlight:typescript
```
[].reduce((cur,next) => cur + next)
```
- Question:Uncaught TypeError TypeError: Reduce of empty array with no initial value
?
- Answer:集合內一定要含有元素

6. #flashcards 
- Highlight:typescript
- Question:將數值˙相加為何用此寫法有問題?
```
reduce(r => r)
```
?
- Answer:類推方式錯誤，無自行映射應為Aggregate寫法而不是Sum寫法
```
reduce((res,cur) => res + cur)
```