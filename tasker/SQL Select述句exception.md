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
Qty::2



#資料 #py
# Unify
- 集合本身都有類似集合體，跟實際轉成集合的資料結構，差別在於弱型別用符號表示


1. #flashcards 
- Highlight:javascript
- Question:如何將IEnumerable轉成array
?
- Answer:ToArray: Array.prototype.slice.call(**IEnumerable**) 

2. #flashcards 
- Highlight:javascript
- Question:直覺用Select(r => r.Value)取不到整個集合?
```
IEnumerable<KeyValuePair<int, List<BookLendRecord>>>
        let records = lendLists.filter(object => {
            return object.Key == new Number(id);
        }).map(r => r.Value)[0];
```
?
- Answer:直覺錯誤map預設回傳**集合**，所以是包在集合中元素內

3. #flashcards 
- Highlight:
- Question:
?
- Answer:
