### 計算前幾季平均,補缺失值
- 將時間的基本檔撈取出
- 將商品基本檔撈取出
- 時間和商品CROSS JOIN出主表
- 主表再去LEFT JOIN消除NULL值
- ROW_NUMBER()弄出order scale欄位，支援前幾、後幾平均

union,except之類列結合特性以主表為主**移除重複**
### [UPDATE JOIN](######UPDATE_JOIN_ex)
- 也要有FROM As別名
- INNER JOIN內不能有子查詢,需用With
### [集合間差異比較](######EXCEPT_example)


###### EXCEPT_example
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


###### UPDATE_JOIN_ex

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
```
