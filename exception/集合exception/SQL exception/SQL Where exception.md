# Metadata
Qty::3
Review::
Restructure::

### Think



# Exception



1. #flashcards 
- Highlight:MS-SQL附件檔案要搬移，需要針對單號欄位編碼移動位置判別，但有的單號為空白
- Question:解法方式想要寫法精簡，透過短路式先行判別長度後後在截斷字串
```
len > ... substring ...  //或是
WHERE IS NOT NULL <> ''
```
?
- Answer:
- MS-SQL計算原理為先計算一層後，在透過此層在前推一層，而不是二個條件推一層
ex:
100 => LEN() >  => 10 => substring => 5
按照如上原理，因無過濾因此還是丟exception

2. #flashcards 
- Highlight:MS-SQL
- Question:Where條件式整數與小數做比較return?
?
- Answer:小數位需指定到確切位數，否則不成立
  - ex 65.42 < 65 exception
  - 65.42 < 65.00

3. #flashcards 
- Highlight:在Oracle中，主表JOIN副表取得相關資訊，並用WHERE條件
- Question:Invalid parameter binding Arg_ParamName_Name
?
- Answer:WHERE述句欄位前面並無表格別名修飾，導致無法辨識
```
strSql += @" AND a.nc_prod_policy_clause_id = :a.nc_prod_policy_clause_id "; ok

strSql += @" AND nc_prod_policy_clause_id = :nc_prod_policy_clause_id "; error
```

