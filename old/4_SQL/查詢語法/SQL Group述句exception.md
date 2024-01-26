---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
#資訊 
# Unify




1. #flashcards 
- Highlight:結構為表頭和表身1-M關係，想要將表身資訊給結合成一個欄位與表頭共同呈現
- Question:for xml path('') 本身為轉換xml格式，為何可用來從1-M => 1-1
?
- Answer:
- 本質為1-M => 1-1 string，但其仍然透過XML標記將讓字串能區分集合元素，利用此特性進行重組串接
- 在將其放在衍生欄位，透過KEY配對即能達到效果
- 表身在整合1-1時，需用單頭KEY當欄位
```
SELECT FGBBAA002 FROM FGBBA GROUP BY FGBBA002 for xml path('')
=>
SELECT DISTINCT FGBAA002 + '|' FROM (
SELECT DISTINCT FGBBAA002 FROM FGBBA GROUP BY FGBBA002 
)a for xml path('')

SELECT FGBAA001 //此欄位必須為分組功能單頭KEY
,
SELECT FGBAA002 + '|' FROM (
SELECT DISTINCT FGBBAA002 FROM FGBBA 
WHERE ... //外表與內表KEY配對 
GROUP BY FGBBA002 
)a for xml path('')
FROM FGBBA
GROUP BY FGBBA002
```


2. #flashcards 
- Highlight:MS-SQL
- Question:如何驗證表格欄位之間關係為1-1或1-M
?
- Answer:利用COUNT底層原理,其為類似LINQ GROUP key - Enumerable關係,只是在將其Enumerable總計算出數字


3. #flashcards 
- Highlight:
- Question:[PIVOT運算子](https://dotblogs.com.tw/SteveLiu/2019/05/21/173803)
?
- Answer:
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


4. #flashcards 
- Highlight:
- Question:
?
- Answer:

