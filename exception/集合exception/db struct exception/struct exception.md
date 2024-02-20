# Metadata
Qty::5
Review::
Restructure::

### Think

# Exception


1. #flashcards 
- Highlight:
- Question:叢集索引(Clustered)使用時機?
?
- Answer:PK適用，因其是將資料實體存取結構做順序排序，其會修改資料存取實體結構，只能有一個

2. #flashcards 
- Highlight:
- Question:非叢集索引(Non Clustered)使用時機?
?
- Answer:FK、Where、Group、Order適用，它並不會影響實體資料存取排序，可以有多個

3. #flashcards 
- Highlight:
- Question:非叢集索引(Non Clustered)失效情境?
?
- Answer:where用like

4. #flashcards 
- Highlight:
- Question:如何透過結構設計提升效能
?
- Answer:
- 讀寫資料庫分離,在透過MS-SQL內建方式同步
- 讀寫分離設計讀取DB結構可以弄成非正規化減低JOIN，或是用View檢視表
- 針對user對特定資料讀多寫少狀況弄成cache,將讀多資料特別撈出來到List上,跟著Request消失,或是Thread定期更新

5. #flashcards 
- Highlight:
- Question:用List結構在後端運算非常緩慢
?
- Answer:
- 在記憶體中的 List 資料不似在資料庫中那樣，這些資料是分散且沒有 Key，當資料量有百萬筆以上，使用 foreach 這類的 loop 一筆筆比對，會執行到天荒地老。
- 轉換字典
  - 宣告Key的覆寫比較物件
  - 來源結構轉字典要注意重複Key的問題
  - 字典建構式要注意比較物件