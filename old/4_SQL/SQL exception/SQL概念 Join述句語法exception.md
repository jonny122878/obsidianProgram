# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::3
Review::

#work #知識 
# Unify

1. #flashcards 
- Highlight:
- Question:
?
- Answer:

2. #flashcards 
- Highlight:
- Question:
?
- Answer:



# Exception

1. #flashcards 
- Highlight:LINQ
- Question:DataTable使用Join限制?
?
- Answer:
  - DataTable AsEnumerable表達和陳述式都不能用複合key
  - ex:on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }

2. #flashcards 
- Highlight:LINQ
- Question:陳述式left join中into含意?
?
- Answer:into為二張表交集所產出結果集合， 因此**多張表**就要有**多個into** 

3. #flashcards 
- Highlight:LINQ EF
- Question:為何需要用到Include用意在於
?
- Answer:二張資料表之間可透過建立ICollection屬性去做連結撈取，進而先將二張實體表載入，提升撈取效能


4. #flashcards 
- Highlight:
- Question:
?
- Answer:




## 關聯
- 疑惑點:原本SQL語句只有5句,處理後暴增為17句
- 情境:將INSERT SQL集合每列SQL用表格名去撈取對應SQL資料庫欄位屬性做處理,將INSERT SQL集合與SQL資料庫屬性集合做Join
- 判別:
  - Join首先要考量key會是一對一、一對多、多對多
  - 一對多情況通常情境是紀錄檔對基本檔,屬正常情況
  - 多對多通常就會有大量重複資料,像此種狀況因寫入單據資料(表身都是同張表格名),此種狀態就會變成乘積

- 

- There is already an open DataReader associated with this Command which must be closed first?
  - EF集合沒有用Extension讓其支援標準運算，ex:ToList() 

- 疑惑點:JOIN不出結果
- 情境:建立一個DB參數集合與UI元件集合要將二者關聯後UI值填入參數
- 判別:檢查後面是否有ToList之類實體化,此現象因LINQ有**延遲效果**

- 疑惑點:匿名型別無法用陳述式JOIN
- 判別:語法規範

- 疑惑點:在驗證時EXCEPT明明二者集合有差異但產出結果為0
- 情境:二個bool實值型別集合
- 判別:語法規範,預設不管參考與實值都要override,否則都為0



# 動作limit
## Structure
## Map
## Where
- [Where並無區分實值和參考型別，都會回傳一個實體化此型別，內容為空集合](######Where_NULL_ex)
- 再做if判別需特別考慮的情況
  - 字串型態上若有null則會發生和空字串不一致
  - 數字型態除了null又多了小數位取幾位的法則
- [FirstOrDefault 實值型別回傳仍是NULL](######FirstOrDefault_NULL_ex)
  - 自動初始化型別
  - KeyValuePair:struct實值型別，Key Value若是基本型別會自動初始化，反之則為null
  - int =0
  - bool = false
  - string exception為null
  - 可歸納說在FirstOrDefault狀況下，實值型別取決於元素而不是集合
- [FirstOrDefault 後面接屬性會exception](######FirstOrDefault_error_ex)
- [First 不論**實值**或參考型別集合回傳都是NULL，因此都會丟exception](######實值_參考_型別集合_ex)
- [FirstOrDefault](https://dotblogs.com.tw/initials/2017/08/31/224712)
## Zip

- DefaultIfEmpty()內參數都不放任何值?
  - default 產出一個Enumerable含有1個null element 
- KeyValuePair<string,string> KeyValuePair<Tuple<string,string>T> 無法join?
  - 此問題非引入命名空間原因，目前未知原因 
