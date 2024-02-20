# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::
Review::

#知識   #work #py 
# Unify
- 物件概念都與C#雷同，深拷貝可擅用語法糖或JSON函數
- 物件實體化時小心C#null直覺概念
- 集合和lambda型別都用**右側符號**表達
- 集合用右側符號區分
- 型別註記使用時機當型別推論會出現**any型別**
- never表示函數return 可能會無窮導致中斷情況
- 允許any存在時機，I/O或JSON.prase() return這種有無限多種情況
- unknown優化any，讓其被第一次any指定後不能再被指定
# 語言存在環境特性?
## 環境
- 解決js弱型別特有Type Annotation(型別推論機制)
- tsconfig.json設定翻譯成javascript相關參數
  - experimentalDecorators 是否允許裝飾器
  - strictNullChecks
## 調用特別注意bug
- 雖然每個型別都有規範，但還是要特別注意防呆型別
## 未知思路

# 型別機制
## 轉型衝突
- 型別推論:右側值去決定變數型別
- 型別註記:變數不指定初始值直接宣告變數型別
- [[variant exception]]
## 特有型別
- null、undefined並無透過強型別統一弄成只有null
```
undefined:this.questionData = <QuestionModel>{};
this.questionData = <QuestionModel>
{
	quoteQuestionId:2,
};
```
主要差別在於物件初始化若無指定屬性是**undefined**，且要特別小心後續針對此物件屬性條件式判別
- void本質上來說也是一種型別

# 變數、集合、條件、迴圈、函式、事件基礎元素所對應語法?
## 變數
- 物件declare時，和C#概念相同，理解實體化錯誤就會丟出Cannot read properties of undefined (reading 'push')
```
let arr :SmSaveProdCommiRateDModel[];
IEnumerable<SmSaveProdCommiRateDModel> arr;
let arr :SmSaveProdCommiRateDModel[] = [];
IEnumerable<SmSaveProdCommiRateDModel> arr = new List<SmSaveProdCommiRateDModel>;
```
- 物件深拷貝有語法糖可利用,若超過一層以上要用JSON 格式的序列化和反序列化來執行深拷貝
```
queryKey: SmCommonQueryModel;
query(queryKey: SmCommonQueryModel): void {
        this.queryKey = { ...queryKey};
 }
 let amtfObj = JSON.parse(JSON.stringify(r.amtConfig));
```
- 因為集合都用符號表達，因此用字典與其屬性對應物件
```
    addresses:SelectItemModel[] =
    [
        { value: '0', text: '00', title: '00' },
    ];
```
- 類似C# Tuple
```
models:[string,string][] = [];
this.models.push([valAddress,valScope]);
```
- 類C# Dictionary
```
const group:Map<number,SmSaveProdCommiRateDModel[]> = new Map<number,SmSaveProdCommiRateDModel[]>();
group.has(item.addRate)
group.set(item.addRate,arr);
group.get(item.addRate).push(item);
```
## 集合
- 引入C#語法與原生javascript對集合操作做合體，調用時不用function用**lambda**
```
selected.some(it => this.selected.indexOf(it) == -1)
```
- 衍生變數函數簽名一樣直接用lambda符號表達即可
```
t(p1:(t1:number) => {}):void
{
}
```
## 條件
## 迴圈
## 函式
## 事件

# 原生功能體現環境特性?


