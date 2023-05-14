---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:練習
Author:
Note Type:
Topics:


# Highlight:
1,2.Angular cli做基架Load新專案
# Question:
1.Please update your Node.js version or visit https://nodejs.org/ for additional instructions.
2.檔案 C:\Users\bayon\AppData\Roaming\npm\ng.ps1 未經數位簽署。
# Answer:
1.node -v Angular cli version 不符，node、npm、Angular cli**各自有版本**
2.這個錯誤訊息是由於您的系統安全設定阻止了執行未經數位簽署的 PowerShell 腳本所導致的。在這種情況下，這是由 Angular CLI 創建的 PowerShell 腳本。
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
```


