# Metadata
Qty::3
Review::
Restructure::relation

### Think


# Exception


1. #flashcards 
- Highlight:
- Question:Aggregate、Where、Order其Enumerable動作是數列內元素互相運算，3個衍生衝突
?
- Answer:
  - 元素值為null
	[[Enumerable Aggregate exception]]4.
	[[SQL Aggregate exception]]4.
  - 型態間精度不同比較
	[[SQL Aggregate exception]]2.
	[[Enumerable Where exception]]1.
	[[SQL Where exception]]2.
	- 預設值權重
	[[Enumerable Order exception]]3.
	[[SQL Order exception]]1.、3.、4.

2. #flashcards 
- Highlight:Aggregate、Order原生只有聚合效果，但已知2個語言會封裝映射動作和常用聚合效果、2個不會
- Question:
?
- Answer:
- typescript、javascript弱型別概念，因此為原生
	 [[Enumerable Aggregate exception]]3.、6.
	 [[Enumerable Order exception]]2.、4.
	 [[Enumerable Max exception]]2.
- LINQ、MS-SQL為有封裝過後
	[[Enumerable Order exception]]1.

3. #flashcards 
- Highlight:
- Question:Aggergate Enumerable本身為空，已知1種會丟exception、1種不會
?
- Answer:
- 丟exception:
	[[Enumerable Aggregate exception]]1.、5.
	[[Enumerable Max exception]]1.
	
- 不丟exception:
	[[SQL Aggregate exception]]1.、3.

4. #flashcards 
- Highlight:
- Question:述句語法糖2個衝突
?
- Answer:
- 函數:
	[[SQL Order exception]]2.
	[[SQL Select exception]]2.、3.
- 別名:
	[[SQL Order exception]]5.
	[[SQL Where exception]]3.
- 換行符
	[[SQL Select exception]]5.

5. #flashcards 
- Highlight:
- Question:Enumerable之間結合，衍生2個衝突
?
- Answer:
- 主表和副表決定
	[[SQL Join exception]]1.、2.、3.
- 元素之間重複處理
	[[SQL Union exception]]2.
- Enumerable有空情況
	[[SQL Union exception]]1.

6. #flashcards 
- Highlight:
- Question:Select其Enumerable動作是元素本身之間再次投射，衍生衝突
?
- Answer:
- 型態理解
	[[Enumerable Select exception]]1.、4.




- 







- MS-SQL **function**本身不丟exception,可以想像成是弱型別,異常丟出NULL
- typescript、MS-SQL對NULL認定在於是否默認0


- 集合再數列運算通常都會產生集合體之類概念，後續再轉成實際資料結構
- 集合在弱型別用符號表示
- 弱語言和Dapper投射預設為空情況
- C# string語法糖


- 日期和數字要特別小心精度比較理解和直覺不同

- 弱型別要特別小心無定義清楚物件屬性、return值

# Exception






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