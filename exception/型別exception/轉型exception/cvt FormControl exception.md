# Metadata
Qty::5
Review::
Restructure::relation 3

### Think







# Exception

1. #flashcards 
- Highlight:
- Question:在checkbox、radioButton呈現null、0、1會發生那些現象
?
- Answer:
- checkbox因為本身二元性，null和0都為不勾選
- radioButton則因其必要選特性，null表示都初始都無勾選狀態

2. #flashcards 
- Highlight:
- Question:checkbox、radioButton吃入數字型別讀出來到model會呈現型別?
?
- Answer:checkbox轉bool，radioButton遵循其他UI通用規則都是string

3. #flashcards 
- Highlight:
- Question:考量到null，但還是出錯
```
setValue:'q3': this.mainData.question.q03?.toString() 
```
?
- Answer:setValue每個元件都要設定值，遺漏null情況無填值
```
'q3': this.mainData.question.q03?.toString() || null,
```

4. #flashcards 
- Highlight:DropDownList需放一個default請選擇選項
- Question:該如何在html樣版上設定selected
?
- Answer:只需value設定null即可，其預設ORDER BY最前面
```
SelectItemModel = {value:null,text:'請選擇',title:''}
```
5. #flashcards 
- Highlight:combobox來源為數字型態
- Question:確認FormGroup有註冊，但載入發現combobox並未填值
?
- Answer:combobox內顯值為數字，但綁定呈現時需轉成string


6. #flashcards 
- Highlight:
- Question:
?
- Answer: