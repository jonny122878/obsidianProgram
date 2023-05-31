# IDE構造:
## 編輯區塊
## 檔案列表
## 結果呈現
## 上方工具列

# 共用情境:
## 樣版搬移
## 跳躍
## 編輯


## Debug
- 先清除舊有殘留斷點 
    - ctrl+shift+f9 (clear all break)
- 開始下break
     - F9 (set break)
- debug之前重建
     - ctrl+shift+b(build project) 
- debug各種顆粒度切換
     - ctrl+f5(test not break)
	  - f5 (run)
	  - f11 (run step)
	  - f10 (not run function)
	  - shift+f11(jump function)
	  - shift+f5 (jump run)
- 按照上次觀測結果
  - ctrl+\,e
  - ctrl+alt+b
  - 迴圈式進行條件break
    - 
  - 此次觀測用不到停用
    - ctrl+f9
  - 完全用不到刪除
    - f9

 


  
  
## tag
  - ctrl+b+t (set tag)
  - ctrl+k+k (set tag 2012)
  - ctrl+b+c (clear all tag)
  - ctrl+k+l (clear all tag 2012)
  - ctrl+b+p (previous point tag)
  - ctrl+b+n (next point tag)
## search
- select value+ctrl+f3 (搜尋目前文件,少打關鍵字直接代入) 
- ctrl+shift+f3 (all seracrh 事前先將搜尋顆粒度調整好)
- F12 (declare)
- ctrl + - (retrun call declare)
- ctrl+shift+ - (return declare)
## observer

## file 

## restructure
  - prop+tab (create property)
  - ctor+tab (create class new)
  - ctrl+shift+a (create file)
  - shift+alt+a (edit add new file)
  - shift+f10+o+r

## veiw
- ctrl+m,o(hidden area)
- c
- 
- trl+m+p(cancel hidden)
- enter(方案總管內會將資料夾收起)
- ctrl+m,m (region給隱藏)
- enter (在工具列中資料夾展開和隱藏)
- ctrl+g (move point line)
- ctrl+tab (previous next cs) 
- ctrl+w ctrl+x(tool box)
- ctrl+w ctrl+s(方案總管)
- ctrl+w,l (伺服總管)
- alt+t+n+o (套件管理主控台)
- alt+t+n+n (NuGet) 






 

# 問題情境
- 建立新專案是否需要在此路徑下再開資料夾?
  - 編譯器會自動建立對應資料夾，名稱用專案命名
  - ![project建立對應資料夾](https://i.imgur.com/RezAS8T.png)
- Web與API做前後分離如何測試?
  - 嘗試用2個sln分離
- NET6無法使用using intelligense字體反白?
  - 應和NET6無關，IDE重啟即可 
- Just My Code?
  - 不啟動則會連原生.NET碼也會進入 
- 如何計算程式碼度量?
  - [度量](https://ithelp.ithome.com.tw/articles/10078641)

copy不同的sln可以有紀錄break與tag功能
