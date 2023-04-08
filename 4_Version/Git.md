


## commit碰到情況
### 拉新需求
  - git flow feature start feature_branch (on develop branch)


# 解決問題情境步驟
## 初始化、拉新需求
  - [Git初次使用要設定](######install_git_setting)


## 多人協作遠端衝突
  - [開發完成推送遠端推不上去](######push_error_ex)
## commit碰到情況


  - [commit要存檔](######commit_example)
  - [暫存區和commit為不同區塊，分支切換暫存區檔案不會變](######temp_ex)
  - [開發到一半要去做別的事](https://gitbook.tw/chapters/faq/stash)
  - [退版](######reset_tag)
## 合併分支情境
  - [1個commit 2個檔案但再merge時只要1個檔案](######reset_ex)
  - [merge所在branch](######merge_example)
  - [feature需求合併](######merge_feature_ex)
  - pull下來新的commit點
    - pull會先到local origin branch瀏覽
    - 無問題checkout到local branch
    - merge origin branch 

# 指令樣式
ex:function、object....
## Git指令顆粒度概念
- directory
- repository
- branch
- commit
## 指令本地
### 查詢
  - git log 
  - git config -l
  - git branch (all local branch)
  - git branch -r (all web branch)
  - git branch -a (all branch)
  - git status (on branch)
  - git diff (on branch)
  - git reflog
### 新增
  - git config --local user.name **新增此專案使用者名字**
  - git config --local user.email **新增此專案使用者的電子郵件**
  - git config --global user.name **新增Git使用者名字**
  - git config --global user.email **新增Git使用者的電子郵件**
  - git add -A(on branch 用在第一次加入file都沒被追蹤,資料夾要先追蹤不然每次都跑新檔案)

  - git commit -a 'msg'(on branch 已追蹤又刪除才能用)
  - git tag -a (on 要貼tag branch，適合標注版號，方便退版)
  - git branch (on repository，不常用因有導入gitflow)
  - git stash (加入temp)
### 修改
  - git merge **branch** *--no-ff* (此參數常用會長出分支，on merge branch)   
  - git restore **file** (on commit)  
  - git branch -D **branch** (參數有分大小寫,並且delete當前位在branch無法刪)
  - git reset **branch**^ (往前一次)
  - git reset **branch**~5 (數字表示次數)
    - default 參數 --mixed(會將拆除檔案丟到暫存區)
    - --hard直接捨棄
  - :wq
  - git merge **branch**(on branch 當下branch是要被merge進來，因不會呈現分支不常用)
  - commit index **選a** (y n q a d e)(不建議使用，建議退掉commit點只取要檔案)
  - git checkout **branch** --patch **file**(file要注意是否子資料夾，不建議使用，建議退掉commit點只取要檔案)  
### 移
  - git checkout 
## 指令遠程
### 查 
  - git remote -v
### 修
  -  git remote set-url origin **web url**  
### 新
  - git clone(on directory) p1
  - git push origin **branch** (branch名稱要對應）
  - git push origin **branch** -f (強制將遠端清除並push)
  - git push --all origin
  - git push --mirror **url** (其它遠程儲存庫)
  - git push -f origin **branch**
### 刪


# limit
ex:臨界值
## 為何branch分岔路產生情況?
- 最開始時二個branch起點為同個init commit
  - 因此除非起點那個commit同時拉出了**2條以上**新的branch畫面為了區分會長耳
  - 當二個branch各自commit一次後，雖然起點同一個，但各自commit並無**先後順序**關聯，因此開岔了
  - 結論:會有分岔情況就是有新的commit，或是為了**視覺上區別**呈現
## 為何merge有時會有長耳有時不會?
- 長耳機制在於產生commit情況，因此會發生在merge衝突上
- merge衝突:
  - merge時有衝突時無法合併的此時git會將衝突檔案呈現再檔案上
  - 這時你必須決定此次**最後衝突結果**
  - 修改完後就會commit記錄決定結果並順便將其merge
- 無merge衝突情況:
  - branchs中header所指向同個commit
  - 若merge要長耳需要設定**非快轉模式**，多加1個commit

## 刪除.git資料夾後結果?
delete .git是所有都delete回歸到最開始git init那時檔案狀態

## 將檔案copy到控管資料夾外結果?
以目前所在分支檔案狀態為主

## https和ssh差異?
- [https和ssh差異](https://www.casper.tw/git/2018/02/12/github-ssh-https/)
- [ssh是甚麼](https://codecharms.me/posts/security-ssh)

## reset、rebase、revert退回指令差異?
- [reset、rebase、revert](https://gitbook.tw/chapters/rewrite-history/reset-revert-and-rebase)
簡而言之可先大方向區分成有無將分支push出去

## git clone是否會產生資料夾?
會自己幫你產生資料夾，~~需再建立對應子資料夾~~

## git無法拉feature?
- [git無法拉feature](https://stackoverflow.com/questions/36843062/fatal-not-a-gitflow-enabled-repo-yet-please-run-git-flow-init-first)

## git pull不存在的branch後無法在本地端建立branch直接從pull branch開 new branch
- checkout pull **branch**
- checkoub -b **feture/branch**






###### [reset_tag](##commit碰到情況)
- git tag (查詢目前所有tag)
- git show tag name (找出tag hashcode)
- git reset hashcode (退到問題版本之前)
- git checkout -b hotfix/ (將此有問題的版本拉出一個上版問題分支進行修正) 
- git merge (修正測試後merge master and develop)

###### [install_git_setting](##commit碰到情況)
- 再調用時，將其Git想成exe，設定使用者帳號一樣，設定使用者名稱和信箱
- 其有全區域概念，若想讓**不同專案設定不同使用者**是可以的，預設是讀**全域**設定

###### [commit_example](##commit碰到情況)
```
Git Extensions選擇要修改操作的分支
file save之後才會有commit跑出來
```
###### [temp_ex](##commit碰到情況)
```
暫存區:test1.txt on develop
git checkout master
```

###### [push_error_ex](##多人協作遠端衝突)
原因:表示commit之前歷程不一致
- fetch後可從樹狀結構瀏覽遠端和本地差異 
- reset push branch到差異前的版本
- stash 暫存擋 or checkout -b 新的分支(如有新增untracked file只能用此方法)
- pull local
- reslove conflict，stash拉出來處理或是merge
- 重新push上去
另種暴力解法直接 git push -f  override衝突點







###### [reset_ex](##合併分支情境)
- reset develop讓commit點檔案退到暫存區
- 重新將要上版的檔案commit
- commit後接續merge流程
```
git reset develop^
git add 'commit file'
git commit -m 'msg'
```

###### [merge_example](##合併分支情境)
```
所在位置為無merge要上版branch
Commands Merge Branch 選擇開發驗證完成要上版的分支
看到二個分支在同個位置即為合併完成
```





