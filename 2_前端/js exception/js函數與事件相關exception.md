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
#資料 
# Unify



1. #flashcards 
- Highlight:javascript
- Question:是否能將千分位字串直接轉型parseInt
?
- Answer:會截斷轉型30,000,000 => 30

2. #flashcards 
- Highlight:
- Question:Uncaught **TypeError**:object Array is not a function
?
- Answer:函式理解調用錯誤,dataArr.filter(dataArr,function(e){})

3. #flashcards 
- Highlight:調用keyborad event發現二者都能指定不會exception
- Question:指定event掛載時,onchange = function() { },與 = function(e){ }差異
?
- Answer:想為**函式多載**情況，當有參數時可針對其對應作掛載event作判別，ex:keyborad系列參數就是 keycode

4. #flashcards 
- Highlight:Array對集合調用方法
- Question:psuh、shift、pop、unshift差異,pop無資料情況
?
- Answer:附加索引順序上,push常用理解就是附加在尾端,**unshift反之**，非直覺shift，pop無資料不會丟exception，像foreach一樣直接跳開

5. #flashcards 
- Highlight:click textbox時為彈出calendar元件,使用者只能透過此方式輸入,不能透過用手keyin方式
- Question:讓使用者再此輸入框不能輸入任何值，該使用keypress、keyup、keydown何者?
?
- Answer:因完全不能調用鍵盤,按照此上述3 event特性,選keyup(因其為鍵盤event順序最後並且其為最新輸入值)

6. #flashcards 
- Highlight:
- Question:做addEventListener掛載時,常常忘記如何調用
?
- Answer:js特性弱型別語言,本身就有函式當參數傳，調用本身是**方法**,第二個參數為**函式**

7. #flashcards 
- Highlight:
- Question:在調用replace時是否能像理解C# replace
?
- Answer:JavaScript的replace()函數默認是**不區分大小寫**的。如果您需要在JavaScript中區分大小寫，可以使用**正則**表達式來實現，其他相關規則也通用
類似用C# replace全字串取代
```
replace(/,/g, '')
```

1. #flashcards 
- Highlight:內建日期函數理解錯誤
- Question:獲取當前月份，用getMonth但是其得到值為當前月份-1
?
- Answer:其內部邏輯為**array**，因此索引從0開始計數

9. #flashcards 
- Highlight:ASP.NET宣染檔案
- Question:preventDefault()調用無效果
?
- Answer:要先確保Console無錯誤是正常的，若js封裝ascx IDE exception是找不出行數

10. #flashcards 
- Highlight:
- Question:調用有參數function,參數都是undefined
?
- Answer:弱型別特性,因此都要用convert做類似宣告動作

9. #flashcards 
- Highlight:
- Question:
?
- Answer:



- 疑惑點:自定義物件equal無效果
- 情境:
- 判別:類似LINQ一般,要自訂比較override



# limit
## 特性
## 分隔符
## 型別(含轉型)
- js操作DOM為何無作用?
  - script本身也是有作用域概念，操作的DOM要放前面表示有宣告能操作
  ```
  <body>
  DOM.....  
  </body>
  <script></script>
  ```
  - script放置位置結論:
  - 放在head內為所需**副程式** ex:jQuery
  - 放置在body後為**操作DOM**且**不用event**
- 當字串和數字做運算，不丟exception會如何產出?
    - 型別之間不會有exception情況，而是由產出結果代替
    - ex:1/0 => infinity
    - ex:"test" +2 => NaN 
## 變數
## 結構集合
- 如何選取陣列內字典?
  - 與C#相同邏輯
  ```
  let gridFlg = (result[0].DEL_FLG) ? '是':'否';
  ```
## 廻圈
## 條件
- 不同型別之間是可以比較並無exception產出結果為?
  - ex:7 > "test" => NaN
- 字串做大小比較為何無異常?
  - 按照字母順序做比較基準，如果超過一個字元用字元順序開始比較
  - "a" > "b" => false
  - "test" > "tesz" => false
- 字串比較為何無作用?
  - string比較要用單引號、===
  ```
  let firstIdx = models.findIndex(function(e){return e.Email === 'test0906568135@gmail.com' });
  ```
