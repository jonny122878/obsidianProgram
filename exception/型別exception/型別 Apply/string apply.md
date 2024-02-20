# Metadata
Qty::
Review::
Restructure::relation

### Think

# Exception


6. #flashcards 
- Highlight:C#
- Question:字串找字母位置
?
- Answer:
|指令|遍歷方向|是否複數目標|
|:---|:---|:---|
|IndexOf|前|N|
|IndexOfAny|前|Y|
|LastIndexOf|後|N|
|LastIndexOfAny|後|Y|

4. #flashcards 
- Highlight:C#
- Question:數字轉各種格式
?
- Answer:
- 再做格式運算若有小數點會四捨五入
|值|顯示|ex|
|:---|:---|:---|
|N0|千分位|1,285|
|0.00|小數2位|2.83|
|千分位含小數2位|#,##0.00|1,286.11|

2. #flashcards 
- Highlight:C#
- Question:Split:分離出來有無內建參數過濾空字串
?
- Answer:有
  ```
    var splits = afrRoad.Split(new char[] { '號', '之', '樓',' ' }, StringSplitOptions.RemoveEmptyEntries);
    ```

3. #flashcards 
- Highlight:javascript
- Question:做到類似C# array join function
?
- Answer:調用方法類似
```
let td = ['<tr>',
'<td class="blue">',
$(e).find('name').text(),
'</td>',
'<td class="green">',
$(e).find('ename').text(),
'</td>',
'</tr>'].join("\n");
```

4. #flashcards 
- Highlight:C#
- Question:陣列要組合成字串，ex:insert SQL指令，不用Aggregate下?
?
- Answer:可透過string.Join，省去了移除最後字元和元素間要加入分隔
  ```
  var arr = new List<string> {"a","b","c" };
  var value = string.Join("-", arr);
  ```

1. #flashcards 
- Highlight:typescript
- Question:replace string 能否FIRE_AP_COMMI => fireApCommi
?
- Answer:Reg搭配lambda
```
const replacedString = originalString.replace(/[A-Z]/g, (match) => match.toLowerCase());
```

4. #flashcards 
- Highlight:C#
- Question:字串要防呆時要同時兼顧空字元與null，需要自行寫函式?
?
- Answer:內建string.IsNullOrEmpty