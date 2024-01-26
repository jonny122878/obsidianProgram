# Metadata
Qty::5
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突


# Exception


1. #flashcards 
- Highlight:C#、EF
- Question:將資料讀出後,發現EF物件並無將關聯class讀出
?
- Answer:將其想成關聯式資料庫若要讀多張表要用Include

2. #flashcards 
- Highlight:
- Question:將共通查詢邏輯封裝成小函數調用private IQueryable,從資料庫撈取資料但怎麼撈都逾時
?
- Answer:有點類似非同步,內外之間調用點會相互影響,Iqueryable延遲特性不能內外調用,一定要ToList

3. #flashcards 
- Highlight:EF
- Question:能否再調用撈出物件
```
var quest = uow.Repository<QuoteQuestion>().GetAll().Where(x => x.QuoteMainId == quoteQuestionModel.QuoteMainId).ToList();
context.Entry(data).State = EntityState.Deleted;
context.SaveChanges();
```
?
- Answer:物件參考特性無法調用

4. #flashcards 
- Highlight:EF
- Question:在IQueryable Enumerable內調用自己封裝函數
The client projection contains a reference to a constant expression of 'BankPro.ComlFire.Service.Domain.Managers.Appraisal.AppraisalQuery.AppraisalInstallmentService' through the instance method 'ConvertToRoc'. This could potentially cause a memory leak; consider making the method static so that it does not capture constant in the instance
?
- Answer:IQueryable為在資料庫操作非記憶體內，因此無實體

5. #flashcards 
- Highlight:使用者在調用佣金明細參數，可以允許參數為數字或空白
- Question:EF進行撈取時丟出Column contains NULL data，但用EF寫入又無問題
?
- Answer:問題出在class前Attr
```
[Required]
```
