# Metadata
Qty::
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突



- Input**共用資料**要特別注意異步特性
- ViewChild key綁定
- ngOnChange:位置、順序、變化
  - 順序:裝飾器觸發之後會直接跳轉ngOnChange event，而不是所觸發函數繼續往下跑
  - 變化:裝飾器事件觸發規則是不能為參考型式、最後賦值要跟原本不同
  - 位置:要是外部傳入，內部直接修改不會觸發



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
- Highlight:只單純想要用一個變數去觸發ngOnChange，但此裝飾器值不做任何運算
- Question:為何沒有觸發
```
this.isClose = null;
this.isClose = true;
```
?
- Answer:必須要子component值最後有所改變，ex:本來為true，那中途設成null，最後又設定true並不成立


7. #flashcards
- Highlight:
- Question:ViewChild can not read undefined setQueryId
?
- Answer:檢查發現ViewChild參數內要和html別名符號# 相同

8. #flashcards
- Highlight:ngAfterViewInit
- Question: NG0100: ExpressionChangedAfterItHasBeenCheckedError: Expression has changed after it was checked. Previous value: ''. Current value: '[object Object]'.
?
- Answer:原因為原本ngOnChange已經呼一次 子ngAfterContentChecked,還沒載完又再次呼叫ngAfterContentChecked
- ngAfterContentChecked 其他組件ViewChild component
- ngAfterViewChecked DOM變更觸發
- [[https://mileslin.github.io/2017/08/Template-Driven-%E5%8B%95%E6%85%8B%E5%8A%A0%E5%85%A5%E9%A9%97%E8%AD%89%E5%B1%AC%E6%80%A7%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85/]]

9. #flashcards
- Highlight:
- Question:目前調用component修改Input無觸發ngOnChange
?
- Answer:要異動Input要在傳入的component

10. #flashcards
- Highlight:detail-fire-insu-work-paper、detail-add-insu-work-paper同時共用1個component(common-work-paper),import ok
- Question:The Component 'allEdit' is declared by more than one NgModule.
?
- Answer:解決方法必須將共用component多弄一個module,讓其他componenet註冊

10. #flashcards
- Highlight:
- Question:若在component修改Input裝飾器值
?
- Answer:只會修改當下component外部Input和其他component都不會有變化



11. #flashcards
- Highlight:
- Question:ViewChild 改值
?
- Answer:ngOnChange不會trigger