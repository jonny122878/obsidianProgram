# Metadata
Qty::2
Review::
Restructure::relation

### Think


# Exception

1. #flashcards 
- Highlight:MS-SQL
- Question:目前排程每日會透過PROCEDUCE將資料移轉,但隨著時間推移資料量越來越大,user希望能否只保留當月份,之前資料只保留月底最後一日即可,規劃PROCEDUCE計算將刪除的日期塞到暫存表,其他排程在調用此暫存表,但發現還沒調用到此暫存表就消失了...
?
- Answer:用符號來分隔
```
#為區域 ##為全域
```

2. #flashcards 
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


3. #flashcards 
- Highlight:
- Question:
?
- Answer:

4. #flashcards 
- Highlight:
- Question:
?
- Answer:

5. #flashcards 
- Highlight:
- Question:
?
- Answer: