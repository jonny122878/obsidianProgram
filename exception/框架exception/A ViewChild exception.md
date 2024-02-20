# Metadata
Qty::3
Review::
Restructure::relation

### Think

- Input**共用資料**要特別注意異步特性
- ViewChild key綁定
- ngOnChange:位置、順序、變化
  - 順序:裝飾器觸發之後會直接跳轉ngOnChange event，而不是所觸發函數繼續往下跑
  - 變化:裝飾器事件觸發規則是不能為參考型式、最後賦值要跟原本不同
  - 位置:要是外部傳入，內部直接修改不會觸發


1. #flashcards
- Highlight:
- Question:ViewChild can not read undefined setQueryId
?
- Answer:檢查發現ViewChild參數內要和html別名符號# 相同

2. #flashcards
- Highlight:
- Question:ViewChild 改值
?
- Answer:ngOnChange不會trigger

3. #flashcards
- Highlight:ngAfterViewInit
- Question: NG0100: ExpressionChangedAfterItHasBeenCheckedError: Expression has changed after it was checked. Previous value: ''. Current value: '[object Object]'.
?
- Answer:原因為原本ngOnChange已經呼一次 子ngAfterContentChecked,還沒載完又再次呼叫ngAfterContentChecked
- ngAfterContentChecked 其他組件ViewChild component
- ngAfterViewChecked DOM變更觸發
- [[https://mileslin.github.io/2017/08/Template-Driven-%E5%8B%95%E6%85%8B%E5%8A%A0%E5%85%A5%E9%A9%97%E8%AD%89%E5%B1%AC%E6%80%A7%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85/]]


