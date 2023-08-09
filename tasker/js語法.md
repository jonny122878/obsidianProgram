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
#知識 #work 

# Unify
- 簡化DOM操作用jQuery，弱型別Debug用TypeScript
- 變數型別右側值，集合類型右側符號決定
- 特別小心var特有hoisting現象
- 起手式要特別針對型別防呆，並且其變數型別會跟著右側指定值變換

# 語言存在環境特性?
## 環境
整個網頁背後是透過window物件去控制,在再透過inherit將其區分為Console,Document這子物件
因此指令種類區分:
- window(基礎功能:ex:網址、初始化跳轉位置)
- document(平常最常用到,使用者互動,依附在[[js DOM]]下)
  -  後來推出語法精簡操作DOM[[jQuery語法]]
- 語言自身
  - 解決弱型別難以Debug[[TypeScript語法]]
## 調用特別注意bug
###### Debug要有這基本認知
- 純弱型別語言，可動態重複指定**override原本型別**
- 型別指定鬆散可以累加
	ex:變數declare Array 再指定其atttribute (類似強型別指定class)
###### 撰寫起手式
- 因其為弱型別不會exception,再起手式必定要防呆時需多考慮**各種exception型別**
	ex:像是若要防呆集合類型在jQuery可用 $.isArray
- [10小技巧](https://medium.com/i-am-mike/10%E5%80%8B%E6%96%B0%E6%89%8B%E5%BF%85%E7%9F%A5%E7%9A%84-javascrip-%E5%AF%A6%E7%94%A8%E6%8A%80%E5%B7%A7-75b55d7c3e47)
	
## 未知思路
function first 表示語言最小單位為**function**,(未知語法調用時參數傳function就對了)

# 型別機制
## 轉型衝突
因純弱型別語言是透過型別替代exception，因此除了null之外還有其他表示狀態型別
- NaN 其為數字型別計算錯誤
- undefined 其為任何型別若未初始化表示狀態
## 特有型別
- 其本身並無KeyValuePair，透過字典方式呈現
# 變數、集合、條件、迴圈、函式、事件基礎元素所對應語法?
## 變數
- [script生命週期建議位置](https://codertw.com/%E5%89%8D%E7%AB%AF%E9%96%8B%E7%99%BC/283038/)
- 特別小心var作用域其與平常理解不同會有变量提升（hoisting）
## 集合
- 只會有**array與dict**搭配組合
- 用let搭配右側**指定符號**來產生對應型別集合 
  ```
  let lists = ["A","B","C"];
  ```
  - 若無存在索引元素回傳undefined
  [[SQL Select述句exception]]

## 條件
## 迴圈
## 函式
## 事件
- event處理流程 => trigger => capture => process
- event綁定方法
     - 指定法
     ```
        let btn = document.getElementById("Content");
        btn.onclick = function(){alert('click Content');}
     ```
     - 監聽法
     ```
         btn.addEventListener("click",
    function()
    {
      alert('click Content');
    });

    btn.addEventListener("click",
    function()
    {
      alert('twice click Content');
    });
     ```
     語法理解錯誤常見誤區[[js函數與事件相關exception]]

|event|功能|
|:--|:--|
|onkeyup|為此3個event最後trigger，若有取得最後使用者輸入值則用此|
|onkeypress|只接收文字類型按鍵(但若用中文輸入法若沒打完字會有遺漏捕捉單引號情形)|
|onkeydown|所有按鍵都能接收|

- event內屬性:
  - cancelable:表示是否可阻擋event繼續冒泡,若為false則調用preventDefault無效
  - preventDefault:停止目前事件動作
  - stopPropagation:讓其停止事件繼續冒泡




# 原生功能體現環境特性?

#### extension method prototype
- extension method都是透過此屬性override:
- ex:Object.prototype
#### inherit static method
- Object.keys，字典取每個KeyValuePair的key
#### 延遲查詢
- 所丟入參數為函數都帶有此特性,特有 call back function,ex:addEventListener