# 引入副程式
ex:NuGet、using.....
對DOM進行CRUD
因依附在DOM為tree structure,因此其Query是獨特的

# 解決問題情境步驟
## 格式轉換
### [轉換型態](######convert_type_ex)
### [string to array](######string_convert_array_ex)
### [string format](######string_format_ex)
### [string array組合](######string_array_concat_ex)
### [date格式轉換](######date_format_ex)
ps:object and JSON are same

## DOM異動
### [combobox get value](######combobox_get_value_ex)
### [two combobox relationship](######two_combobox_relationship_ex)
### [button add tag](######button_add_tag_ex)
## 其他
### [獲取傳遞來表單值](######get_form_value_ex)
### [URL編碼轉換](https://www.ewdna.com/2008/12/javascriptescape-encodeuri.html)
# 指令樣式
ex:function、object....
## function
- **DateTime**.getFullYear()
- **DateTime**.getMonth()
- **DateTime**.getDate()
- **string**.padStart(**補的位數**, '**補的字元**')
  - ex:padStart(2, '0')
- parseInt(**數字**, **進位數**)
  - ex:parseInt(data['Birthday'].substr(6), 10) 
- window.location.href = "https://localhost:44348/Member/Index";
- arr.pop() 取得最後元素
## Style
- HTMLElement.setAttribute('**className**','**css**') 

## 選取器
- HTML collection document.getElementsByClassName('**className**');
- HTML collection document.getEleMentsByTagName('**tagName**');
- NodeList document.querySelectorAll('**any 選取器組合pattern(允許父子)**')
- HTML document.getElementById('**id**')

## 型態
- HTML Collection
  - HTML document.getElementsByTagName('**tagName**').namedItem('**name scale**');
- NodeList
  - document.querySelectorAll("**any pattern**").length
  - ex:
  - document.querySelectorAll('div.divCss input[type="checkbox"]'); //div的class為divCss內input屬性指定
  - document.querySelectorAll('div input[type="checkbox"]'); //div內input屬性指定
  - document.querySelectorAll('div .txtTest'); //div內txtTest class
# limit
ex:臨界值
- innerText and innerHTML區別?
  - innerText:接收值**不會過濾**HTML
  - innerHTML:接收值**會過濾**HTML
```
let tagShow = document.getElementsByTagName("h3")[0];
tagShow.innerHTML = "顯示:" + value;
//tagShow.innerText = "顯示:" + value;
```
- NodeList and HTMLCollection區別?
  - [NodeList and HTMLCollection區別](https://ithelp.ithome.com.tw/articles/10268108?sc=iThelpR)
  - 類似IEnumerable無法有類似LINQ支援(陣列方法)
- Controller return Json DateTime資料無法被解析?
  - 字串切割數字提取出來，轉型成數字再轉日期
  ```
  let today = new Date(parseInt(data['Birthday'].substr(6), 10));
    var dd = String(today.getDate()).padStart(2, '0');
    var mm = String(today.getMonth() + 1).padStart(2, '0'); 
    var yyyy = today.getFullYear();
    today = yyyy + '-' + mm + '-' + dd;
  ```
- Date型別填入input type date無法填入?
  - 需為yyyy-MM-dd格式 
- substr與substring差異?
  - 計數單位為長度與位置數量 
  - [參考](https://www.wibibi.com/info.php?tid=315) 
- 調用replace並沒有每個目標物都取代到?
  - 會從開頭開始尋找取代到第一個目標物後停下來 
###### date_format_ex
- 一樣預設為YYYY/MM/DD HH:mm:ss(但有分上下午)
- ISO為YYYY-MM-DD....(因為提供其他預設函數，需自行字串切割)
```
let input = '2017-10-17T00:00:00';
let dateTime = new Date(input).toLocaleString();
let date = new Date(input).toLocaleDateString();
let time = new Date(input).toLocaleTimeString();
let ISOdateTime = new Date(input).toISOString();
```


###### string_array_concat_ex
```
let lists = ['A','B','C','D'];
s = s.concat(lists);
```

###### string_format_ex
- format替換用`
```
let r = getRandom(0,255);
let g = getRandom(0,255);
let b = getRandom(0,255);
let rgb = `background-color: rgb(${r},${g},${b})`;
```

###### get_form_value_ex
- form
  - method設定**get**，post因client and server同來源牴觸原本網路性質
  - action設定**導向url** 
  - input中name,value屬性 傳遞後 JSON key-value
- dest
  - 參數字串分割成字典
  - 從表單中name屬性查找字典中對應key-value
```
<form action="./question3_B.html" method="get" id="formA">
    <label for="inputA">請輸入A網頁的值</label>
    <input type="text" id="inputAID" name="inputAName" value="">
    <button type="submit">提交</button>
</form>
function GetDictQuery()
{
    let dictQuery = {};
    let query = window.location.search.substring(1);
    let params = query.split('&');
    //Map to Dict (順序尺度判別key or value)
    params.forEach(ele => {
        let pairs = ele.split('=');
        dictQuery[pairs[0]] = pairs[1];
    });
    return dictQuery;
}
let dictQuery = GetDictQuery();
let name = dictQuery['inputAName'];
```



###### button_add_tag_ex
```
let tagContent = document.getElementById("btnContent");
tagContent.addEventListener("click",
function()
{
  alert('tagContent click');
  //get div目前的數量並且製作對應id value
  let divNum = document.getElementById("Content").childElementCount;

  alert(divNum);
  let idBtn="btn" + String(divNum);
  let idLb="lb" + String(divNum);
  alert(idLb);
  let lb = document.createElement('label');
  lb.id = idLb;
  lb.innerText = "label" + String(divNum);
  let btn = document.createElement('button');
  btn.id = idBtn;
  btn.innerText = "button" + String(divNum);
  btn.onclick = function()
  {
    document.getElementById(idLb).remove();
  }
  document.getElementById("Content").appendChild(btn);
  document.getElementById("Content").appendChild(lb);
});
```

###### two_combobox_relationship_ex
```
let models = [
  {ID:1,Email:"bayonet79921@gmail.com",Name:"jonny"},
  {ID:2,Email:"test0906568135@gmail.com",Name:"2601"},
  {ID:3,Email:"b0931866529@gmail.com",Name:"tsai"}
];  
let tagEmail = document.getElementById("MemberCashInMemberGmail");
let tagName = document.getElementById('MemberCashInMemberName');

tagEmail.addEventListener("change",
function(){
  alert('change');
  let index=tagEmail.selectedIndex; //序號，取當前選中選項的序號
  let val = tagEmail.options[index].text;
  alert(val);
  const idxModel = models.findIndex(object => {
                    return object.Email === val;
                  });

  tagName.selectedIndex = idxModel;
  alert(idxModel);                
});
```

###### convert_type_ex
共同點用函式建構式注入
```
let date = new Date('2022-08-05');
let bool = new Boolean(true);
let num = new Number(2.19);
```

###### string_convert_array_ex
```
const text = '["Ford", "BMW", "Audi", "Fiat"]';
const myArr = JSON.parse(text);
```


###### combobox_get_value_ex
```
let email = document.getElementById("MemberCashInMemberGmail");
let index=email.selectedIndex; //序號，取當前選中選項的序號
let val = email.options[index].text;
```