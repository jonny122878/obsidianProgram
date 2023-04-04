# 引入副程式
ex:NuGet、using.....
- NET Core安裝套件預設路徑:C:\Program Files (x86)\dotnet
- .NET Framwork為類別庫是由ADO.NET、WinForm...組成
- C:\Program Files (x86)\Microsoft SDKs\NuGetPackages
- 在專案裝NuGet:C:\Users\bayon\.nuget\packages\ajaxcontroltoolkit\15.1.2
- [.NET Framework支援OS](https://blog.darkthread.net/blog/net472-and-win10-version/)
- [.NET相容性](https://blog.darkthread.net/blog/netfx-eos-list/)

# 解決問題情境步驟
## 專案替換
名稱替換
- 外部資料夾
- 內部資料夾
- sln
- csproj
- csproj.user
- sln編輯
## WinForm編譯exe
- App.config
- csproj
  - 應用程式
    - 組件名稱
    - 起始物件
  - 貞錯
    - 命令引數
外部提煉到config或命令引數

# 指令樣式
ex:function、object....
## 分類
### 特性ex:CRUD
# limit
- 安裝NuGet套件無法安狀?
  - 要注意專案本身框架版本
- ASP.NET 找不到路徑 bin\roslyn\csc.exe?	
  - 開新專案再重建後複製csc.exe過去
- 為何.NET6沒有基本C#語法，ex:namespace、using.....
  - 用Top-level-statements 
ex:臨界值
- 未載入System.Web.pdb
- 原因為Debug到被封裝起來dll,需在偵錯設定打開Just My Code只Debug我自身程式碼,否則就是要設定NuGet或Microsoft其程式碼所在路徑




