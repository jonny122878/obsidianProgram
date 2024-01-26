# Metadata
Qty::
Review::
Restructure::relationId、summary

#work #資訊 
# Unify

## 本質

## 衍生衝突


- declare function給其他component調用時要注意物件參考特性
- model.ts型別註記只在IDE有效，若是接收any會被override
- 下列情境可透過產生非預期錯誤判別，ex:stestnull，60004000，console error
- 物件delcare方式C#與typescript不同，typescript並不會自行將屬性給定義
- typescript string與null運算會自動轉成字串，與數字會將null當成0



1. #flashcards 
- Highlight:typescript
```
let valAddress:string = this.form.controls['address'].value;
```
- Question:字串接受是否像C#一樣默認null?
?
- Answer:一樣


2. #flashcards 
- Highlight:typescript
- Question:model.ts定義string,但實際值是number
?
- Answer:因透過千分位函數**function return any**,model提供型別註記但若透過any方式塞其他值是不會exception


3. #flashcards 
- Highlight:typescript
- Question:物件拷貝並無提示
```
JSON.parse(JSON.stringify(this.addressQueryDatas));
```
?
- Answer:其function為any，建議接收變數用型別推論

4. #flashcards 
- Highlight:typescript
- Question:使用者反應label呈現地址後null
?
- Answer:null + 'string' = 'nullstring'



5. #flashcards 
- Highlight:typescript
- Question:null* 2 ??
?
- Answer:因為null識別為0，因此等於0


6. #flashcards 
- Highlight:在API中將new隱含型別或各種具名參考型別class給傳入，Prase string to json之後，在透過 dynamic 接收 json prase class
- Question:
  - 若dynamic接收變數若調用不存在的屬性編譯器會檢查嗎?
  - new隱含型別此種編譯器製造出來型別是否能Parse
?
- Answer:
  - 不會檢查，還原之後看編譯器型別為JSON OBJECT
  - new隱含型別因是編譯器製造出來每次都不相同，還原之後就是string

7. #flashcards 
- Highlight:TypeScript
- Question:明明textbox為空字元，但return function此物件後發現屬性為null
?
- Answer:會自動將臨界屬性給轉null
```
JSON.parse(JSON.stringify(results));
```
8. #flashcards 
- Highlight:typescript
- Question:面板上加總計算呈現加總數值並列
?
- Answer:array內含有string，string + number會轉成string

9. #flashcards 
- Highlight:typescript
- Question:1/0數學上無意義
?
- Answer:Infinity

10. #flashcards 
- Highlight:typescript
- Question:Cannot read properties of null (reading 'issueRate')
?
- Answer:物件在實體化每個欄位都要指定，否則templete調用會噴出

15. #flashcards 
- Highlight:typescript
- Question:FormControl value為string 和if內數字進行運算會產生何種結果
?
- Answer:其會自動轉數字
```
('10' > 3) true
('10' < 3) false
```


15. #flashcards 
- Highlight:python
- Question:運算除法若想輸出浮點數或整數
?
- Answer:
```
5 / 2 float
5 // 2 int
5 / 2/0 float
```