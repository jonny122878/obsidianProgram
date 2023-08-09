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
Qty::8

#work #知識 
# Unify
- 條件式判別null原則都是到物件，屬性直接exception
- declare function給其他component調用時要注意物件參考特性
- model.ts型別註記只在IDE有效，若是接收any會被override
- 物件delcare方式C#與typescript不同，typescript並不會自行將屬性給定義
- typescript null只能阻擋null、undefined其他則失效
- typescript string與null運算會自動轉成字串，與數字會將null當成0

1. #flashcards 
- Highlight:typescript
- Question:條件式要擋掉不符合臨界值型別，能否用null擋全部
?
- Answer:只能用null、擋住undefined，內容相同都是空值，差別再於給使用者了解臨界狀態。NaN不表示空值只能用isNaN判別

2. #flashcards 
- Highlight:typescript。當新增狀態時，Output型別並無初始化，用if防呆
```
if(this.mainData.questionData.q04 != undefined)
```
- Question:Console一樣錯誤訊息
?
- Answer:物件本身才有用，其屬性無效
```
this.mainData.questionData undefined
this.mainData.questionData.q04 error
```

3. #flashcards 
- Highlight:typescript
```
let valAddress:string = this.form.controls['address'].value;
```
- Question:字串接受是否像C#一樣默認null?
?
- Answer:一樣


4. #flashcards 
- Highlight:typescript
- Question:model.ts定義string,但實際值是number
?
- Answer:因透過千分位函數**function return any**,model提供型別註記但若透過any方式塞其他值是不會exception


5. #flashcards 
- Highlight:typescript
- Question:物件拷貝並無提示
```
JSON.parse(JSON.stringify(this.addressQueryDatas));
```
?
- Answer:其function為any，建議接收變數用型別推論


6. #flashcards 
- Highlight:typescript
- Question:條件式跳出非true、false之外值
```
if (0 && !isNaN(Number(0))) return 0
```
?
- Answer:目前還無法確定0定義?


7. #flashcards 
- Highlight:typescript
- Question:使用者反應label呈現地址後null
?
- Answer:null + 'string' = 'nullstring'


8. #flashcards 
- Highlight:typescript
- Question:null* 2 ??
?
- Answer:因為null識別為0，因此等於0


9. #flashcards 
- Highlight:在API中將new隱含型別或各種具名參考型別class給傳入，Prase string to json之後，在透過 dynamic 接收 json prase class
- Question:
  - 若dynamic接收變數若調用不存在的屬性編譯器會檢查嗎?
  - new隱含型別此種編譯器製造出來型別是否能Parse
?
- Answer:
  - 不會檢查，還原之後看編譯器型別為JSON OBJECT
  - new隱含型別因是編譯器製造出來每次都不相同，還原之後就是string

10. #flashcards 
- Highlight:
- Question:
?
- Answer: