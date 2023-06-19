---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:
#知識 
# Unify
調用componenet時與C# Controller無太大差異
- 注意成員**初始值**和初始**函數位置**
- DI時擅用語法糖

# Highlight:
1. component內constructor injection service
2. component內建一屬性用來處理商業邏輯
```
preViewData:PreviewModel;
selectValue:string;
```
3. 衍生上述情境，用字串來接收combobox選取值
```
if(this.selectValue === '')
```
# Question:
1. 發現接手code並無宣告相對應成員
2. 在調用component內建屬性時，丟出Cannot set properties of undefined (setting 'ProdPolicyClauseId')
3. 為何防呆無法條件無法成立
# Answer:
1. Angular語法糖省去C#宣告成員冗餘效果
2. C#WinForm邏輯Form、Form_Load相同，**成員都需實體化**避免預設null造成不可預期錯誤
```
ngOnInit(): void {

}
```
3. 同上若string無實體化default undefined
```
if(this.selectValue === undefined)
```