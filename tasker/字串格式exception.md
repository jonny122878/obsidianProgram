---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::10

#知識  #work 

# Unify
- typescript replace參數彈性很大包含Reg、lambda
- string array結合通常都有內建函數
- string 通常都有截斷、分割成陣列函數

1. #flashcards 
- Highlight:C#
- Question:Split:做字串分割目標物若在字尾最後字元,會產出幾個陣列?
?
- Answer:分割目標會被吃掉後產出2個元素陣列，不是~~1個元素陣列~~
  ```
  var file = @"D:\test\test.txtz";
  var split = file.Split('z');
  ```
  

2. #flashcards 
- Highlight:typescript
- Question:replace string 能否FIRE_AP_COMMI => fireApCommi
?
- Answer:Reg搭配lambda
```
const replacedString = originalString.replace(/[A-Z]/g, (match) => match.toLowerCase());
```

3. #flashcards 
- Highlight:C#
- Question:變數使用.ToString()丟出exception?
?
- Answer:要先將object給強型別


4. #flashcards 
- Highlight:C#
- Question:字串要防呆時要同時兼顧空字元與null，需要自行寫函式?
?
- Answer:內建string.IsNullOrEmpty


5. #flashcards 
- Highlight:C#
- Question:陣列要組合成字串，ex:insert SQL指令，不用Aggregate下?
?
- Answer:可透過string.Join，省去了移除最後字元和元素間要加入分隔
  ```
  var arr = new List<string> {"a","b","c" };
  var value = string.Join("-", arr);
  ```

6. #flashcards 
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



7. #flashcards 
- Highlight:C#
- Question:Split:分離出來有無內建參數過濾空字串
?
- Answer:有
  ```
    var splits = afrRoad.Split(new char[] { '號', '之', '樓',' ' }, StringSplitOptions.RemoveEmptyEntries);
    ```


8. #flashcards 
- Highlight:C#
- Question:SubString(8)截斷結果?
?
- Answer:從第8字元**順序開始**截斷,~~從順序0字元開始取8個字元~~


9. #flashcards 
- Highlight:C#
- Question:string String.Empty大小寫區別?
?
- Answer:實作上無區別，都是把null給填值

11. #flashcards 
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


10. #flashcards 
- Highlight:C#
- Question:字串轉其他字元
?
- Answer:
  - 中字UTF8:byte佔3個
  - 中字ANSI:byte佔2個
```
string str = "test對";
var bytes = Encoding.UTF8.GetBytes(str);
var charArr = Encoding.UTF8.GetChars(bytes);
var encode = Convert.ToInt32(charArr[4]);
```


10. #flashcards 
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


11. #flashcards 
- Highlight:C#，excel字串用replace函數替換對應名目尺度(ex:條件式取代字串:sample:31-十一月-2018)
- Question:取代出只符合一半情況
?
- Answer:
  - 條件式的守則是從**嚴謹到寬鬆**，不然就會有擋下來沒有達到預期的效果，順序搭配鬆緊非常重要，就是成敗的關鍵。
  - 可是你如果從一月取代到十二月時就會出錯，因為一月會先把十一月的後二字給取代掉，從而導致無法預期的結果。

12. #flashcards 
- Highlight:
- Question:
?
- Answer:


