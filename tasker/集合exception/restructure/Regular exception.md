# Metadata
Qty::8
Review::
Restructure::

#work #資訊 
# Unify

## 本質
- 原始結構體
- 參考結構體
- 換行符
- 特殊符
## 衍生衝突
- 原始結構體:1 string理解、
- 參考結構體:8 Regex效能差別
- 換行符:g 2、3
- 特殊符:


1. #flashcards 
- Highlight:javascript
- Question:調用re.test()怎樣都無法調用
?
- Answer:注意指定re是否有用成string,Regular Expression是一種型別,只需re =/pattern/

2. #flashcards 
- Highlight:C#。AP存檔時丟出MS-SQL欄位與資料行數量不一致情況,要檢查確認是那個對照欄位出問題,因此將欄位與對應值切割成二個array
- Question:發現在用Regular去捕捉字串時,並沒有辦法INSERT SQL整句整個用Regular抓取到string內
?
- Answer:因為input 來源為string.Format() 所以其帶有\n符號,預設Regex是無匹配換行符的,
Regex = new Regex(re,RegexOptions.Singleline**);

3. #flashcards 
- Highlight:typescript、javascript
- Question:檢查文字框只能輸入正整數,思路為用test(),整個匹配用\g去設定
```
/\d+/g
```
?
- Answer:\g其本質為忽略換行為單位,但目前檢查文字框就無換行,思路為用開頭和結尾當約束條件
```
/^\d+$/
```

4. #flashcards 
- Highlight:typescript
- Question:檢查小數3位和正整數,但明明測試無問題,實際上1.此種情況無法防呆
```
/(^\d+$|^\d+\.\d{1,3}$)/
```
?
- Answer:檢查文字框是否type為number,會自動轉型成1
- 1-1 轉成null

5. #flashcards 
- Highlight:
- Question:撈取INSERT SQL欄位區段撈不到
```
([\w]+)
```
?
- Answer:C#,撈取INSERT SQL值區段撈不到
  - 釐清特殊字元定義，ex:() 刮弧就是特殊字元
  - 釐清那些是符號規範,ex:,逗號就不在\w類別尺度內
  - 解法所能接受符號自己包覆成類別尺度,並且特殊符號前面要加修飾子
```
\([\w,+]\)
```

6. #flashcards 
- Highlight:C#,撈取INSERT SQL值區段撈不到
- Question:因值區段包含眾多符號,規劃用萬用字元.去抓
```
(.*\)
```
?
- Answer:
  - .萬用字元順序>)，因此整個就停不下直接到結尾
  - 釐清那些是特殊符號,那些是不包含\w符號需要自己用做成**類別尺度[]**



7. #flashcards 
- Highlight:javascript
- Question:怎樣都攔到
```
/\d+.\d+/ 
```
?
- Answer:注意關鍵字是否有加入特殊修飾字元辦識

8. #flashcards 
- Highlight:javascript
- Question:調用new RegExp與re直接調用區別?
?
- Answer:
|項目|優點|缺點|
|:--|:--|:--|
|new RegExp|re可抽換|效能差|
|re直接調用|效能好|不能替換其它re|

- [javascript re參數解說](https://tw511.com/a/01/43028.html)


10. #flashcards 
- Highlight:
- Question:
?
- Answer:

