# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::8
Review::


#知識   #work 
# Unify
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
- Answer:需特別注意trigger定義型別為**參考型別**如物件需重新new，下方無法triggr，並且若用return物件時要重新弄一個，不能用指向
```
this.premData.CommonInusModels.shift();
return JSON.parse(JSON.stringify(this.queryData));
```

8. #flashcards 
- Highlight:ngOnChange先去db去載入設定檔轉成UI畫面之後,在去db撈存取資料填值
- Question:明明資料庫都有值,但沒有載入出資料
?
- Answer:不能將其寫不同個subscribe，因為非同步若撈取值先載入就無法填入

9. #flashcards 
- Highlight:
- Question:
?
- Answer:

