# Metadata
Qty::4
Review::
Restructure::relation

### Think

# Exception


1. #flashcards 
- Highlight:
- Question:原本class屬性對應html模塊textbox為數字，但textbox輸入值後屬性讀出為文字
?
- Answer:若不需要特別格式，可用html標籤解決
```
<input type="number"
```

2. #flashcards 
- Highlight:
- Question:FormControl確定有填值,value也有綁定但畫面顯示上無值
?
- Answer:html css radio radio-inline

3. #flashcards 
- Highlight:typescript
- Question:檢查小數3位和正整數,但明明測試無問題,實際上1.此種情況無法防呆
```
/(^\d+$|^\d+\.\d{1,3}$)/
```
?
- Answer:檢查文字框是否type為number,會自動轉型成1
- 1-1 轉成null

4. #flashcards 
- Highlight:表單為編輯狀態
- Question:屬性readonly、disabled該如何選擇?
?
- Answer:readonly不能有keyborad event,但是可以**focus與copy**

5. #flashcards 
- Highlight:
- Question:
?
- Answer: