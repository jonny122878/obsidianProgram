# Metadata
Qty::8
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突


# Exception


1. #flashcards 
- Highlight:Oracle調用Select語句
- Question:Oracle中Select述句表格名稱有null?
```
from FUN_GET_INS(null) 
```
?
- Answer:Oracle中調用函數語法可以和撈取表格相同，null表示參數

2. #flashcards 
- Highlight:MS-SQL撰寫預存程序挖空參數
- Question:當SQL要改成用string取組合時,單引號exception
?
- Answer:'''' + 'string' + '''' ,等於**單引號特殊符**區別''''

3. #flashcards 
- Highlight:MS-SQL撰寫預存程序要將計算表格放入變數
- Question:除非同時指定了TOP、OFFSET或FOR XML，否則ORDER BY在檢視表、內建函式、衍生資料表、子查詢及通用資料表運算式中均為無效
?
- Answer:可用直覺式思考，因ORDER BY主功能為投射給使用者呈現，若在上述情境等於耗效能而無任何成果

4. #flashcards 
- Highlight:MS-SQL
- Question:PROCEDUCE與FUNCTION如何調用
?
- Answer:PROCEDUCE與FUNCTION本質相同,差異再於調用方式FUNCTION可下SQL語句內
```
SELECT column FROM Function('paramter')  
```

5. #flashcards 
- Highlight:MS-SQL撰寫函數
- Question:丟出訊息:在函式中使用副作用運算子,'INSERT EXEC' 無效
?
- Answer:函式本身只能是純函式,不能有**副作用**，ex:調用預存程序修改其他表

6. #flashcards 
- Highlight:MS-SQL撰寫預存程序
- Question:丟出訊息:在有預期條件內容指定非布林運算式,接近BEGIN
?
- Answer:IF條件式沒寫好，在MS-SQL為成對式
```
IF 
BEGIN
END
```

7. #flashcards 
- Highlight:MS-SQL
- Question:目前排程每日會透過PROCEDUCE將資料移轉,但隨著時間推移資料量越來越大,user希望能否只保留當月份,之前資料只保留月底最後一日即可,規劃PROCEDUCE計算將刪除的日期塞到暫存表,其他排程在調用此暫存表,但發現還沒調用到此暫存表就消失了...
?
- Answer:用符號來分隔
```
#為區域 ##為全域
```


8. #flashcards 
- Highlight:Oracle
- Question:能否透過類似下方指令產生暫存表
```
SELECT * INTO FROM
```
?
- Answer:要特別注意連線斷開生命週期還在
```
CREATE TABLE temp_table AS
SELECT NC_POLICY_ATTACH_FILE_ID
FROM NC_POLICY_ATTACH_FILE
```
