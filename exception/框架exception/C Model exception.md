# Metadata
Qty::2
Review::
Restructure::relation

### Think




# Exception


1. #flashcards 
- Highlight:DbSet理解錯誤造成LINQ無法操作
- Question:具有陳述式主體Lambda運算式，不可轉換成運算式樹狀結構 IQueryable
?
- Answer:DbSet inherit IQueryable 延遲查詢調用，因此若要用LINQ要先AsEnumerable，而不是透過用本來資料表去弄


2. #flashcards 
- Highlight:NET6
- Question:Code First如何產生SQL指令寫到log
?
- Answer:
```
    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        Console.WriteLine(modelBuilder.Model.ToDebugString());
    }
```

3. #flashcards 
- Highlight:
- Question:
?
- Answer:

4. #flashcards 
- Highlight:
- Question:
?
- Answer:

5. #flashcards 
- Highlight:
- Question:
?
- Answer:

