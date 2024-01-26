# Metadata
Qty::3
Review::
Restructure::relation、summary

#work #資訊 
# Unify

## 本質

## 衍生衝突


- 相對位置理解



1. #flashcards 
- Highlight:撈取DOM table並用tr 一列列迴圈展開
- Question:為何明明遍歷語法還是抓到全部
```
for item in sources:
	item.xpath('/td[1]/')
```
?
- Answer:小心xpath上相對路徑，會去默認撈上一層

2. #flashcards 
- Highlight:
- Question:為何驗證表格列數量時丟出沒有此屬性
```
table.find_element(By.TAG_NAME,"tr")
```
?
- Answer:find_element and find_elements是不相同1個是撈出集合

3. #flashcards 
- Highlight:
- Question:invalid argument: invalid locator\n  (Session info: chrome=118.0.5993.120)
?
- Answer:找不到元素

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