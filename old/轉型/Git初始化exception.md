# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::3
Review::

#work #知識 
# Unify
- 雙向溝通區分為本地沒有或遠端沒有，衍生遠端別人先push branch

1. #flashcards 
- Highlight:
- Question:
?
- Answer:

2. #flashcards 
- Highlight:
- Question:
?
- Answer:

# Exception

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
- Question:origin已經有新建feature branch，但本地沒有該如何拉取
?
- Answer:提取下來會將本地origin給刷新，再透過簽出即可到origin

4. #flashcards 
- Highlight:
- Question:
?
- Answer:

