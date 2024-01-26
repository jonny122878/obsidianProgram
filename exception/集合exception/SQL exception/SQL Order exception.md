# Metadata
Qty::5
Review::
Restructure::

### Think




- 型態是會決定順序權重，ex:數字
- javascript、typescript是透過接近數學方式呈現
- 各種語言都會有ThenBy概念



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
- Highlight:MS-SQL combobox DataSource來源為資料庫內表格,其中有一欄為數字用來決定item先後順序,其欄位為文字型態
- Question:發現有的項目排序在最前面
?
- Answer:**空字串**在文字順序權重比為最小

4. #flashcards 
- Highlight:MS-SQL combobox item呈現次序按照數字欄位去遞增
- Question:呈現結果並無照預期
?
- Answer:其數字欄位是**字串**型別，權重為1、10、11、2、3、4

5. #flashcards 
- Highlight:Oracle中進行主表JOIN副表取得資訊細節後ORDER BY
- Question:'ORA-00904: "BUSINESS_CD_NAME": 無效的 ID'
?
- Answer:檢查後發現ORDER BY述句並無此欄位名，值得一提可用**As別名**去調用
