---
date:
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

#知識 #金財通 
# Unify
調用componenet時與C# Controller無太大差異
- component生成trigger為html調用點
- constructor:DI
- ngOnInit:一次性載入
- ngOnChanges:本身內部裝飾器會因其它component有異動時
- DI時擅用語法糖
- [生命週期](https://ithelp.ithome.com.tw/articles/10231105)




1. #flashcards 
- Highlight:component內constructor injection service
- Question:發現接手code並無宣告相對應成員
?
- Answer:Angular語法糖省去C#宣告成員冗餘效果

2. #flashcards 
- Highlight:component內建一屬性用來處理商業邏輯
```
preViewData:PreviewModel;
selectValue:string;
```
- Question:在調用component內建屬性時，丟出Cannot set properties of undefined (setting 'ProdPolicyClauseId')
?
- Answer:C#WinForm邏輯Form、Form_Load相同，**成員都需實體化**避免預設null造成不可預期錯誤
```
ngOnInit(): void {

}
```

3. #flashcards 
- Highlight:衍生上述情境，用字串來接收combobox選取值
```
if(this.selectValue === '')
```
- Question:為何防呆無法條件無法成立
?
- Answer:同上若string無實體化default undefined
```
if(this.selectValue === undefined)
```

4. #flashcards 
- Highlight:父component click按鈕trigger子compoent，初始化如下:
```
ngOnInit() {
this.setFormGroup();
}
ngOnChanges() {
this.setFormValue();
}
```
- Question:為何click之後並將資料載入
?
- Answer:生命週期會順序ngOnChanges => ngOnInit

5. #flashcards 
- Highlight:父component click按鈕trigger子compoent
- Question:為了讓表單資料能載入改在constructor
```
    constructor() {
        this.setFormGroup();
    }
```
?
- Answer:能解決問題，但習慣配置constructor應用在DI

6. #flashcards 
- Highlight:在子component自行做測試資料模擬ngOnchange
- Question:為何無trigger onOnchage
?
- Answer:要模擬裝飾器修改值應改在父component

7. #flashcards 
- Highlight:在父component自行做測試修改裝飾器值trigger 子component ngOnchange
- Question:為何無trigger
?
- Answer:需特別注意trigger定義型別為**參考型別**如物件需重新new，下方無法triggr
```
this.premData.CommonInusModels.shift();
```
<!--SR:!2023-06-24,3,250-->

8. #flashcards 
- Highlight:
- Question:
?
- Answer:

