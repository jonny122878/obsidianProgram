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
- Highlight:MS-SQL中PROCEDUCE計算資料增加一個流水號欄位，日期+類別+筆數數量
- Question:按照推理每組序號應為獨一無二，為何會產出序號重複情況
?
- Answer:因序號編碼規則中間有含類別此二位數字編碼，ORDER按照**數字大小**

2. #flashcards 
- Highlight:MS-SQL
- Question:Order陳述式內是否可放置函數?
?
- Answer:可

3. #flashcards 
- Highlight:原本附件檔案會分別存放在三個路徑中其中一個路徑，需求是要將目前所存放檔案給移轉到另個位置
- Question:分析解法是透過LINQ GROUP BY以檔案為Key，路徑為Enumerable，透過此方式ORDER BY用檔案是否存在bool當條件，取最前面的，產出不如預期
?
- Answer:直覺true > false，但實際false > true

4. #flashcards 
- Highlight:combobox DataSource來源為資料庫內表格,其中有一欄為數字用來決定item先後順序,其欄位為文字型態
- Question:發現有的項目排序在最前面
?
- Answer:**空字串**在文字順序權重比為最小

5. #flashcards 
- Highlight:combobox item呈現次序按照數字欄位去遞增
- Question:呈現結果並無照預期
?
- Answer:其數字欄位是**字串**型別，權重為1、10、11、2、3、4

6. #flashcards 
- Highlight:
- Question:
?
- Answer:
