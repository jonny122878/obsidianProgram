---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
#資料 
# Unify

# 語言存在環境特性?
## 環境
## 調用特別注意bug
## 未知思路

# 型別機制
## 轉型衝突
- [[C轉型exception]]
- [[C語法exception]]
- [型態之間比較as,switch](https://blog.xuite.net/hsiung03/blog/63883241#)
## 特有型別
- [[DataTable參考型別理解錯誤]]

# 變數、集合、條件、迴圈、函式、事件基礎元素所對應語法?
## 變數
## 集合
## 條件
## 迴圈
## 函式
## 事件

# 原生功能體現環境特性?




## 語言存在環境特性?
- 最小單位為class
## 語言型別衝突呈現:如何declare?、exception所丟出?


## 變數、條件、迴圈、函式四大基礎所對應語法?
## 變數(含結構體)
- 變數名稱不能有如下符號:-、 
- new初始化**字典**建構子
```
var dict = new Dictionary<string, string>() 
{ 
    ["A"]="test1",
    ["B"]="test2",
};
```
- get、set屬性選取器是可以再用private去修飾
- **byte** array 職責存**圖片、影片**等...

## 廻圈
## 條件
- [NULL物件調用,型別符號處理](https://www.dotblogs.com.tw/MemoryRecall/2021/07/25/172410)
## 函數
- [event](https://ithelp.ithome.com.tw/articles/10075114)
- event解壓縮對照
  |enum|Keys對照||
  |:---|:---|:---|
  |KeyPress|KeyPressEventArgs|e.KeyChar == (char)Keys.Enter|
  |KeyDown|KeyPressEventArgs|KeyAscii == Convert.ToDecimal(Keys.Escape)|
- partial修飾子協同開發
## 原生功能體現環境特性?







# limit
## 特性
## 分隔符
## 型別(含轉型)
- namespace想增加可讀性不用刮弧寫法?
  - 陳述式，ex:namespace a1.Controllers;
- 屬性類別要運算簡化寫法?
  - lambda，ex:public int TemperatureF => 32 + (int)(TemperatureC / 0.5556); 
- 匿名型別使用時機?
  - 具有參數的**唯讀性**，僅調用此區塊**一次性**
    ```
    var query = new [] {
    new { test = "test" },
    new {},
    };
    ```
- object and dynamic都是弱型別差異是?
  - dynamic初始化後設定還可以再做變動(做到真正弱型別語言特性)
- object as int;丟出exception?
  - 因變數為物件不是實質型別，後面加?inherit Nullable
- DBull本身何無法進行比較或轉型?
  - 因其本身也是與object同等類型弱型別，只是其是模擬DB
  - ex:轉型
   ```
    ~~object a = DBNull.Value;~~
    ~~var str = (int)a;~~
    ```
   - ex:比較
   ```
    object ob = "";
    ~~string str = "";~~
        if(ob == DBNull.Value)
    {

    }
    ```
- DBNull是否可ToString()
  - 就像object一樣所有型別都能轉字串 
- 泛型介面該如何繼承?
  - 再三角框內填類別即可
    ```
    public interface IRepository<T>  
    public class MemberRepository : IRepository<Member>
    ```
- 泛型類別實作泛型介面一樣用T即可
  ```
  public class MockRepository<T> : IRepository<T> where T : Member
  ```
- 碰到結構上類別名稱相同該如何調用?
  - 類似函式簽名一樣，雖然名稱相同但泛型參數不同
  - 調用時三角形內型別注入即可調用並能使用父類的屬性 
    ```
    var result = new Adapter<IEnumerable<MemberModel>>();
    public class Adapter
    {
        public string ResCode { get; set; }
        public string ResMsg { get; set; }
    }
    public class Adapter<TModel> :Adapter
    {
        public TModel Model { get; set; }
    }
    ```
- readonly、const區別再於?
  - const其解決需求就是指定一個不可變常量做運算用、指定**參考型別**是不允許 
  - readonly其用來副程式注入，用來調用而不做修改，不能在**建構子外**做實體化
## 變數
- DataTable讀取出來變數無法有提示字元並調用其功能?
  - 需特別轉強型別才能調用其型別功能
   ```
    var date = (DateTime)base.deleteParam.Rows[base.deleteParam.DeleteCellY][base.deleteParam.DeleteCellX];
    ```
- 再調用LINQ時想將lambda內函數在外部計算確無法?
  - lambda內部函式變數作用域封閉性，不對外共享
## 結構集合
- using可用來限制變數作用域，使用時機為?
  - 使用**有限資源**時(如檔案、資料庫連線、記憶體等)，確保使用完後立即釋放該資源，避免佔用
  - ex:[using](######using_ex)
- try-catch中try變數不能被catch調用?
  - 因其有作用域，因此需在最開頭宣告 
  - [try-catch作用域](######try_catch_ex)
## 廻圈
- foreach集合為空是否需寫判斷式解決exception?
  - 因其集合非null會跳過不做展開 
## 條件
## 函數
- 調用函數時想用其功能，但回傳值用不到，需要隨便宣告1個變數接收?
  - return value在調用時可以不接收return 
- 在WinForm建立一個按鈕，其同時也產生event?
  - 事件是被掛載的，不是天生就自帶的(觀察者模式)
  ```
  private void txtHWB_Validated(object sender, EventArgs e)
    {
    }
    this.txtHWB.Validated += new System.EventHandler(this.txtHWB_Validated);
  ```
- 按鈕再注入到副程式類別中按鈕，event無效果?
  - 參考物件的指向並不會將事件一起綁定過去，它們是分離的，假如你要將按鈕指定到另個按鈕，你要做的不只是指定按鈕，你還要再事件中指定要掛載的函式。
- event中sender表示甚麼?
  - 類似擴充方法傳遞自己，ex:click button return button，select combobox return combobox 
  


###### try_catch_ex
```
SqlTransaction tran = this.sqlConnection.BeginTransaction();
            try
            {
                SqlCommand cmd = new SqlCommand(strSQL, this.sqlConnection);                
                cmd.ExecuteNonQuery();
                tran.Commit();
            }
            catch (Exception ex)
            {
                tran.Rollback();
                this._err = ex.Message;
            }
            finally 
            {
                this.sqlConnection.Close();
            }
```
###### using_ex
```
using (var transaction = connection.BeginTransaction())
{
    var command = connection.CreateCommand();
    command.CommandText =
    @"
        INSERT INTO data
        VALUES ($value)
    ";

    var parameter = command.CreateParameter();
    parameter.ParameterName = "$value";
    command.Parameters.Add(parameter);

    // Insert a lot of data
    var random = new Random();
    for (var i = 0; i < 150_000; i++)
    {
        parameter.Value = random.Next();
        command.ExecuteNonQuery();
    }

    transaction.Commit();
}
```



###### object_c_ex






