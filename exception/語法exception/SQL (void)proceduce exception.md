# Metadata
Qty::4
Review::
Restructure::relation

### Think

# Exception


1. #flashcards 
- Highlight:MS-SQL
- Question:人事系統資料定期將本地端資料給還原，如何提升效能
?
- Answer:
1.不需要去追蹤**異動資料行**時，可透過SET NOCOUNT ON 提升效能
2.backup要把原本資料都清除時，可透過**TRUNCATE TABLE**，其與DELETE區別也在於不追蹤**異動資料行**

2. #flashcards 
- Highlight:MS-SQL，PROCEDUCE去計算資料，因為資料庫名稱為變數，所以將多段SQL弄成string後去執行
- Question:EXECTE後一直出現exception
?
- Answer:string在組合時，良好習慣頭尾要加**空字元**，免於掉入 SELECTFROM 這類keyword無間隔情況組合內變數時，外部要在加字串修飾符
```
'' + @variant + ''
```


3. #flashcards 
- Highlight:MS-SQL
- Question:BEGIN TRANSACTION 接近END之處語法不正確
?
- Answer:TRANSCATION本身也有**區塊修飾子**特性，因此無須特別在用BEGIN END區塊，且用COMMIT、ROLLBACK此種也有**區塊修飾子**特性結尾
false
```
BEGIN TRANSCATION
END
```
true
```
BEGIN TRANSCATION

IF @@ERROR = 0
BEGIN
	COMMIT;
END
ELSE
	ROLLBACK;
END

```


4. #flashcards 
- Highlight:MS-SQL，目前排程每日會透過PROCEDUCE將資料移轉,但隨著時間推移資料量越來越大,user希望能否只保留當月份,之前資料只保留月底最後一日即可
- Question:所有透過PROCEDUCE透過排程每日計算出來結果表都符合此規則,因此想封裝副程式,直覺想到PROCEDUCE、Function、exec SELECT語法再用FROM去接收
?
- Answer:PROCEDUCE本身定位可想成是計算函數,因此return int的只是負責呈現**計算結果狀態**
exec本身內建PROCEDUCE也帶有同樣特性,function因其特性不能再調用PROCEDUCE,但需求是SELECT語法要組成字串丟入exec也沒辦法
解決方法改成用暫存表,資料連線斷開就隨之消失

5. #flashcards 
- Highlight:
- Question:
?
- Answer: