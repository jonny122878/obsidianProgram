---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:金財通
Author:
Note Type:
Topics:


# Highlight:
1. service層要return表格資料
```
:Observable<DmCommonPolicyClauseInfoModel>
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
2. any可以將其想成object，因此只要宣告**型別名稱**和JSON內**KEY**有對應到，就可進行綁定
```
{
	"data": {}
}
this.ddlInitData = data.data as InitDropdownData;
```