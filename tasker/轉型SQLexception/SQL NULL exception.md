# Metadata
Qty::2
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突




1. #flashcards 
- Highlight:在MS-SQL中PROCEDUCE移轉到MTB01單位是以批覆書,但單張披覆書對應法人會有多個**1-M**關係,因此透過CURSOR+UPDATE方式將欄位串接
ex:法人1+法人2....
- Question:轉出來結果有些欄位明明是對應法人,但其產出NULL
?
- Answer:原因1張批覆書對應3個法人,但是其中**1位法人NULL**,任何型態+NULL=NULL

2. #flashcards 
- Highlight:Oracle中decimal欄位允許NULL
- Question:檢查Oracle結構是允許NULL，且Dapper結構也為decimal?不知為何跳出不允許NULL訊息
?
- Answer:直覺錯誤，NULLABLE、DATA_DEFAULT ，要以**NULLABLE**為主


5. #flashcards 
- Highlight:
- Question:
?
- Answer:

