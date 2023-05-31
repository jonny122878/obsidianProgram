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


# Highlight:
1. 在todo-list.component.html中button設定加入event
```
(click)="$event.target"
```
在todo-list.component.ts

3. 想要在父module.ts做一個下拉選單全部來源，後續在透過注入到子module.ts
```
@Input() dropdownInitData: InitDropdownData;
```
# Question:

2. 物件在指定DTO時有無類似Dapper方式將其都給指定
3. 為何明明後端API是有資料的，在子module.ts直接呼叫service也是有值，但透過父module.ts呼叫service無值
# Answer:
1.在todo-list.component.html中button設定加入event參數直覺錯誤jQuery，應為event
```
(keyup)="addTodo($event)"
```
在todo-list.component.ts:型別為事件
```
addTodo(event :KeyboardEvent):void
```

2. 其有內建語法糖可直接指定
```
    queryKey: SmCommonQueryModel;
    query(queryKey: SmCommonQueryModel): void {
        this.queryKey = { ...queryKey};
    }
```
3. 因為Observerable為異步，每個component所呼叫時間不盡相同