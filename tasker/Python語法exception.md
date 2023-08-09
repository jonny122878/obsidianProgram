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
#資訊 #py 
# Unify




1. #flashcards 
- Highlight:要將陣列給塞入字典元素
```
arrBingo.insert({term:key,balls:value})
```
- Question:name 'term' is not defined
?
- Answer:和JSON直覺稍有不同，key要加引號

2. #flashcards 
- Highlight:
- Question:為何import後還是會exception
```
import db
dbContext = MongoDbContext( "localhost", "test_db") //error
```
?
- Answer:前面要再加import修飾子
```
dbContext = db.MongoDbContext( "localhost", "test_db")
```

3. #flashcards 
- Highlight:
- Question:
?
- Answer: