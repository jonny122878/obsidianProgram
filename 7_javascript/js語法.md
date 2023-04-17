---
data:2023-04-04
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:總結
Author:
Note Type:
Topics:


## 語言存在環境特性?
整個網頁背後是透過window物件去控制,在再透過inherit將其區分為Console,Document這子物件
因此指令種類區分:
- window(基礎功能:ex:網址、初始化跳轉位置)
- document(平常最常用到,使用者互動,依附在[[js DOM]]下)
-  後來推出語法精簡操作DOM[[jQuery]]
- 語言自身
### 調用心法
###### Debug要有這基本認知
- 純弱型別語言，可動態重複指定**override原本型別**
- 型別指定鬆散可以累加
	ex:變數declare Array 再指定其atttribute (類似強型別指定class)
###### 未知語法思考
- function first 表示語言最小單位為**function**,(未知語法調用時參數傳function就對了)
###### 撰寫起手式
- 因其為弱型別不會exception,再起手式必定要防呆時需多考慮**各種exception型別**
	ex:像是若要防呆集合類型在jQuery可用 $.isArray
	
- https://vocus.cc/article/61e24cd9fd8978000164dc34
- https://medium.com/i-am-mike/10%E5%80%8B%E6%96%B0%E6%89%8B%E5%BF%85%E7%9F%A5%E7%9A%84-javascrip-%E5%AF%A6%E7%94%A8%E6%8A%80%E5%B7%A7-75b55d7c3e47

## 語言型別衝突呈現:如何declare?、exception所丟出?


#### 型別(含轉型)
- 宣告關鍵字let 
- 因純弱型別語言，除**null**外還有undefined，limit相關型別
- KeyValuePair
- 餘數和次方
```
let user = {ID:1,Name:"test"};
7 % 2
7 ** 2
```
- [script建議位置](https://codertw.com/%E5%89%8D%E7%AB%AF%E9%96%8B%E7%99%BC/283038/)
#### 變數
- 字串變數組合要單雙引號去搭配 
- 簡單區分function內為區域,外部為全域
- 覆寫機制也和C#相同,同名稱再宣告一次就override
#### 結構集合
- 只會有**array與dict**搭配組合
- 用let搭配右側**指定符號**來產生對應型別集合 
  ```
  let lists = ["A","B","C"];
  ```
  - 若無存在索引元素回傳undefined
  [[js array]]
  
## 變數、條件、迴圈、函式四大基礎所對應語法?
#### 函數

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
     語法理解錯誤常見誤區[[js 函數 exception]]
    

|event|功能|
|:--|:--|
|onkeyup|為此3個event最後trigger，若有取得最後使用者輸入值則用此|
|onkeypress|只接收文字類型按鍵(但若用中文輸入法若沒打完字會有遺漏捕捉單引號情形)|
|onkeydown|所有按鍵都能接收|

- event內屬性:
  - cancelable:表示是否可阻擋event繼續冒泡,若為false則調用preventDefault無效
  - preventDefault:停止目前事件動作
  - stopPropagation:讓其停止事件繼續冒泡



## 原生功能體現環境特性?
#### extension method prototype
- extension method都是透過此屬性override:
- ex:Object.prototype