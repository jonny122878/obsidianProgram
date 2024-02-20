# Metadata
Qty::8
Review::
Restructure::relation、Qty

### Think


# Exception


1. #flashcards 
- Highlight:在子component自行做測試資料模擬ngOnchange
- Question:為何無trigger onOnchage
?
- Answer:要模擬裝飾器修改值應改在父component

2. #flashcards 
- Highlight:在父component自行做測試修改裝飾器值trigger 子component ngOnchange
- Question:為何無trigger
?
- Answer:需特別注意trigger定義型別為**參考型別**如物件需重新new，下方無法triggr，並且若用return物件時要重新弄一個，不能用指向
```
this.premData.CommonInusModels.shift();
return JSON.parse(JSON.stringify(this.queryData));
```


3. #flashcards
- Highlight:只單純想要用一個變數去觸發ngOnChange，但此裝飾器值不做任何運算
- Question:為何沒有觸發
```
this.isClose = null;
this.isClose = true;
```
?
- Answer:必須要子component值最後有所改變，ex:本來為true，那中途設成null，最後又設定true並不成立

4. #flashcards
- Highlight:目前開發component click button 來源從另外一個component抓取，click寫法如下
```
load:void
{
    this.loadClick.emit();
    console.log(this.thirdAddressQueryDatas);
}
```
- Question:為何裝飾器資料無刷新
?
- Answer:是會進行刷新，但是在ngOnChange

5. #flashcards
- Highlight:
- Question:若在component修改Input裝飾器值
?
- Answer:只會修改當下component外部Input和其他component都不會有變化

6. #flashcards
- Highlight:
- Question:目前調用component修改Input無觸發ngOnChange
?
- Answer:要異動Input要在傳入的component

7. #flashcards
- Highlight:問卷資料父component透過Input載入
- Question:If 'quote-question-form' is an Angular component and it has 'questionData' input, then verify that it is part of this module.
?
- Answer:主html有用Input屬性綁定，但子component成員內Input屬性名稱無對應到

8. #flashcards
- Highlight:
- Question:目前component不管如何調用都無法trigger
?
- Answer:html 無綁定 Input
