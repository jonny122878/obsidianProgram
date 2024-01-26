# Unify

# Evergreen Note
Highlight:
Question:
Answer:
# Summary

# Note
- Regex在c#Match()就算無Match到也會return**一個Group**且其屬性為Success為false
- 若re為多個 ex:(?<...>)時還是除了Group[name].Value,還會有一個Match全部的

```
GroupCollection Regex.Match(string)
```

- [[Reg抓取字串變數含有換行符]]Enum設定換行也抓取


- [獲取只有數字檔案名](######獲取只有數字檔案名)
- [獲取只有文字檔案名]
- (######獲取只有文字檔案名)
- [取得負數整數、小數](######取得正負整數、小數)
- [取得斜線日期格式](######取得斜線日期格式)


###### 取得正負整數、小數
- 思考盲點(數字有數量限制不是一直抓取到不是數字停下)
- Regex rgDate = new Regex(@"^\d{3}/\d{2}/\d{2}");

###### 取得正負整數、小數
- ^-?\d+$
- ^-?\d\.\d+$
- 可利用開頭和結尾約束，避免讓單字其他字元進入
- 利用非貪模式讓負號只保留一個



###### 獲取只有數字檔案名
- 目標為類別尺度，反斜線
- 貪心
```
var input = "20211028債券部對手信用風險.xls";            
Regex rgDate = new Regex(@"\d+");
var date8 = rgDate.Match(input).Groups.Cast<Match>().Select(r => r.Value).First(); 
```

###### 獲取只有文字檔案名
- 目標為類別尺度，反斜線
- 貪心
- 用中刮建立邏輯反向
```
var input = "20211028債券部對手信用風險.xls";            
Regex rgReport = new Regex(@"[^\d]+");           
var report = rgReport.Match(input).Groups.Cast<Match>().Select(r => r.Value).First();
```
