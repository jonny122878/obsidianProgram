# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::2
Review::
#work #知識 
# Unify
- 大量為主題
- 刪除大量branch
- 退掉大量commit點




1. #flashcards 
- Highlight:
- Question:已經commit之後，該如何退掉commit
?
- Answer:
  - git reset **branch**^ (往前一次)
  - git reset **branch**~5 (數字表示次數)
    - default 參數 --mixed(會將拆除檔案丟到暫存區)
    - --hard直接捨棄(不建議)

2. #flashcards 
- Highlight:
- Question:merge一段時間後本地有大量舊有feature分支，是否有類似模糊搜尋將此批量分支刪除
?
- Answer:
```
git branch | grep 'feature/' | xargs git branch -d
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