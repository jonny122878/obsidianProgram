# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::8
Review::
Restructure::

#work #知識 
# Unify

## 本質

## 衍生衝突



# Exception


1. #flashcards 
- Highlight:C#
- Question:function call async function,but function return not Task
?
- Answer:调用异步函数（带有async），外部函数不用await等待异步函数完成，异步函数将在后台独立运行，外部函数将立即继续执行，不会等待异步函数完成。意味外部函数不等待异步函数的结果，可能导致异步操作和外部操作并发执行。

2. #flashcards 
- Highlight:C#
- Question:call async function,but not await keyword
?
- Answer:
```
在外部函数中没有使用await等待异步操作完成，直接获取Task<int>的Result属性。这可能会导致线程阻塞，因Result属性会等待异步操作完成并返回。这种做法并不推荐，它可能导致死锁或不可预测的行为。
如果确实需要在不等待异步操作的情况下执行其他操作，那应该小心处理并确保不会导致线程阻塞或不一致的结果。

```

3. #flashcards 
- Highlight:C#
- Question:
```
在外部函数中没有使用await等待异步操作完成，直接获取Task<int>的Result属性。这可能会导致线程阻塞，因Result属性会等待异步操作完成并返回。这种做法并不推荐，它可能导致死锁或不可预测的行为。
如果确实需要在不等待异步操作的情况下执行其他操作，那应该小心处理并确保不会导致线程阻塞或不一致的结果。
```
?
- Answer:class方法在實作時需加async,interface不需要

4. #flashcards 
- Highlight:typescript,service層要return表格資料
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

5. #flashcards 
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
- Highlight:
- Question:處理緒和執行緒差異
?
- Answer:
  - 一個具有主(Program.cs)和多個副並且它們是共通的
  - CPU Bound同步多執行(主要原理在於因為不是阻塞，因此時間片段的解決方法是無效的)
  - IO Bound非同步多執行

7. #flashcards 
- Highlight:javascript
- Question:用function模擬非同步多執行緒
?
- Answer:
- setTimeout為執行緒一種,用來模擬IO阻塞情況
- setInterval 非同步多執行緒,定時會call

8. #flashcards 
- Highlight:jQuery
- Question:非同步語法
?
- Answer:
  - 將其想成為C#實現非同步功能，只是其應用在ajax上，then內有針對成功與失敗回傳結果
  ```
  $.when($('#frmQuery').cacheForm()).then(function () {
  })
  ```

9. #flashcards 
- Highlight:
- Question:
?
- Answer:
