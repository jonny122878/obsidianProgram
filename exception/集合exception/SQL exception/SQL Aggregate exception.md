# Metadata
Qty::4
Review::
Restructure::

### Think






# Exception

1. #flashcards 
- Highlight:MS-SQL
- Question:aggrgate function ex:MAX、MIN，若此集合為空則return?
?
- Answer:其aggreagte input型態會有多種,因此用萬用型態**NULL**表達

2. #flashcards 
- Highlight:MS-SQL,AVG在不同數字型態return?
- Question:小數點會依據型態做進位
?
- Answer:int計算出來值就不可能有小數位數值 

3. #flashcards 
- Highlight:Oracle
- Question:怎麼判別都是有重複資料
```
string strSql = @"select count(1)
             from NC_PROD_ADD_RATE_GOODS a
var arrResults = access.QueryList<int>(strSql, parm).ToArray();
if(arrResults.length != 0)
```
?
- Answer:直覺理解錯誤，用count聚合函數只要連線正常一定會有1筆，因此不應用變數列表數量判別

4. #flashcards 
- Highlight:Oracle、MS-SQL
- Question:SUM起來內含null,是否會弄成null
?
- Answer:null 自動忽略成0

