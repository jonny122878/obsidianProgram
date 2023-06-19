---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:總結
Author:
Note Type:
Topics:
#知識 
# Unify
- 物件概念都與C#雷同，深拷貝可擅用語法糖
- 物件實體化時小心C#null直覺概念


## 語言存在環境特性?
- 弱型別特有Type Annotation(型別推論機制)


## 語言型別衝突呈現:如何declare?、exception所丟出?
### null、undefined是否透過強型別統一弄成只有null?
```
undefined:this.questionData = <QuestionModel>{};
this.questionData = <QuestionModel>
{
	quoteQuestionId:2,
};
```
主要差別在於物件初始化若無指定屬性是**undefined**，且要特別小心後續針對此物件屬性條件式判別


- 透過**strictNullCheck** complier設定null
- [[TypeScript轉型exception]]
## 變數、條件、迴圈、函式四大基礎所對應語法?
### 變數
- 引入C#語法與原生javascript對集合操作做合體，調用時不用function用**lambda**
```
selected.some(it => this.selected.indexOf(it) == -1)
```
- 物件declare時，和C#概念相同，理解實體化錯誤就會丟出Cannot read properties of undefined (reading 'push')
```
let arr :SmSaveProdCommiRateDModel[];
IEnumerable<SmSaveProdCommiRateDModel> arr;
let arr :SmSaveProdCommiRateDModel[] = [];
IEnumerable<SmSaveProdCommiRateDModel> arr = new List<SmSaveProdCommiRateDModel>;
```
- 物件深拷貝有語法糖可利用
```
queryKey: SmCommonQueryModel;
query(queryKey: SmCommonQueryModel): void {
        this.queryKey = { ...queryKey};
 }
```
## 原生功能體現環境特性?