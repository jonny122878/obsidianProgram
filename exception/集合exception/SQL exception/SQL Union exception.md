# Metadata
Qty::4
Review::
Restructure::

### Think

# Exception


1. #flashcards 
- Highlight:MS-SQL，在產生Report時將資料UNION整併成各類型項目後呈現
ex: 
```
SELECT '' As 別名
UNION ALL
SELECT '' As 別名
```
- Question:有時會丟出numeric型別錯誤
?
- Answer:情況為需要確保每個子資料集都需要有資料，若其中一個子資料集無資料就會呈現此情況

2. #flashcards 
- Highlight:MS-SQL
- Question:UNION產出資料不如預期?
?
- Answer:
  - 檢查再做接合時SELECT FROM後面不要有其他關鍵字
  - 檢查接合表格是否有重複資料

3. #flashcards 
- Highlight:
- Question:EXCEPT 和所期望不同
?
- Answer:主表為主**移除重複**
```
With std As(
SELECT PRODUCT_ID 
FROM [OSC_BIS].[dbo].[REP_FIXEDINCOME_DEP_BondRating_Compare] 
WHERE POSITIONDATE = '20220317' AND Bloomberg_Credit_Rating <> '無資料對應'
GROUP BY PRODUCT_ID),
cmp As (
SELECT [BOND_ID] 
FROM [OSC_REPORT].[dbo].[REP_FIXEDINCOME_DEP]
WHERE POSITIONDATE='20220317' and [NOMINAL_AMOUNT]!= 0 and product_id in ('04','07','08','13')
GROUP BY [BOND_ID]

)
SELECT * FROM std
EXCEPT
SELECT * FROM cmp
```

4. #flashcards 
- Highlight:
- Question:
?
- Answer: