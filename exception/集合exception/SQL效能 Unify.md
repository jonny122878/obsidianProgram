# Metadata
Qty::
Review::
Restructure::relation

### Think

# Exception


1. #flashcards 
- Highlight:
- Question:效能問題可從3個面向著手
?
- Answer:
- 調用有問題
	[[struct exception]]3.
	[[EF Speed exception]]1.、2.、3.
- 既有結構調整
	[[struct exception]]1.、2.
- 整體架構調整
	[[struct exception]]4.

2. #flashcards 
- Highlight:
- Question:
?
- Answer:

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
# Summary
提升效能思路:擅用Index，不因**不良SQL讓Index**無作用，以及關閉類似log不是主功能資訊
#### Index
- 大量INSERT時關閉索引
- BATCH INSERT
- BULK INSERT
- 型別上檢查ntext查詢會遠小於nvarcahr(max)

#### 關閉資訊
- [[PROCEDUCE備份資料效能問題]]

#### 系統設計

#### AP操作
- [[EF Speed exception]]

# Note
