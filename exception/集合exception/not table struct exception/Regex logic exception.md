# Metadata
Qty::6
Review::
Restructure::relation 1~6

### Think


# Exception


1. #flashcards 
- Highlight:C
- Question:取得正負整數、小數
- 思考:數字有數量限制不是一直抓取到不是數字停下
?
- Answer:
```
Regex rgDate = new Regex(@"^\d{3}/\d{2}/\d{2}");
```

2. #flashcards 
- Highlight:C
- Question:取得正負整數、小數
- 思考:
- 可利用開頭和結尾約束，避免讓單字其他字元進入
- 利用非貪模式讓負號只保留一個
?
- Answer:
```
^-?\d+$
^-?\d\.\d+$
```

3. #flashcards 
- Highlight:C
- Question:獲取只有文字檔案名
- 思考:
- 目標為類別尺度，反斜線
- 貪心
?
- Answer:
```
var input = "20211028債券部對手信用風險.xls";            
Regex rgDate = new Regex(@"\d+");
var date8 = rgDate.Match(input).Groups.Cast<Match>().Select(r => r.Value).First(); 
```

4. #flashcards 
- Highlight:C
- Question:獲取只有數字檔案名
- 思考
- 目標為類別尺度，反斜線
- 貪心
- 用中刮建立邏輯反向
?
- Answer:
```
var input = "20211028債券部對手信用風險.xls";            
Regex rgReport = new Regex(@"[^\d]+");           
var report = rgReport.Match(input).Groups.Cast<Match>().Select(r => r.Value).First();
```

5. #flashcards 
- Highlight:javascript，直覺按照小數格式寫出Reg
- Question:測試時輸入穿插空白都會進行防呆,ex:' 3'、'3 '、'3 9'。但當甚麼都**不輸入為空字元**就跳脫防呆
?
- Answer:寫防呆時考量[[不好判別exception]]

6. #flashcards 
- Highlight:C，AP檢驗月份日期是否正確,直覺反應用二個數字規則約束,但月份一月到九月**前面數字**都要是0,十月到十二月**開頭都是1**,尾數只能0~2
- Question:按照規則分析,是有二種條件,是否需要用二個re去檢驗
ex:
```
bool isOne = ....
bool isTen = .....
if(isOne || isTen)
```
?
- Answer:條件用()去包覆,之後在透過[]符號類似SQL WHERE IN ()
```
[(0?\d)|(1?[0-2])]
```
