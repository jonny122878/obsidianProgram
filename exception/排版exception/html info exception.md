# Metadata
Qty::7
Review::
Restructure::

### Think





1. #flashcards 
- Highlight:在Angular中迴圈滾出來radioButton過於接近，無任何間距
- Question:為何在中間插入空白符無效情況
?
- Answer:在html中空白符為特殊符號

```
&nbsp;
```

2. #flashcards 
- Highlight:user點擊送出鈕後要將按鈕區塊給hidden避免重複發送
- Question:**後端**直覺Visible，但似乎不是所有標籤都有此屬性
?
- Answer:透過css中display=none

3. #flashcards 
- Highlight:實作表格
- Question:table切版在呈現時希望有的儲存格做合併情況
?
- Answer:在td屬性加入指令如下

|css|效果|
|:---:|:---:|
|rowspan|往上下合併|
|colspan|往左右合併|
4. #flashcards 
- Highlight:實作表格因td位置有大有小,而去設定width絕對尺度
- Question:tr本身是按照內部有幾個td去平均分佈所佔位置，但若用width**絕對**尺度,每個td加總tr不盡相同，**常理推論**不可能一個tr2000,一個1000,變成表格不在是方形情況
?
- Answer:當表格列有衝突時會用tr**最大值**為基準

5. #flashcards 
- Highlight:實作表格
- Question:用width**絕對**尺度內部td給調寬但是沒有如預期將其撐開
?
- Answer:使用width絕對屬性,其邏輯上不可能會超出所在**容器寬度**情況

6. #flashcards 
- Highlight:
- Question:切版中畫一條線該選擇何者元素
?
- Answer:hr

7. #flashcards 
- Highlight:
- Question:想在標題前面加入紅字標示符號與文字靠右
?
- Answer:
- 文字靠右是整個都要套用,因此加在td
- 標示符號紅字只有標示符號自身,因此在用span行內容器在包一層