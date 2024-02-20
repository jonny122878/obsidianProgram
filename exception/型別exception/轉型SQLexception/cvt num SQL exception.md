# Metadata
Qty::5
Review::
Restructure::

### Think


1. #flashcards 
- Highlight:MS-SQL
- Question:INSERT INTO SQL丟出轉換numeric、int到資料類型numeric時發生**算數溢位**錯誤
?
- Answer:
numeric規範:
   - 了解小數位數,ex:numeric(6,4)表示最少要保留四位小數位數
   - 183.481 因小數位數保留4位 complier翻成183.4810 exception
   - 因此推算**整數**位只能是2位
   - 確保讓使用者輸入長度也要有限制
int規範:
   - 在INSERT語法上8 是會exception
   - 8.0 表示有小數位

2. #flashcards 
- Highlight:MS-SQL、Oracle
- Question:INSERT SQL時丟出此訊息,明明在AP時有將流水號欄位**塞入數值**且**無重複**，但位於資料表 'TableName' 的識別欄位其外顯值只有當使用了資料行清單且 IDENTITY_INSERT 為 ON 時才能指定。
?
- Answer:流水號可以將其想成是**int型態加上規則**,因此型態定義上已是另種型態,不能塞值
	insert語句變成要指定欄位，避免因為流水號欄位為空產生ORA-00936: 遺漏表示式
```
INSERT INTO NC_ZIP_TOWN (NC_ZIP_CITY_ID,ZIP_CODE,TOWN_NAME,CREATED_DATE,CREATED_USER,UPDATED_DATE,UPDATED_USER)
VALUES(127,'t1','t',SYSDATE,'cUser',SYSDATE,'uUser')
```

3. #flashcards 
- Highlight:MS-SQL
- Question:明明想要計算%數,但產出結果確是四捨五入小數
```
SELECT 1/6
```
?
- Answer:型態定義可透過字面上,因此再後面加**小數位**數即可
```
SELECT 1.00 / 6.00
```

4. #flashcards 
- Highlight:Oracle，用Dapper操作DB，資料庫遞增值流水號欄位設定塞0
- Question:丟出:{"ORA-00001: 違反必須為唯一的限制條件 (FIRE_MSIG_USER.PK_PROD_POLICY_CLAUSE)
?
- Answer:若確認塞0那此種情況就是資料表結構有異動過，將原本**表格資料**都清除即可

5. #flashcards 
- Highlight:MS-SQL
- Question:四捨五入、無條件進位、無條件捨去
?
- Answer:
```
SELECT FLOOR(4.9)
SELECT CEILING(3.05)
SELECT ROUND(3.4,0)
```




5. #flashcards 
- Highlight:
- Question:
?
- Answer:


