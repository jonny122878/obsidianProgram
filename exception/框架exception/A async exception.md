# Metadata
Qty::3
Review::
Restructure::relation

### Think

# Exception


1. #flashcards 
- Highlight:ngOnChange先去db去載入設定檔轉成UI畫面之後,在去db撈存取資料填值
- Question:明明資料庫都有值,但沒有載入出資料
?
- Answer:不能將其寫不同個subscribe，因為非同步若撈取值先載入就無法填入

2. #flashcards
- Highlight:父module.ts做一個下拉選單全部來源，後續在透過注入到子module.ts
```
@Input() dropdownInitData: InitDropdownData;
```
- Question:為何明明後端API是有資料的，將方法搬子module.ts呼叫service也是有值，但透過父module.ts呼叫service無值
?
- Answer:**異步**觀念，每個component呼叫時間不盡相同，可透過setTimeout處理，但若此componenet是透過其他user trigger因其delay時間夠久並不受影響

3. #flashcards 
- Highlight:
- Question:click按鈕資料填入對話框,但資料尚未填入對話框就跳出
?
- Answer:click掛載函數是非同步情境

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