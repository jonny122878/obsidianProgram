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
Topics::true
Qty::4
#dart #資料 
# Unify


1. #flashcards 
- Highlight:Windows
- Question:安裝程式語言步驟
?
- Answer:
  - 先去官網找其對應PlatForm SDK
  - 在設定環境變數讓PlatForm能識別
  - 搭配對應IDE並且識別SDK位置


2. #flashcards 
- Highlight:
- Question:重灌流程
?
- Answer:
 - 先去微軟官網載入來源並將其弄入**外部**裝置(USB、DVD)
 - 在本機BIOS設定(和外部裝置IO串接) 


3. #flashcards 
- Highlight:Windows
- Question:改密碼
?
- Answer:
- [ ] 控制台\所有控制台項目\使用者帳戶\管理帳戶\變更帳戶\
- [ ] 密碼改完之後要再每個排程再按確認


4. #flashcards 
- Highlight:
- Question:node.js、npm、nvm、Angular、typescript如何將環境配置
?
- Answer:
- node.js為其SDK
- nvm調整其版本工具
- npm類似NuGet裝套件使用
- typescript、Anuglar都算是套件

5. #flashcards 
- Highlight:
- Question:
?
- Answer:






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
