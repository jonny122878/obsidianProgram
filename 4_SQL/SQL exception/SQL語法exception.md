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
#資料 #金財通 
# Unify




1. #flashcards 
- Highlight:MS-SQL接手別人寫aspx程式時，使用者反應並資料寫到資料庫，但當下看INSERT語句也看不出所以然來
- Question:insert into table values ()出現錯誤
?
- Answer:將程式Prase SQL貼到MS-SQL後，發現是**直覺理解**有問題，若不打欄位情況下每個欄位值都必須要塞值

2. #flashcards 
- Highlight:Oracle中組合SQL like條件，其架構為Dapper去組合解決SQL Injection
```
var parm = new DynamicParameters(dicParm);
var results = access.QueryList<DmCommonPolicyClauseInfoModel>(strSql, parm);
```
- Question:丟出錯誤
?
- Answer:Oracle中SQL不能直接copy要做一些格式相關處理
```
like '%' || :keyWord || '%' 。ok 
CLAUSE_NAME_ENG like '%1%' 。no
strSql += @" AND APPROVE_NO like '%' || :approveNo || '%' \n "; 。no
```

4. #flashcards 
- Highlight:Oracle用Dapper將組出來SQL方便瀏覽，加入換行符號
- Question:丟出錯誤
?
- Answer:不能像MS-SQL加入換行符

5. #flashcards 
- Highlight:Dapper操作Oracle用SQL撈取後填入DTO
- Question:看起來筆數並沒有邏輯錯誤，數量為正確，但所對應欄位都是空值
?
- Answer:檢查SQL中述句SELECT，需要弄As別名讓其和DTO屬性欄位一致

6. #flashcards 
- Highlight:
- Question:Dapper操作Oracle若Select述句投射欄位並DTO屬性，是否會exception
?
- Answer:直覺思考別名無對應到跟無投射欄位是同樣情況，因此不會exception

7. #flashcards 
- Highlight:MS-SQL撰寫預存程序
- Question:丟出訊息:在有預期條件內容指定非布林運算式,接近BEGIN
?
- Answer:IF條件式沒寫好，在MS-SQL為成對式
```
IF 
BEGIN
END
```

8. #flashcards 
- Highlight:MS-SQL撰寫函數
- Question:丟出訊息:在函式中使用副作用運算子,'INSERT EXEC' 無效
?
- Answer:函式本身只能是純函式,不能有**副作用**，ex:調用預存程序修改其他表

9. #flashcards 
- Highlight:Oracle中進行主表JOIN副表取得資訊細節後ORDER BY
- Question:'ORA-00904: "BUSINESS_CD_NAME": 無效的 ID'
?
- Answer:檢查後發現ORDER BY述句並無此欄位名，值得一提可用**As別名**去調用

10. #flashcards 
- Highlight:MS-SQL撰寫預存程序挖空參數
- Question:當SQL要改成用string取組合時,單引號exception
?
- Answer:'''' + 'string' + '''' ,等於**單引號特殊符**區別''''


11. #flashcards 
- Highlight:MS-SQL撰寫預存程序要將計算表格放入變數
- Question:除非同時指定了TOP、OFFSET或FOR XML，否則ORDER BY在檢視表、內建函式、衍生資料表、子查詢及通用資料表運算式中均為無效
?
- Answer:可用直覺式思考，因ORDER BY主功能為投射給使用者呈現，若在上述情境等於耗效能而無任何成果

12. #flashcards 
- Highlight:在Oracle中，主表JOIN副表取得相關資訊，並用WHERE條件
- Question:Invalid parameter binding Arg_ParamName_Name
?
- Answer:WHERE述句欄位前面並無表格別名修飾，導致無法辨識
```
strSql += @" AND a.nc_prod_policy_clause_id = :a.nc_prod_policy_clause_id "; ok

strSql += @" AND nc_prod_policy_clause_id = :nc_prod_policy_clause_id "; error
```


13. #flashcards 
- Highlight:Oracle調用Select語句
- Question:Oracle中Select述句表格名稱有null?
```
from FUN_GET_INS(null) 
```
?
- Answer:Oracle中調用函數語法可以和撈取表格相同，null表示參數

14. #flashcards 
- Highlight:在Oracle SQL Developer中調用SQL語句
- Question:明明資料庫訊息已經呈現刪除筆數完畢，用EF撈取卻還有資料?
?
- Answer:在Oracle SQL Developer要**確認變更**

15. #flashcards 
- Highlight:AP表格在user剛載入時希望只有表頭,表身無資料
- Question:SELECT '' As,'' As 為了讓gridview撈出有標題,不進行 FROM實體表格撈取
?
- Answer:.直覺下是沒有撈出任何東西,但實際logic其實為1筆,SQL本身有聚合特性[[SQL抽象查詢]]

16. #flashcards 
- Highlight:AP在建檔寫入資料時丟出**資料行數量<欄位數**訊息
- Question:訊息判別是組合SQL字串時出了問題
?
- Answer:從數量這個線索可以推估，在AP使用者互動框內含有,或'特殊符號，INSERT INTO子句會變成多個欄位

17. #flashcards 
- Highlight:
- Question:
?
- Answer:






- 情境:Where條件式整數與小數做比較return?
  - 小數位需指定到確切位數，否則不成立
  - ex 65.42 < 65 exception
  - 65.42 < 65.00


- 情境:UPDATE INNER JOIN 副表與主表為1-M關係,其會如何替換?
- 判別:只替換M數量表格第一筆

- 情境:UPDATE INNER JOIN 副表A 100 副表B 105 主表其會如何替換?
- 判別:最後表B為數量基準

- 情境:Select中WHERE陳述式放在子查詢,與放在JOIN外層差異?
- 判別:放在外層是已經產生JOIN結果在WHERE過濾,二者看起來相同,但實際執行會有數量不同情況

- 情境:UNION產出資料不如預期?
  - 檢查再做接合時SELECT FROM後面不要有其他關鍵字
  - 檢查接合表格是否有重複資料



## Group
- 若要分組有依據日期年度但欄位為日期型態有辦法放在Group陳述內?
  - 因日期函數return為單一值因此放此處不影響
- 資料行 '...' 在選取清單中無效，因為它並未包含在彙總函式或 GROUP BY 子句中?
  - 因SQL Group無帶有投射性質，需注意Select與Group陳述式欄位數量一致 
