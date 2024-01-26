# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::5
Review::true

#dart #資料 
# Unify




1. #flashcards 
- Highlight:
- Question:C#開發dll為何flutter無法用第三方函式庫調用?
?
- Answer:dll本身是有調用約定，並且C#約定stdcall不能修改，dart和C++約定都為cdecl，目前已知只有C++能修改dll調用約定

2. #flashcards 
- Highlight:C#
- Question:MAUI為何專案無法建置過
?
- Answer:OS開發人員
![[Pasted image 20230830182148.png]]
3. #flashcards 
- Highlight:
- Question:未載入System.Web.pdb
?
- Answer:為Debug到被封裝起來dll,需在偵錯設定打開Just My Code只Debug我自身程式碼,否則就是要設定NuGet或Microsoft其程式碼所在路徑


4. #flashcards 
- Highlight:
- Question:安裝NuGet套件無法安裝?
?
- Answer:要注意專案本身框架版本，目前分為如下
- NET Core安裝套件預設路徑:C:\Program Files (x86)\dotnet
- .NET Framwork為類別庫是由ADO.NET、WinForm...組成
- C:\Program Files (x86)\Microsoft SDKs\NuGetPackages
- 在專案裝NuGet:C:\Users\bayon\.nuget\packages\ajaxcontroltoolkit\15.1.2
- [.NET Framework支援OS](https://blog.darkthread.net/blog/net472-and-win10-version/)
- [.NET相容性](https://blog.darkthread.net/blog/netfx-eos-list/)

5. #flashcards 
- Highlight:
- Question:專案名稱替換
?
- Answer:
	- 外部資料夾
	- 內部資料夾
	- sln
	- csproj
	- csproj.user
	- sln編輯


6. #flashcards 
- Highlight:
- Question:
?
- Answer:

7. #flashcards 
- Highlight:
- Question:
?
- Answer:




## WinForm編譯exe
- App.config
- csproj
  - 應用程式
    - 組件名稱
    - 起始物件
  - 貞錯
    - 命令引數
外部提煉到config或命令引數


- ASP.NET 找不到路徑 bin\roslyn\csc.exe?	
  - 開新專案再重建後複製csc.exe過去
- 為何.NET6沒有基本C#語法，ex:namespace、using.....
  - 用Top-level-statements 

- 



