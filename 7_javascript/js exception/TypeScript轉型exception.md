---
data:
aliases:
---
# Metadata
Status:
Source Type:
Source URL:
Project:金財通
Author:
Note Type:
Topics:
#資訊 

# Unify


# Highlight:
1. service層要return表格資料
```
:Observable<DmCommonPolicyClauseInfoModel>
```
2. service層方法函數簽章為any
```
saveProdClauseDescDetail(data: ProdClauseDescDetailFormModel): Observable<any> {
return this.http.post<any>(this.controllerUrl + 'modifyClauseParam', data);
}
```
# Question:
1. 明明是型別相同，但接收IDE顯示紅字
2. any型別如何接收後端API發送JSON數據
# Answer:
1. Observable本身為一種**非同步**能override泛型型別，因此調用是需用其內建方法
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
2. any可以將其想成object，因此只要宣告**型別名稱**和JSON內**KEY**有對應到，就可進行綁定
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


