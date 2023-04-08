---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:總結
Author:
Note Type:
Topics:


## 語言存在環境特性?
- 位置概念
```
USE[所在資料庫]
```
|PROCEDUCE|View|function|
|:--|:--|:--|
|計算用副程式,return 不能被override|為展現層非實際表格不能ORDER BY|遵循function**無副作用**,內部不能exec|
- 上述三種物件都和**table同位階** 符合異動結構時用create、alter
副程式應用選擇[[想要提煉function return一張表]]
在 SQL Server 中，View 本身是一個虛擬表格，是由一個或多個 SELECT 語句所組成的，而不是一個實際的表格。因此，View 中的資料是根據 SELECT 語句所定義的查詢結果產生的，而不是實際存在的資料。因此，在 View 中使用 ORDER BY 是沒有意義的，因為它不會改變 View 中的資料。

## 語言型別衝突呈現:如何declare?、exception所丟出?
#### 型態區分
- With這種**暫存變數**若有多個，ex:With name1 As(), name 2 As()
- select、insert 這些都是屬於**陳述式**,若要一起整個腳本執行以;為結尾
- 傳統變數
#### 日期型別
- 字串條件自動轉型，ex:
    - 20220415
    - 2022/04/15
    - 2022-04-15
#### 結構變數
- 宣告時類似VB語法，DECLARE name As xxx
- 要用@來修飾
- 寫入時前面要加set
- 若為表格類型的要用()包覆
- With內要as不能無資料行名稱
- With各區塊變數共通的
- With 內部必要命名，前若有更新指令；
- With 宣告變數若沒有用Declare用完就就釋放
- ex:[With串接,之後生命週期到陳述式就結束了](######with_ex)
#### 結構集合
- **資料表**來達到結構集合的特性
- As [特殊欄位名]
- Constraint default 預設欄位值
- As別名 不能用在其他主句ex:where order

## 變數、條件、迴圈、函式四大基礎所對應語法?
#### 廻圈
- 組成要素只有While搭配計數值與中斷值
- BEGIN END中間內包覆指令
ex:[SQL_Loop_example](######Loop_SQL_ex)
#### 條件
- BETWEEN AND是含**limit**範圍
- WHERE **column** BETWEEN **最小值含limit(相當於<=)** AND **最大值含limit(相當於>=)**
- ex:[BETWEEN-AND正負數比較](######BETWEEN_AND_SQL_ex)
- 傳統AND串接[[SQL條件短路寫法邏輯炸彈]]
#### 函數
- 與一般函數基本要件一樣參數、函數名、回傳值
- 較為不同回傳值類似python可有可無
- 資料表可掛觸發程序
- 去更新令張表
https://dotblogs.com.tw/ricochen/2011/06/23/29628



## 原生功能體現環境特性?
- SP_EXECUTESQL 預存程序
  - 組合字串陷阱[[PROCEDUCE字串組合]]
  
- INFORMATION_SCHEMA.COLUMNS 表格結構
ps:C:\\Programs_Note\\SQL\\






###### with_ex
- 在UPDATE陳述式結束後with變數生命週期就已結束
```
With wrnt_underlying_event_date As(
SELECT ROW_NUMBER() Over (PARTITION by wrnt_id ORDER BY event_date DESC) As seq,*
FROM wrnt_underlying
WHERE wrnt_id IN(
SELECT wrnt_id
FROM wrnt_underlying
WHERE event_date > @zDate
GROUP BY wrnt_id)
)
,wrnt_underlying_event_date_1 As (
SELECT * FROM wrnt_underlying_event_date WHERE seq = 1
)
UPDATE wrnt_underlying
SET event_date = @zDate
FROM wrnt_underlying M
INNER JOIN wrnt_underlying_event_date_1 U
ON M.wrnt_id = U.wrnt_id AND M.event_date = U.event_date;
UPDATE wrnt_exercise SET effective_date = @zDate 
FROM wrnt_exercise As M
INNER JOIN wrnt_exercise_effective_date_1 U
ON M.wrnt_id = U.wrnt_id AND M.effective_date = U.effective_date;
```


###### Loop_SQL_ex
- 宣告計數、總筆數、來源表
- 從來源表初始總筆數
- Loop內部要有計數指令，迴圈取得來源資訊
```
DECLARE @num_wrnt_exercise_event_date AS int;--計數
DECLARE @len_wrnt_exercise_event_date AS int;--總筆數
SET @num_wrnt_exercise_event_date  = 1;
--暫存表用來存要更新id,date
DECLARE @t_wrnt_exercise_event_date  table(
seq int,
wrnt_id varchar(20),
update_date datetime
);
SET @len_wrnt_exercise_event_date = (SELECT COUNT(*) FROM @t_wrnt_exercise_event_date);
WHILE @len_wrnt_exercise_event_date >= @num_wrnt_exercise_event_date
BEGIN
	update wrnt_exercise set event_date =@zDate where wrnt_id = (SELECT wrnt_id FROM @t_wrnt_exercise_event_date WHERE seq = @num_wrnt_exercise_event_date)
	and event_date=(SELECT event_date FROM @t_wrnt_exercise_event_date WHERE seq = @num_wrnt_exercise_event_date)

	SET @num_wrnt_exercise_event_date = @num_wrnt_exercise_event_date +1;
END
```
###### BETWEEN_AND_SQL_ex
```
WHEN 2.99 BETWEEN 2.00 AND 2.99 THEN 2 
小數點區間放反
WHEN -2.99 BETWEEN -2.99 AND -2.00 THEN 2 
```
