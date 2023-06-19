# IDE構造:
## 編輯區塊
## 檔案列表
## 結果呈現
## 上方工具列
# 共用情境:
## 樣版搬移
## 跳躍
- win+r+recent快速將昨日開啟項目給開啟
- win+x (OS相關設定ex:電腦管理、資安相關截圖防毒軟體、windows update)
## 編輯



## Desktop
- ctrl+win+d
- ctrl+win+f4
- win+arrow


# Fast Key
## 新
- ctrl+shift+n (create directory)
- win+r+notepad (create txt)
- control,再搜尋框打系統即可看到環境變數 (設定環境變數)
- alt+h+pi 丁選
## 刪
- alt+f4 (close window)
## 修
- f2 (rename file)
- ctrl+l(edit path)
- win+u+a(進入設定) 
## 查
- win+alt+d = calendar
- alt+v+o+item = filter
- shift+f10(on directory)(右鍵瀏覽)
- alt+enter (查看檔案屬性)

- win+r
  - recent
  - gpedit.msc 本機群組
  - regdit
  - eventvwr (事件檢視)
- win+v (查看剪貼簿)
- 開啟舊檔 tab order
  - 檔案列表
  - 檔案列表名稱欄(last)
  - 檔案名稱 (default)
- 檔案總管路徑為空
- 檔案總管路徑有值 
## 移
- f6(移動到資料夾各區塊) 
- win+home
   - ex:[將目前window做編輯](######將目前window做編輯)
- ctrl+alt+tab
   - ex:[資料夾間搬移檔案](######資料夾間搬移檔案)
- win+num
  - ex:[使用中呼叫其他資源](######將目前window做編輯)
- win+direction


# 解決問題情境
## 改密碼
- [ ] 控制台\所有控制台項目\使用者帳戶\管理帳戶\變更帳戶\
- [ ] 密碼改完之後要再每個排程再按確認
## 環境變數
- win+r control
- 輸入環境變數到搜尋框上
## 預設安裝程式位置
- C:\Program Files (此處為x64套件路徑)
- C:\Program Files (x86) (此處為x86套件路徑)
# 重灌流程
- 先去微軟官網載入來源並將其弄入**外部**裝置(USB、DVD)
- 在本機BIOS設定(和外部裝置IO串接) 
# VM
- 預設路徑為C:\Program Files (x86)\VM ware
- licesne expired 不是權限問題是到期
[download](https://www.vmware.com/tw/products/workstation-player/workstation-player-evaluation.html)

# Docker
解決問題：讓程式和其相依套件打包成一起
VM和Docker差異：有OS和無OS

查看.net framework
https://docs.microsoft.com/zh-tw/dotnet/framework/migration-guide/how-to-determine-which-versions-are-installed

# limit
- exe不可預期關閉?
  - 檢查是否OS有相容
- 程式連線資料庫發現TLS、SSL之類協定無法連線?
  - 要確認資料庫主機regedit相關設定
  - [TCP_IP無啟用](https://ithelp.ithome.com.tw/questions/10189608)
- .msi安裝檔無dll?
  - 確認重建專案模式是否有包含dll
