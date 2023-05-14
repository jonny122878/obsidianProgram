---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
3.再調用keyborad event發現二者都能指定不會exception
# Question:
1.調用function some時做防呆時不管甚麼情境都是return false
2.Uncaught **TypeError**:object Array is not a function
3.再指定event掛載時,onchange = function() { },與 = function(e){ }差異
# Answer:
1.語法遺漏return ....，導致都為default
2.函式理解調用錯誤,dataArr.filter(dataArr,function(e){})
3.
- 可以想像其為函式多載exception情況
- 當有參數時可針對其對應作掛載event作判別，ex:keyborad系列參數就是 keycode





- 疑惑點:想要讓使用者再此輸入框不能輸入任何值，該使用keypress、keyup、keydown何者?
- 情境:click textbox時為彈出calendar元件,使用者只能透過此方式輸入,不能透過用手keyin方式
- 判別:此特性描述,因完全不能調用鍵盤,按照此上述3 event特性,選keyup(因其為鍵盤event順序最後並且其為最新輸入值)


- 疑惑點:
- 情境:再做addEventListener掛載時,常常忘記如何調用
- 判別:
  - js特性弱型別語言,本身就有函式當參數傳
  - 調用時本身是**方法**,第二個參數為**函式**

- 疑惑點:
- 情境:再做foreach用lambda語法無法調用
- 判別:
  - js特性弱型別語言,就像再調用其它集合一樣,它再foreach時就有迭代器構造
  - 然後用再用function(item,index)去override每個元素要做的事

- 疑惑點:psuh、shift、pop、unshift差異,pop無資料情況
- 情境:再調用Array上
- 判別:再附加索引順序上,push常用理解就是附加在尾端,shift反之

- 疑惑點:pop無資料情況
- 情境:
- 判別:直接跳開,就像是foreach一樣無須特別防呆

- 疑惑點:調用有參數function,參數都是undefined
- 情境:
- 判別:弱型別特性,因此都要用convert做類似宣告動作

- 疑惑點:條件式防呆if(result == NaN)無效果
- 情境:
- 判別:NaN、undefined這種其實不算是型別,而是型別中limit狀態,像是資料庫中NULL一樣,NaN是number型別,undefined為null型別

- 疑惑點:條件式防呆if(arr== [])無效果
- 情境:
- 判別:集合判別應是用集合方法操作

- 疑惑點:自定義物件equal無效果
- 情境:
- 判別:類似LINQ一般,要自訂比較override


- 疑惑點:preventDefault(),Number equal 0 exception
- 情境:Function statement requires a name
- 判別:
  - 要先確保DOM無錯誤是正常的
  - 若js寫在ascx問題IDE exception是找不出行數

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
