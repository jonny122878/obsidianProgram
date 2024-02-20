# Metadata
Qty::3
Review::
Restructure::relation

### Think

調用componenet時與C# Controller無太大差異
使用時機:
- constructor:DI
- ngOnInit:一次性載入
- ngOnChanges:本身內部裝飾器會因其它component有異動時
- component生成trigger為html調用點
- ngOnChanges內部**條件式**判別狀態要思考到其所有被調用情況，否則條件式失效會造成不可預期錯誤
- ngOnChanges觸發條件要是實值而非物件參考變化，特別注意要被其他component調用方法不能直接指向
- DI時擅用語法糖
- [生命週期](https://ithelp.ithome.com.tw/articles/10231105)




1. #flashcards 
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

2. #flashcards 
- Highlight:父component click按鈕trigger子compoent
- Question:為了讓表單資料能載入改在constructor
```
    constructor() {
        this.setFormGroup();
    }
```
?
- Answer:能解決問題，但習慣配置constructor應用在DI

3. #flashcards 
- Highlight:
- Question:若無implements OnChange是否有會trigger ngOnChange
?
- Answer:也會trigger，差別在於有無override 自訂義方法

