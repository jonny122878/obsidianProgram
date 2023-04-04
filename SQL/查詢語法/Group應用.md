
- [PIVOT運算子](https://dotblogs.com.tw/SteveLiu/2019/05/21/173803)
- 原理:原本為記錄格式,key-value,但要像報表式呈現右側為時間ex:1、2、3月...
,將value給group後決定投射幾個欄位
- As別名為必要
- 括弧分隔為必要
```
SELECT 要投射出來欄位
FROM() As m
PIVOT (
	SUM()
	FOR Group Column
	IN([],[],...)

) As pvt
```

#### ROW_NUMBER() Over (PARTITION by 商品 Order by 時間)

- 如何驗證表格欄位之間關係為1-1或1-M
- 利用COUNT底層原理,其為類似LINQ GROUP key - Enumerable關係,只是在將其Enumerable總計算出數字


