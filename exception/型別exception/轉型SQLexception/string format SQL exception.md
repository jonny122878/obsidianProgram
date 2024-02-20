# Metadata
Qty::3
Review::
Restructure::relation 3

### Think

# Exception


1. #flashcards 
- Highlight:MS-SQL做PROCEDUCE計算
- Question:CASE WHEN對二個指定欄位做判別時若為二者空白與NULL均為一種情況，最後將呈現結果將二個欄位給相加
```
CASE ISNULL(,'') + '|' + ISNULL(,'') THEN 'Y'
ELSE 'N'
```
?
- Answer:欄位做串接Aggregate時，忽略default 符號中間串接符號，導致異常

2. #flashcards 
- Highlight:MS-SQL
- Question:當欄位為空字元調用SUBSTRING
?
- Answer:其都為字串,因此return **空字元**

3. #flashcards 
- Highlight:Oracle
- Question:ORA-01722: 無效的數字 
?
- Answer:
```
SELECT QUOTE_NO + ' ' + ID_NO FROM NC_QUOTE_INSURED //error 無語法糖
SELECT QUOTE_NO || ' ' || ID_NO FROM NC_QUOTE_INSURED
```
