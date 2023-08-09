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
Topics::Tools、ShortKey、review

# Unify


#資訊 #work 


## 樣版搬移
### 搬移樣版後文字上落差
- ctrl+l copy整個類別翻過來**多餘屬性**，直接刪除整列

### 函數名稱和函數簽名要抽換
- ctrl+shift+f 用來驗證替換點數量是否正確，調用時先將**顆粒度**調好
- ctrl+shift+h 實際進行替換
- 函數名稱替換一次(讓調用點和其一致)
- 調整**顆粒度目前文件**將函數簽名再次替換
- 後續用ctrl+w+e 快速解決error問題


## 跳躍
### 移動順序為單位
- ctrl + - 
- ctrl+shift+ - 
### 結構單位
- alt+F12 事前先瀏覽確認要編輯在跳躍
- F12 (declare)
- alt+\ 方法成員
### 模塊為單位
- ctrl+1+ctrl+r 先前開過檔案
- ctrl+shift+t 檔案
- ctrl+alt+l 所有專案結構瀏覽
- enter(方案總管內會將資料夾收起)
### 修改模塊為單位
- ctrl+k+k (set tag 2012、2022) **修改**module用**tag為單位**，ex:Service、Controller
- ctrl+b+t (set tag 2019)
- ctrl+w+b ，瀏覽目前所有模塊
- ctrl+k+f ，將單元測試workflow串成資料夾
- ctrl+b+p ，情境通常為樣本跟修改點(省去跳到**總覽模塊**)，環境先用總覽模塊搬到相同順序
- ctrl+b+n ，情境通常為樣本跟修改點(省去跳到**總覽模塊**)，環境先用總覽模塊搬到相同順序
- ctrl+b+c (clear all tag)
- ctrl+k+l (clear all tag 2012)
- ctrl+g (move point line)
### 功能為單位
- ctrl+\,e 2019
- ctrl+w+e錯誤區塊
- shift+esc將當前區塊關閉
- ctrl+alt+b，break點
- alt+g+c，Git變更
### break為單位
- f5 (run)
- f11 (run step)
- f10 (not run function)
- shift+f11(jump function)
- shift+f5 (jump run)
### Git branch為單位
- ctrl+alt+f3 

## 編輯
### Debug
- ctrl+shift+f9 (clear all break)
- F9 (set break)
- ctrl+shift+b(build project) 
- ctrl+u,ctrl+shift+u 大小寫切換
### 目前文件調用點確認
- select value+ctrl+f3 (搜尋目前文件,少打關鍵字直接代入) 
- ctrl+m,m (region給隱藏)

### 快速導出樣版
  - prop+tab (create property)
  - ctor+tab (create class new)
  - ctrl+shift+a (create file)
  - shift+alt+a (edit add new file)
  - shift+f10+o+r

## 視野
- ctrl+k,d 排版