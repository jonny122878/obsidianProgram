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
Qty::10
#知識  #work 
# Unify
- MS-SQL **function**本身不丟exception,可以想像成是弱型別,異常丟出NULL
- typescript、javascript弱型別概念，reduce應為aggregate前身概念，因此必須自行寫MAX、MIN...，並且無自帶map特性
- typescript、MS-SQL對NULL認定在於是否默認0
- 基本上集合為空在任一種語言都會呈現錯誤

1. #flashcards 
- Highlight:MS-SQL
- Question:aggrgate function ex:MAX、MIN，若此集合為空則return?
?
- Answer:其aggreagte input型態會有多種,因此用萬用型態**NULL**表達

2. #flashcards 
- Highlight:新增資料進行防呆時要檢查目前此筆資料為第幾版號
- Question:在LINQ中使用WHERE後MAX丟出exception
?
- Answer:MAX本身並無防呆NULL情境，從**名稱直覺**並無FirstOrDefault

3. #flashcards 
- Highlight:AVG在不同數字型態return?
- Question:小數點會依據型態做進位
?
- Answer:int計算出來值就不可能有小數位數值 


5. #flashcards 
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

6. #flashcards 
- Highlight:LINQ調用Aggregate
- Question:exception序列內未包含項目
?
- Answer:集合內一定要含有元素

7. #flashcards 
- Highlight:LINQ
- Question:Aggregate加總運作是每個元素往前接合，但若是第一個元素?
?
- Answer:想成和空白串接 
  ```
  List<string> insertSQLTables = new List<string>();
  var insertSQLTable = insertSQLTables.Aggregate((cur, next) => cur + next);
  ```

8. #flashcards 
- Highlight:TypeScript
- Question:畫面上呈現Object
```
reduce((cur,next) => cur.prem + next.prem)
```
?
- Answer:其本身和一般直覺用法不同，並無自帶map

9. #flashcards 
- Highlight:TypeScript
- Question:本身沒有MAX函數，但可利用聚合概念達成
?
- Answer:
```
reduce((cur,next) => cur > next ? cur:next)
```

10. #flashcards 
- Highlight:TypeScript
- Question:reduce數字陣列內中含有null元素
?
- Answer:不會丟null,typescript會將null歸納成0

11. #flashcards 
- Highlight:
- Question:
?
- Answer:

