# Metadata
Qty::7
Review::
Restructure::relation 1~7

### Think

1. #flashcards 
- Highlight:typescript
- Question:物件拷貝並無提示
```
JSON.parse(JSON.stringify(this.addressQueryDatas));
```
?
- Answer:其function為any，建議接收變數用型別推論

2. #flashcards 
- Highlight:在API中將new隱含型別或各種具名參考型別class給傳入，Prase string to json之後，在透過 dynamic 接收 json prase class
- Question:
  - 若dynamic接收變數若調用不存在的屬性編譯器會檢查嗎?
  - new隱含型別此種編譯器製造出來型別是否能Parse
?
- Answer:
  - 不會檢查，還原之後看編譯器型別為JSON OBJECT
  - new隱含型別因是編譯器製造出來每次都不相同，還原之後就是string

3. #flashcards 
- Highlight:typescript
- Question:model.ts定義string,但實際值是number
?
- Answer:因透過千分位函數**function return any**,model提供型別註記但若透過any方式塞其他值是不會exception

4. #flashcards 
- Highlight:C#
- Question:變數使用.ToString()丟出exception?
?
- Answer:要先將object給強型別

8. #flashcards 
- Highlight:typescript,service層方法函數簽章為any
```
saveProdClauseDescDetail(data: ProdClauseDescDetailFormModel): Observable<any> {
return this.http.post<any>(this.controllerUrl + 'modifyClauseParam', data);
}
```
- Question:any型別如何接收後端API發送JSON數據
?
- Answer:any可以將其想成object，因此只要宣告**型別名稱**和JSON內**KEY**有對應到，就可進行綁定
```
//方法簽章
getComiRateSettingDetail(ncProdPolicyClauseId: number): Observable<any> {
    return this.http.get<any>(this.controllerUrl + 'QueryClause?' +  ncProdPolicyClauseId);
}
//POSTMAN JSON呈現
{
	"data": {}
}
//接收轉型結果
this.ddlInitData = data.data as InitDropdownData;
```

6. #flashcards 
- Highlight:TypeScript
- Question:明明textbox為空字元，但return function此物件後發現屬性為null
?
- Answer:會自動將臨界屬性給轉null
```
JSON.parse(JSON.stringify(results));
```

7. #flashcards 
- Highlight:typescript
- Question:Cannot read properties of null (reading 'issueRate')
?
- Answer:物件在實體化每個欄位都要指定，否則templete調用會噴出









