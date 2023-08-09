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
#資訊 
# Unify




1. #flashcards 
- Highlight:原本此資料夾都無受到版控情況下,如何將其版控並推送雲端
- Question:
?
- Answer:
- .gitignore (要加入對應語言過濾檔)
- git init 後要先git add -A後再進行,避免git flow**每個branch**都要init
- git flow init
- 創建雲端:
```
create empty repo in GitHub
git remote add origin <Link to GitHub Repo> //maps the remote repo link to local git repo
git remote -v //this is to verify the link to the remote repo 
git push -u origin master  // pushes the commit-ed changes into 
```

2. #flashcards 
- Highlight:雲端已經有git版本庫,該如何拉下來
- Question:
?
- Answer:
```
git clone <Link to GitHub Repo>
// 要更換推送遠端
git remote set-url origin **web url**
```

3. #flashcards 
- Highlight:
- Question:
?
- Answer:

