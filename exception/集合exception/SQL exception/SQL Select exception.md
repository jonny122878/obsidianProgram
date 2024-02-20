# Metadata
Qty::5
Review::
Restructure::

### Think




# Exception


1. #flashcards 
- Highlight:AP表格在user剛載入時希望只有表頭,表身無資料
- Question:SELECT '' As,'' As 為了讓gridview撈出有標題,不進行 FROM實體表格撈取
?
- Answer:.直覺下是沒有撈出任何東西,但實際logic其實為1筆,SQL本身有聚合特性[[SQL抽象查詢]]

2. #flashcards 
- Highlight:MS-SQL
- Question:資料行 '...' 在選取清單中無效，因為它並未包含在彙總函式或 GROUP BY 子句中?
?
- Answer:因SQL Group無帶有投射性質，需注意Select與Group陳述式欄位數量一致 

3. #flashcards 
- Highlight:MS-SQL
- Question:若要分組有依據日期年度但欄位為日期型態有辦法放在Group陳述內?
?
- Answer:因日期函數return為單一值因此放此處不影響

4. #flashcards 
- Highlight:MS-SQL
- Question:Select中WHERE陳述式放在子查詢,與放在JOIN外層差異?
?
- Answer:放在外層是已經產生JOIN結果在WHERE過濾,二者看起來相同,但實際執行會有數量不同情況

5. #flashcards 
- Highlight:Oracle
- Question:'ORA-00933: SQL 命令的結束有問題' 
```
select PKG_PREM_GET_NO.FUN_GET_SER_NO('B',sysdate) As quoteSerNo from dual
```
?
- Answer:Oracle Developer撈取時和MS-SQL不同無語法糖，再撈一張以上SQL述句時須加;
Dapper中SQL子句結尾不能加;
