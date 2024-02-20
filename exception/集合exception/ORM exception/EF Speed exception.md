# Metadata
Qty::3
Review::
Restructure::

### Think

# Exception


1. #flashcards 
- Highlight:C#、EF
- Question:將資料讀出後,發現EF物件並無將關聯class讀出
?
- Answer:將其想成關聯式資料庫若要讀多張表要用Include
二張資料表之間可透過建立ICollection屬性去做連結撈取，進而先將二張實體表載入，提升撈取效能

2. #flashcards 
- Highlight:
- Question:存檔特別慢
?
- Answer:SaveChange 本身是帶有Tran，因此全部異動完調用一次即可

3. #flashcards 
- Highlight:
- Question:撈取特別慢
?
- Answer:
- 只實體化一次，展開時機為最後呈現ex:View和File，延伸可透過Repo封裝
- 當讀取資料不做任何異動時,可用AsNoTracking

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
