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


## 環境
- 依附在DOM上操作,**選取器**概念重要性
- 選取器語法底層Regular
## 調用特別注意bug
- 操作協定時:C#構造推想其為工具封裝成靜態類，類似**HttpContext** $.post、.ajax
- class因其帶有集合特性，可有多個類別但都用同個字串呈現，因此跳脫attr，用addClass
- ddl option 因其結構上與input type這種帶有**內部集合**特性，因此不為val()
- $選取器有些像裝飾器東西，將HtmlElement丟入之後即可操作其對應method
## 未知思路

# 型別機制
## 轉型衝突
-[[jQuery選取器exception]]
## 特有型別

# 變數、集合、條件、迴圈、函式、事件基礎元素所對應語法?
## 變數
## 集合
## 條件
## 迴圈
## 函式
## 事件

# 原生功能體現環境特性?









# 解決問題情境步驟
## [3個div亂數產生背景色](######3個div亂數產生背景色)
## [讀取XML解析成table](######讀取XML解析成table)
## [ajax載入時表單](######ajax載入時表單)
## [ajax提交表單](######ajax提交表單)
- 先讀取表單內容進入字典集合
- success可再內部設定跳轉
## 掛載
- selector
- event
- action


# 指令樣式
ex:function、object....
## 選取器
- [各式選取器](https://ithelp.ithome.com.tw/articles/10095237?sc=pt)
- $("#**Id**")
- **jQuery object Enumerable** $(".**className**")
- **jQuery object Enunerable** $("**tagName**")
- **HTMLElement** $(".**className**").get(**index**)
## Selector Method
- document.attr('**attribute**','**value**')
- document.removeAttr('**attribute**','**value**')
## DOM CRUD
- [CRUD參考](https://zwh.zone/jquery-e6-8e-a7-e5-88-b6dom-e5-85-83-e7-b4-a0/)
- 都是方法組成,ex:children()[0]
- 函數多載有無參數去實現取得寫入,ex:text()、text(context)
- text(*content*) 
- html(*content*)
- empty() 保留此標籤清空內部子元素
## 型態

# limit
ex:臨界值
- 為何表格附加不上去?
  - 是否誤用指令remove連標籤都清除了 
- 選取器組合字串找不到元素?
  - "#" + idDiv + ""
  - "'#" + idSpan + "'" exception
- 附加標籤取不到元素?
  - 附加標籤要用**選取器**且要用**id**免得會取到Enumerable
  - ex:$("<input type='checkbox' id='" + idChk + "'>");
- 選取器不能使用setAttribute?
  - return jQuery object Enumerable
  - 只能用**jQuery** method不能用DOM method
- 選取器綁定是否要特別指定元素?
  - jQuery event and attr可用Enumerable綁定
  - javascript event attribute傳統只能element設定
- 如何類似Form_Load掛載?
  - 不一定需要放在大的$(function(){});也可進行掛載
- when then用法?
  - 將其想成為C#實現非同步功能，只是其應用在ajax上，then內有針對成功與失敗回傳結果
  ```
  $.when($('#frmQuery').cacheForm()).then(function () {
  })
  ```

###### ajax載入時表單
```
$(document).ready(function () {
        
        let dictQuery = GetDictQuery();
        let id = dictQuery['Id'];
        var getUrl = 'https://localhost:44348/Member/LoadEdit?Id=' + id;
        $.ajax({
            type: "GET",
            url: getUrl,
            dataType: "json",
            success: function (data) {
                
            },
            error: function () {

            }
        })
    });
```
###### ajax提交表單
```
$('#btnEdit').click(function () {
        var datas = $("form").serializeArray();
        $.ajax({
            type: "POST",
            url: "https://localhost:44348/Member/Edit",
            data: datas,
            success: function (res) {
                alert('會員修改成功');
                window.location.href = "https://localhost:44348/Member/Index";
            },
            error: function () {
                alert('error');
            }
        });
    });
```


###### 3個div亂數產生背景色
- random function
- string重組
- each迴圈語法=集合+idx+ele
```
function getRandom(min,max){
		return Math.floor(Math.random()*max)+min;
	}
	$('#btn').click(function(){		
		$.each($('div'),function(i,e){
			let r = getRandom(0,255);
			let g = getRandom(0,255);
			let b = getRandom(0,255);
			let rgb = `background-color: rgb(${r},${g},${b})`;
			$(e).attr('style',rgb);
		});
	});
```

###### 讀取XML解析成table
- xml => XMLDocument => 選取器jQuery object Enumerable
- find找出指定jQuery object Enumerable
- 將其組合成表格
```
let xmlDoc = $.parseXML(xml);
let $xml = $(xmlDoc);
let peoples = $xml.find('people');
$.each(peoples,function(i,e){
    let td = ['<tr>',
      '<td class="blue">',
      $(e).find('name').text(),
      '</td>',
      '<td class="green">',
      $(e).find('ename').text(),
      '</td>',
      '</tr>'].join("\n");
      $('#tbody').append(td);
  });
```
