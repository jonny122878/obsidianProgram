# 封裝
## 提煉類別
- 內部欄位是否會有沒考量到方法調用
- 建構式用來將欄位的每個值給初始化，儘量不要再欄位實體而是在建構式，因為你不知道是否有耦合沒實體化的。
- 命名空間檢查，是否internal取代public
- 除非有十足把握不然不要去封裝**溝通層**(Controller)
- 檢查是否有成功解耦:xml層注入到Model層，Model再注入到商業邏輯，這之中如如果xml有更動再Model層沒有做任何刪除結構的動作，運行都要是正常的
- OOP本身帶有記錄狀態的特性，使用時要注意**狀態**是否被改變，或沒初始化
- 其背後是指令式編程帶有順序特性，因此**順序**非常重要，要注意使用的時候有沒有**被注入**
## 實體化物件
- 傳入null不會exception
- SqlCommand command = new SqlCommand(selectSQL, con);
- Form屬性注入要在ShowDialog()之前
```
Form2 from2 = new Form2();
from2.BindingSource = this.bindingSource2;
from2.ShowDialog();
```
- inherit interface get null throw override error (需要用內部欄位處理此問題)
- class宣告屬性若無用內部欄位也有null情況
- LINQ極端值情境若前面為0則後面method不會作動
```
var input = new List<int> { };
var test = input.GroupBy(r => r).Select(r => r.First()).ToList();
```
