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
#資訊 #金財通 
# Unify




1. #flashcards 
- Highlight:service層要return表格資料
```
:Observable<DmCommonPolicyClauseInfoModel>
```
- Question:明明是型別相同，但接收時IDE顯示紅字
?
- Answer:Observable本身為一種**非同步**能override泛型型別，因此調用是需用其內建方法
```
.subscribe(data =>
            {
            },
            error =>
            {
                console.log(error);
            });
```
ps:衍生異步概念，console都要在subscribe內，否則在Chorme打出來**順序不一致**難以debug
```
this.service.getProdClauseDetail(prodPolicyClauseId).subscribe(data => {
            console.log('查詢key:');
            console.log(prodPolicyClauseId);            
            this.detailData = data.data.item2 as ProdClauseDetailFormModel;            
            console.log('查詢result:');
            console.log(this.detailData);
        });
        console.log(this.detailData);  //error
```

2. #flashcards 
- Highlight:service層方法函數簽章為any
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

3. #flashcards 
- Highlight:當新增狀態時，Output型別並無初始化，用if防呆
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

4. #flashcards 
- Highlight:
```
let valAddress:string = this.form.controls['address'].value;
```
- Question:字串接受是否像C#一樣默認null
?
- Answer:一樣

5. #flashcards 
- Highlight:
- Question:在接收值時有let、const、var如何選擇?
?
- Answer:let、const像C#一樣原理作用域，var小心使用上會有弱型別特有**hoisting**

6. #flashcards 
- Highlight:做測試資料進行防呆測試
```
let isExist = this.addresses.some(r => r.value == this.quoteThirdData.quoteAddress[i].locationName);
```
- Question:無按照some去跑?
?
- Answer:並無特別指定屬性所導致
```
let addr2 = <QuoteAddress>
        {
            quoteNo:'',
            quoteVer:1,
            locationNo:'005',
            fullAddress:'test',
        };
```

7. #flashcards 
- Highlight:
- Question:
?
- Answer:

