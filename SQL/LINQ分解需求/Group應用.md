- 情境:一張表格開頭序號有大小項,ex: 1.1、1.2、2.，若前面大項做完移除後要能重新排序
- 分析:
  - 重新排序需要OrderBy Map
  - 再搭配結構上階層式此時很適合用Group去Map
- 實作:
  - 先透過Group Order Map一次
  - 透過Select 再次Map因現在結構是一組組集合,要將集合內加入剛剛Group出結果
  - 最後將一組組集合做展開

### 創建新的集合
- Group補足key
- /為按排列區段分類
- %則是按排列區段元素位置

# 42C.LINQ

# 引入副程式
ex:NuGet、using.....
- using System.Linq;
- using System.Collections.Generic;(ToList...)
- using System;(Tuple)


# 動作解決問題情境
## Structure
load enumerable pk key sort where info 
### 參數之間模塊對應
- 將每個參數層轉換的參數弄成集合
- 將每個參數層用key給結合
- where條件為最開始輸入參數值
## Map
## Where
### where反向誤區
捨去代號和名稱為空白的，直覺代號 != "" && 名稱!= "" ,但因為where是取得所要的，所以只要其中一個空白就被捨去
### 字串欄位做到類似like效果
|指令|效果|
|:--|:--|
|StartsWith|開頭模糊|
|EndsWith|尾巴模糊|
|Contains|開頭結尾模糊|

### OfType解決型別上過濾的Where
## Reduce
### [合併成字串，ps:可用string.Join](######Aggregate_StringBuilder_ex)
## Zip
### [join多張表](left_join多張表.txt)
## Group
## Order
### 二個集合順序insert
  - 分解來源和來源處理
    - 將插入次序小於被插入集合總數給從大到小
    - 分解出插入次序大於被插入集合總數
    - 被插入集合型別轉換
  - 合併
    - 次序大於集合總數直接接合
    - 次序小於集合總數做插入 
## Function

# 動作指令語法
## Structure
- 在記憶體中的 List 資料不似在資料庫中那樣，這些資料是分散且沒有 Key，當資料量有百萬筆以上，使用 foreach 這類的 loop 一筆筆比對，會執行到天荒地老。
- 轉換字典
  - 宣告Key的覆寫比較物件
  - 來源結構轉字典要注意重複Key的問題
  - 字典建構式要注意比較物件
- [提煉LINQ判別OrderBy與OrderByDescending](######OrderBy與OrderByDescending)

## Map
## Where
## Reduce
- Aggregate可以想成是迴圈跑總加，將抽象骨幹：遍歷的當前、下個元素、產出結果。
- StringBuilder是描述current型態
## Zip
- Union 和SQL移除重複
- Intersence
- Except
- ContainsKey
1234
2345做範例
### [陳述式寫inner left join](######inner_left_join_ex)
### [SelectMany寫CROSS JOIN](######SelectMany_cross_join_ex)
## Group
- 和SQL主要差別在於因為LINQ每個方法架構本身都具有投射功能，因此調用時是要建立在Group投射之後再Select投射新的
- Group投射之後變成原本的集合(要用lambda調用)但是集合的都會增加Key欄位並原本集合按照Key分成多個子集合
- 若要達到SQL中的SUM + GROUP 先用GROUP 將集合分類再將分類的集合轉成單一的集合關係值
- Group之後出來的集合是原本的集合加上一定會帶有Key屬性需要再用Select去將之轉換
- LINQ Group By有點是分組而不是移除重復
### [匿名型別解決group_many_key](######Group_many_key_ex)
## Order
- 函式簽名由大小是否覆寫比較方法
  - OrderByDescending
  - OrderBy
- [Rank:帶有類別尺度其排的順序尺度和集合屬性數量有關](https://riptutorial.com/csharp/example/12481/select-with-func-tsource--int--tresult--selector---use-to-get-ranking-of-elements)
- [ntile:衍生Rank多了等距再去做分割](https://riptutorial.com/csharp/example/12481/select-with-func-tsource--int--tresult--selector---use-to-get-ranking-of-elements)
## Function
## Override
- 當再調用參考型別時，和實值型別定義不再於值的相等，而是再於指標指向是否為同個，因此再使用LINQ一些相關動作時，需要override
- 比較
  - 是否相等IEqualityComparer
  - 是否大小等於(延伸可比順序大小)IComparer
  - Order若順序尺度為同次序則按照原本元素次序去比較大小
  - 同個集合可依據不同規則寫多個Compare
  - IEnumerable:撈回來本地再過濾(還要一直做處理用IEnumerable)
  - IQueyable:遠端就做過濾(一次性的就用IQueryable)






###### OrderBy與OrderByDescending
- 觀察LINQ擴充方法原型
```
public static IOrderedEnumerable<BookIndexViewModel> OrderByOrDescending<TKey>(this IEnumerable<BookIndexViewModel> lists, Func<BookIndexViewModel, TKey> func, bool isAsc)
        {
            if (isAsc)
            {
                return lists.OrderBy(func);
            }
            else
            {
                return lists.OrderByDescending(func);
            }
        }
```




###### foreach_Dict_ex
```
 foreach (KeyValuePair<int, string> kvp in productsDictionary)
            {
                Console.WriteLine("Key : " + kvp.Key + " Value : " + kvp.Value);
            }
```

###### ToDictionary_ex
```
var authorityDict = authoritys.Select((row,index) =>
                new Tuple<int, Authority>(index, row)
                ).ToDictionary(
                ele => 
                        new SectionBuild 
                        {
                            登記次序 = ele.Item2.登記次序,
                            地段 = ele.Item2.地段,
                            建號 = ele.Item2.建號,
                        }
            ,ele => ele);
```

###### foreach_Lookup_ex
```
    foreach (IGrouping<char, string> packageGroup in lookup)
    {
        // Print the key value of the IGrouping.
        Console.WriteLine(packageGroup.Key);
        // Iterate through each value in the IGrouping and print its value.
        foreach (string str in packageGroup)
            Console.WriteLine("    {0}", str);
    }
```


###### Group_many_key_ex
```
var query = db.titles
	.GroupBy(x => new { x.pub_id, x.type })
	.Select(g => new { keys = g.Key, cnt = g.Count() });
```

###### Aggregate_StringBuilder_ex
```
var bnakInfo = row.Aggregate(                    
new StringBuilder(),
(current, next) =>
current.Append(next).Append(", ")).ToString() 
).ToList();     
```


###### SelectMany_cross_join_ex
```
var insertSQLs = frtInsertSQLs.SelectMany(inner => afrInsertSQLs
            ,(inner,outer) => inner + outer ).ToList();
```

###### FirstOrDefault_error_ex
```
            var name = this._dbContext.MemberModels.FirstOrDefault(r => 
            r.MemberGmail == loginViewModel.Email &&
            r.MemberPassword == loginViewModel.Password
            ).MemberName;

```



###### GroupJoin_ex
- DefaultIfEmpty撈取時前面要處理成實值
- 後面可接First前面DefaultIfEmpty
```
var dicts = new Dictionary<string,Tuple<string,bool>>();
this.gv_master.Columns.Cast<DataGridViewColumn>().GroupJoin(dicts,
                inner => inner.Name,
                outer => outer.Key,
                (inner, outer) => 
                {
                    var display = outer.Select(c => c.Value.Item2).DefaultIfEmpty(true).First();
                    var title = outer.Select(c => c.Value.Item1).DefaultIfEmpty("").First();
                    
                    inner.Visible = display;
                    if(title != "")
                    {
                        inner.HeaderText = title;
                    }                    

                    return inner;
                }).ToList();
```

###### Where_NULL_ex
```
var listNums = new List<int> {1,2,3 };
var listForms = new List<Form1> { new Form1()};

var whereNums = listNums.Where(r => r == 4).ToArray();//not element
var whereForms = listForms.Where(r => r.Name == "test").ToArray();//not element

var whereNumArrs = listNums.Where(r => r == 4).ToArray();//not element
var whereFormArrs = listForms.Where(r => r.Name == "test").ToArray();//not element
```


###### FirstOrDefault_NULL_ex
```
var lists = new List<int> {1,2,3 };
var arrs = new int[] {1,2,3 };
var dicts = new Dictionary<int, Form1>();
dicts.Add(1,new Form1());
dicts.Add(2,new Form1());
dicts.Add(3,new Form1());

var listFirstOrDefault = lists.FirstOrDefault(r => r == 4);//return 0
var arrFirstOrDefault = arrs.FirstOrDefault(r => r == 4);// return 0
var dictFirstOrDefault = dicts.FirstOrDefault(r => r.Key == 4);//return 0,null
```


###### 實值_參考_型別集合_ex
```
var lists = new List<int> {1,2,3 };
var arrs = new int[] {1,2,3 };
var dicts = new Dictionary<int, Form1>();
dicts.Add(1,new Form1());
dicts.Add(2,new Form1());
dicts.Add(3,new Form1());

var listFirst = lists.First(r => r == 4);//exception
var arrFirst = arrs.First(r => r == 4);//exception
var dictFirst = dicts.First(r => r.Key == 4);//exception
```

###### inner_left_join_ex
```
        var innerQuery = from inner in test1s
                         join outer in test2s
                         on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }
                         select inner;

        var leftQuery = from inner in test1s
                        join outer in test2s
                        on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }
                        into test3s
                        select new { inner,test3s };
```









### LINQ Reduce
``` dt.AsEnumerable().GroupBy(r => r.Field<string>("StockID")).Select(r => new {
ID = r.Key,
AMT = r.SUM(e => e.Field<decimal>(Y_ACU_AMT))
});
```
### 複合key
```
var query = db.titles
	.GroupBy(x => new { x.pub_id, x.type })
	.Select(g => new { keys = g.Key, cnt = g.Count() });
```
### StringBuilder
```
var bnakInfo = row.Aggregate(                    
new StringBuilder(),
(current, next) =>
current.Append(next).Append(", ")).ToString() 
).ToList();
```

###### 陳述式join_example
```
var queryStocks = from stock in excelStockes
                  join date in excelDateTimes
                  on stock.Key equals date.Key
                  select new StockPricePoint 
                  { 
                    ID = stock.Value.ID,
                    Name = stock.Value.Name,
                    SeasonMonth = date.Value,
                    Price = stock.Value.Price                                 
                  };
```
###### 陳述式group_example
```
var queryGroups = from stock in stocks
                  group stock by stock.SeasonMonth into g
                  select new 
                  { 
                    Key = g.Key,
                    Values = g.Select(c => c).ToList()                                  
                  };   
```




### 比較_example
- inherit要將所有泛型替換成要較物件
- class HistComparer:IEqualityComparer<T>
- bool Equals(T x,T y) 此處主要override邏輯
- int GetHashCode(T obj); 此處inherit父類
- 固定寫 return base.GetHashCode();
```
public class CreditModel
        {
            public string Table { get; set; }
            public string Date { get; set; }
            public string Department { get; set; }
            public string GoodsID { get; set; }
            public string GoodsName { get; set; }
            public string Credit { get; set; }
            public string Comment { get; set; }
        }
        public class CreditNameCompare : IEqualityComparer<CreditModel>
        {
            public bool Equals(CreditModel x, CreditModel y)
            {
                var isEqual = false;
                if(x.Table == y.Table && x.GoodsID == y.GoodsID)
                {
                    isEqual = true;
                }
                return isEqual;
            }

            public int GetHashCode(CreditModel obj)
            {
                return base.GetHashCode();
            }
        }
        public class CreditModelCompare : IEqualityComparer<CreditModel>
        {
            public bool Equals(CreditModel x, CreditModel y)
            {
                var isEqual = false;
                

                //PK識別:Date、GoodsID
                if (x.Table == y.Table &&
                    x.Date == y.Date &&
                    x.GoodsID == y.GoodsID &&
                    x.Credit == y.Credit
                    //先test 全部feature
                    && x.Department == y.Department
                    && x.GoodsName == y.GoodsName  
                    )
                {
                    isEqual = true;
                }
                return isEqual;
            }
            public int GetHashCode(CreditModel obj)
            {
                return base.GetHashCode();
            }
        }
        public class TestCreditModelCompare : IComparer<CreditModel>
        {
            public int Compare(CreditModel x, CreditModel y)
            {
                var dicts = new Dictionary<string, int>();
                dicts.Add("債券", 1);
                dicts.Add("財務", 2);
                dicts.Add("承銷", 3);
                dicts.Add("股自", 3);

                var std = dicts.First(r => r.Key == x.Department).Value;
                var cmp = dicts.First(r => r.Key == y.Department).Value;
                if (std == cmp)
                {
                    return 0;
                }
                else if (std > cmp)
                {
                    return 1;
                }
                else
                {
                    return -1;
                }
            }
            public int GetHashCode(CreditModel obj)
            {
                return base.GetHashCode();
            }
        }    
    
```   

    
