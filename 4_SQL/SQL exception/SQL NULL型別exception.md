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
Topics::SQL
#資訊 #金財通 

# Unify


1. #flashcards 
- Highlight:使用者在調用佣金明細參數，可以允許參數為數字或空白
- Question:EF進行撈取時丟出Column contains NULL data，但用EF寫入又無問題
?
- Answer:問題出在class前Attr
```
[Required]
```

2. #flashcards 
- Highlight:在MS-SQL中PROCEDUCE移轉到MTB01單位是以批覆書,但單張披覆書對應法人會有多個**1-M**關係,因此透過CURSOR+UPDATE方式將欄位串接
ex:法人1+法人2....
- Question:轉出來結果有些欄位明明是對應法人,但其產出NULL
?
- Answer:原因1張批覆書對應3個法人,但是其中**1位法人NULL**,任何型態+NULL=NULL

3. #flashcards 
- Highlight:Oracle中decimal欄位允許NULL
- Question:檢查Oracle結構是允許NULL，且Dapper結構也為decimal?不知為何跳出不允許NULL訊息
?
- Answer:直覺錯誤，NULLABLE、DATA_DEFAULT ，要以**NULLABLE**為主

4. #flashcards 
- Highlight:Oracle中decimal欄位允許NULL
- Question:在Dapper底下不能調用DBNull.Value?
?
- Answer:語法誤區
```
RateAAg = (r.RateAAg.HasValue) ? r.RateAAg.Value : DBNull.Value, //error
RateAAg = (r.RateAAg.HasValue) ? r.RateAAg.Value : null, //ok
```


5. #flashcards 
- Highlight:
- Question:
?
- Answer:

