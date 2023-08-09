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
#知識 #work 

# Unify
- Input**共用資料**要特別注意異步特性
- 

1. #flashcards
- Highlight:父module.ts做一個下拉選單全部來源，後續在透過注入到子module.ts
```
@Input() dropdownInitData: InitDropdownData;
```
- Question:為何明明後端API是有資料的，將方法搬子module.ts呼叫service也是有值，但透過父module.ts呼叫service無值
?
- Answer:**異步**觀念，每個component呼叫時間不盡相同，可透過setTimeout處理，但若此componenet是透過其他user trigger因其delay時間夠久並不受影響


2. #flashcards
- Highlight:下拉選單共用子元件引入
- Question:Can't bind to 'action' since it isn't a known property of 'comirate-setting-query-form'.?
?
- Answer:子表單無declare component

3. #flashcards
- Highlight:問卷資料父component透過Input載入
- Question:If 'quote-question-form' is an Angular component and it has 'questionData' input, then verify that it is part of this module.
?
- Answer:主html有用Input屬性綁定，但子component成員內Input屬性名稱無對應到

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
- Highlight:有2個tab其中1個點擊按鈕修改狀態，另個tab也會跟著連動
- Question:用Input裝飾器設計讓2個tab共用同資料?
?
- Answer:違反裝飾器本身設計職責，Input為父這邊共用**讀取**資料來源，若要修改各別應用Output


6. #flashcards
- Highlight:
- Question:
?
- Answer:
