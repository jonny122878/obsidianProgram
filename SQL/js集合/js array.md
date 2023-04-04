# 動作解決問題情境
## Structure
## Map
- ToArray: Array.prototype.slice.call(**IEnumerable**) 
## Where
## Reduce
## Zip
## Group
## Order
## Function

# 動作指令語法
## Structure
### [物件陣列](######object_array_ex)
## Map
### [結構轉換DOM](map_to_DOM_ex)
## Where
### [Where](######where_filter_ex)
### [類似FistOrDefault](######first_findIndex_ex)
## Reduce
### [string合併](######string_aggregate_ex)
## Zip
## Group
## Order
## Function

# 動作limit
## Structure
## Map
```
IEnumerable<KeyValuePair<int, List<BookLendRecord>>>
        let records = lendLists.filter(object => {
            return object.Key == new Number(id);
        }).map(r => r.Value)[0];
```
- 直覺用Select(r => r.Value)取不到整個集合?
  - map預設回傳集合，所以是包在集合中元素內
- 情境再調用Map時怎都無法調用,原因function 無return
- 情境因為無硬性規範function return值,若含有if map時就會有undefined情況
## Where

## Reduce
## Zip
## Group
## Order
## Function

###### string_aggregate_ex
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


###### object_array_ex
```
function Player(Id, Name, RegDate, Score) {
    this.Id = Id;
    this.Name = Name;
    this.RegDate = RegDate;
    this.Score = Score;
}
var p1 = new Player("P1", "Jeffrey", new Date(1900, 0, 1), 32767);
var p2 = new Player("P2", "Darkthread", new Date(2016, 6, 2), 65536);
var list = [p1, p2];
```
```
p1["Id"] = 取屬性值
```


###### map_to_DOM_ex
```
let btns = models.map(function(e)
{
    let btn = document.createElement('button');
    btn.id = e.ID.toString();
    btn.innerText = e.Email;    
    return btn;
});
```
###### where_filter_ex
```
var whereResult = list.filter(function(o) { return o.Score > 32767 });
```

###### first_findIndex_ex
- 用findIndex取得index後再取元素
- 或是map指定第0元素
```
const index = list.findIndex(object => {
                              return object.Id === 'P2';
                            });
```


https://www.casper.tw/javascript/2017/06/29/es6-native-array/#Array-prototype-map
