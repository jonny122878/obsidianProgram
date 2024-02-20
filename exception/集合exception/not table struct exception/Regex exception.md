# Metadata
Qty::7
Review::
Restructure::relation 4、5

### Think



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
- Highlight:C
- Question:若都無Match到return結果為?Match到多個結果為?
```
GroupCollection Regex.Match(string)
```
?
- Answer:
- Regex在c#Match()就算無Match到也會return**一個Group**且其屬性為Success為false
- 若re為多個 ex:(?<...>)時還是除了Group[name].Value,還會有一個Match全部的

5. #flashcards 
- Highlight:C，資料庫內有有許多表單且其編碼單號都有其自訂規則,任務是要按照單號編碼移轉到指定資料庫
- Question:執行出現exception,發現是資料表單號欄位**有NULL**
?
- Answer:在C#內的Regex只能**處理空字元**,是null時就會丟exception

6. #flashcards 
- Highlight:javascript
- Question:調用new RegExp與re直接調用區別?
?
- Answer:
|項目|優點|缺點|
|:--|:--|:--|
|new RegExp|re可抽換|效能差|
|re直接調用|效能好|不能替換其它re|

- [javascript re參數解說](https://tw511.com/a/01/43028.html)

7. #flashcards 
- Highlight:typescript
- Question:在做字串驗證是否要特別防呆臨界值空字元和null
?
- Answer:無須特別去防呆都會return false
```
//.test('')
//.test(null)
```