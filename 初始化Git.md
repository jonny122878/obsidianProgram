---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:亞證
Author:
Note Type:
Topics:


# Highlight:
- 原本此資料夾都無受到版控情況下,如何將其版控並推送雲端
- 雲端已經有git版本庫,該如何拉下來
# Question:
此二者步驟是否相同?
# Answer:
#### 本機git初始化步驟
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
#### 雲端git初始化步驟
```
git clone <Link to GitHub Repo>
// 要更換推送遠端
git remote set-url origin **web url**
```



