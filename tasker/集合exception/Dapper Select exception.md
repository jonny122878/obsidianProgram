# Metadata
Qty::6
Review::
Restructure::relation、summary

#work #資訊 
# Unify

## 本質

## 衍生衝突


# Exception


1. #flashcards 
- Highlight:Oracle
- Question:將組出來SQL方便瀏覽，加入換行符號丟出錯誤
?
- Answer:不能像MS-SQL加入換行符

2. #flashcards 
- Highlight:Oracle
- Question:Dapper操作Oracle若Select述句投射欄位並DTO屬性，是否會exception
?
- Answer:直覺思考別名無對應到跟無投射欄位是同樣情況，因此不會exception

3. #flashcards 
- Highlight:Dapper操作Oracle用SQL撈取後填入DTO
- Question:看起來筆數並沒有邏輯錯誤，數量為正確，但所對應欄位都是空值
?
- Answer:檢查SQL中述句SELECT，需要弄As別名讓其和DTO屬性欄位一致

4. #flashcards 
- Highlight:EF、Dapper
- Question:原本EF update寫法更新效率太慢，換成Dapper後發現有的欄位無正常更新
?
- Answer:EF一次都是更新整個物件，Dapper則是Update語句更新指定欄位，因此發生遺漏情況

5. #flashcards 
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

6. #flashcards 
- Highlight:Oracle中decimal欄位允許NULL
- Question:在Dapper底下不能調用DBNull.Value?
?
- Answer:語法誤區
```
RateAAg = (r.RateAAg.HasValue) ? r.RateAAg.Value : DBNull.Value, //error
RateAAg = (r.RateAAg.HasValue) ? r.RateAAg.Value : null, //ok
```
