# 目錄
- [情境範例](#情境範例)
- [指令](#指令)
  - [通用指令](##通用指令) 
  - [OS處理指令](##OS處理指令) 

  - [檔案讀寫指令](##檔案讀寫指令) 
  - [網路相關指令](##網路相關指令) 
- [limit](#limit)
  - [limit通用指令](##limit通用指令) 
  - [limitOS處理指令](##limitOS處理指令) 
  - [limit檔案處理指令](##limit檔案處理指令) 
  - [limit檔案讀寫指令](##limit檔案讀寫指令) 
  - [limit網路相關指令](##limit網路相關指令) 

# 情境範例
- [網路磁碟創建](######disk_ex)
- [檔案備份](######backup_file_ex)
- [讀取txt做判別](######read_txt_ex)
- [backup DB](######backup_db_ex)
- [解壓縮檔案](######prase_zip_ex)
- [ftp下載檔案](######ftp_download_ex)
- [7zip解壓縮](https://hooo.medium.com/%E5%B7%A5%E4%BD%9C%E7%AD%86%E8%A8%98-%E9%80%8F%E9%81%8E7zip%E6%8C%87%E4%BB%A4%E5%B0%8D%E6%AA%94%E6%A1%88%E9%80%B2%E8%A1%8C%E5%A3%93%E7%B8%AE%E8%88%87%E8%A7%A3%E5%A3%93%E7%B8%AE-861da198932)
# 指令
## [通用指令](#目錄)
- 新
- 刪
- 修
- 查
  - date
  - time
  - computername
  - username
  - query /?
  - cd (可得到目前bat當下路徑)
  - CMDCMDLINE  (執行這個檔案的原執行程式，一般是CMD.exe)
  - RANDOM  (0到32767之間的亂數)
- 移
  - cd/d**path** (排程不能空白要填/d)
  
----
## [OS處理指令](#目錄)
- 新
  - start */max /min* **exe** "**file**" (若不填預設原本呈現視窗)
  - powershell "Compress-Archive -Path **to zip folder** *-update* -DestinationPath **zip**" (update已存在是否覆寫壓縮檔)
- 刪
  - C:\WINDOWS\system32\shutdown.exe -s -t 0 (close computer)
  - C:\WINDOWS\system32\shutdown.exe -f -r (restart computer)
  - taskkill /im **exe** /f (close exe)
- 修

- 查
  - tasklist (return PIDs)
- 移
----
## [檔案處理指令](#目錄)
- 新
  - touch **file**
  - md **directory** *dirctory2* *dirctory3* (only directory)
- 刪
  - del
  - del *.txt
  - del **dirctory** /S /Q (整個資料夾內含檔案刪,不詢問)
  - rd **directory**
- 修
  - ren **source** **dest** (放在迴圈內注意路徑所在位置)
- 查
  

----
## [檔案讀寫指令](#目錄)
- 新
  - sqlcmd -s **server** -u **user** -p **pwd** -i **SQLScript** -o **txt or csv**
  - sqlcmd -s **server** -u **user** -p **pwd** -q **SQL**
  - sqlcmd -s **server\instance** -q **"SQL"**
  - dir > **file** (create file if it not exist,override file if it exist)
  - dir >> **file** (create file if it not exist,append file if it exist)
- 刪
    
- 修
- 查
- 移
----
## [網路相關指令](#目錄)
- 新
  - net use **disk** **path** **pwd** /user:**username** /persistent:no
- 刪
  - net use **disk** /delete
- 修
- 查
  - netstat -a -n -o
- 移
---

# limit
## [limit通用指令](#目錄)
- 新
  - time (若早上做時段擷取會少了一個數字，ex:08 => 8) 
- 刪
- 修
- 查
  
- 移




## 名稱記憶


###### [backup_db_ex](#目錄)
- RESTORE_FOLDER要還原資料庫bak位置
```
@echo off
REM 用來產生Log的格式 可以是yyyyMMdd HHmmss if need HHmmss
for /f %%i in ('formatdate.exe yyyyMMdd') do (set logtime=%%i)
set RESTORE_FOLDER=D:\DB

set RESTORE_SERVER=10.40.100.61
set RESTORE_USER=sa
set RESTORE_PASSWORD=

REM Kill the proc for restore success
sqlcmd -S%RESTORE_SERVER% -U%RESTORE_USER% -P%RESTORE_PASSWORD% -Q "exec master..spj_KillSPID 'dbName'"

sqlcmd -S%RESTORE_SERVER% -U%RESTORE_USER% -P%RESTORE_PASSWORD% -Q "RESTORE DATABASE %1 FROM DISK = '%RESTORE_FOLDER%\dbName.bak' WITH REPLACE" -o%1.restore.%logtime%.log

```

###### [disk_ex](#目錄)
- 刪除後新增
```
net use Y: /delete
net use Y: \\10.40.100.60\n00r1 password  /user:oscadmin /persistent:no
```

###### [backup_file_ex](#目錄)
- 目前系統時間函數
- 切換所在路徑
- 指令選定並定義limit
- 指令組合變數或迴圈
```
set dayName=%date:~0,4%%date:~5,2%%date:~8,2%
set timeName=%time:~0,2%%time:~3,2%%time:~6,2%
if %timeName:~0,1% EQU " " set timeName=%timeName:~1%
cd/dD:\jonny\testBat\backup
md %dayName%_%timeName%
move "D:\jonny\testBat\input\test1.txt" "D:\jonny\testBat\backup\%dayName%_%timeName%\test1.txt"
::集合指令式
move "D:\jonny\testBat\input\*.txt" "D:\jonny\testBat\backup\%dayName%_%timeName%\"
::迴圈語法式
for /f %%i in ('dir /b *.txt') do (
move D:\jonny\testBat\input\%%i D:\jonny\testBat\backup\%%i
)
::
```

###### [read_txt_ex](#目錄)
txt sample:
```
已將資料庫內容變更為 'OSC_REPORT'。
          
----------
20220530  

(1 rows affected)
```
ex:單位為行讀取判別(因內容有空白因此加入分隔符)
```
cd/dD:\jonny\testBat\IsTranDate
set IsTranDate=Y
for /f "delims= " %%i in (IsTranDate.txt) do (
if %%i EQU 20220531 set IsTranDate=N
)

```




###### [prase_zip_ex](#目錄)
- 7z壓縮
- winrar
```
for /d %%X in (*) do "c:\Program Files\7-Zip\7zG.exe" a -mx "%%X.zip" "%%X\*"

cd \tools\winrar
winrar.exe x "d:\TEJ\%filename1%" "d:\TEJ\%My_DATE1%\" -u
::解壓縮 u參數表示"若檔案已存在直接覆蓋"
```


###### [ftp_download_ex](#目錄)
```
@Echo off

    echo wscript.echo dateadd("d",-1,date) >%tmp%\tmp.vbs
    for /f "tokens=1,2,3 delims=/- " %%i in ('cscript /nologo %tmp%\tmp.vbs') do set y=%%i
    for /f "tokens=1,2,3 delims=/- " %%i in ('cscript /nologo %tmp%\tmp.vbs') do set m=%%j
    for /f "tokens=1,2,3 delims=/- " %%i in ('cscript /nologo %tmp%\tmp.vbs') do set d=%%k
    if %m% LSS 10 set m=0%m%
    if %d% LSS 10 set d=0%d%

set T_day=WRTWSE%y%%m%%d%.txt
set O_day=WROTC%y%%m%%d%.txt

echo open fancy.sfi.org.tw > d:\WRTWSE\getfile_New.txt
echo user warrantwin justwin  >> d:\WRTWSE\getfile_New.txt
echo cd warrants >> d:\WRTWSE\getfile_New.txt
echo prompt off >> d:\WRTWSE\getfile_New.txt
echo lcd d:\WRTWSE >> d:\WRTWSE\getfile_New.txt
echo prompt off >> d:\WRTWSE\getfile_New.txt
echo mget %T_day% >> d:\WRTWSE\getfile_New.txt
echo mget %O_day% >> d:\WRTWSE\getfile_New.txt
echo quit >> d:\WRTWSE\getfile_New.txt
ftp -ins:d:\WRTWSE\getfile_New.txt
::判斷檔案ZIP是否存在
@echo on
::@echo off



```

[bat命令](https://iter01.com/623328.html)


IF EXIST filename.txt (
    del filename.txt
) ELSE (
    echo filename.txt missing.
)