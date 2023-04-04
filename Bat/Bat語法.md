# 特性
- 做任何指令時都有位置概念
- ex:ren指令參數前就不要加路徑
- 空白是有含義的,因此在備註、條件、迴圈、路徑要特別小心
# 分隔符
-無符號做分隔(;、,)，用空白為單位

# 型別

# 結構變數
- 類似**Razor**用%%去包覆
- 宣告時**無型別概念**都用SET
- 宣告無全區域概念，像是迴圈內變數
- 同樣變數名重複指定也要SET
- 再做變數指定時不需用%%修飾符,其修飾是用來組字串
- 字串截斷是要將整個目標字串用%%包覆
- ex:SET day=%date:0~4%%date~5,2%
- 再做右側指定時字串不需要加修飾符
- 類似若弱型別因此要用set /a 關鍵字 variant += 1

# 結構集合

# 迴圈
  - 語法規範
    - 開頭必加/f
    - 計數變數用%%i去修飾等同%%變數修飾
    - 並且特別注意do( 不能換行
    - ex:[資料夾內檔案迴圈展開](######loop_compare_bat_ex)
  - 迴圈展開txt
    - "delims="分割單位為行數
    - "delims= "分割單位行數但後面有分隔符號，
    - for /f "delims= " %%i in (IsTranDate.txt)
    - 注意keyword順序
    - 展開txt不需要要加入引號修飾(避免OS將txt開啟)
    
# 條件
- 相等符號是和c#同樣
- EQU、LSS...比較符
- if not defined 

# 函式：調用參數用/符號修飾
- 內部函式語法規範
    - 類似goto原理用:做修飾子
    - 變數並無區分回傳和輸入(等於變數作用域會代到外面)
    - [讀取txt內容到變數做變化](######function_inner_bat_ex)
- 外部函式語法規範
    - 要被呼叫的bat副檔名改成cmd
    - cmd調用bat參數，按照順序從%1開始
    - [backup db](######function_outer_bat_ex)





###### loop_compare_bat_ex
ex:原始迴圈
```
for /f %%i in ('dir /b *.txt') do (
move D:\jonny\testBat\input\%%i D:\jonny\testBat\backup\%%i
)
```
~~ex:迴圈變數替換~~
```
for /f %%i in ('dir /b *.txt') do (
move D:\jonny\testBat\input\%%i% D:\jonny\testBat\backup\%%i%
)
```
~~ex:迴圈換行~~
```
for /f %%i in ('dir /b *.txt') do 
(
move D:\jonny\testBat\input\%%i D:\jonny\testBat\backup\%%i
)
```


###### [function_inner_bat_ex](##bat)
```set server=10.40.100.60
set user=ddmc
set pwd=23618600
set IsTranDate=Y

call :TranDate IsTranDate
if %IsTranDate% EQU N goto NotExcute
:NotExcute
cd/dD:\JRisk\Excute_SQLScript\IsTranDate\log\
set nowDate=%date:~0,4%%date:~5,2%%date:~8,2%
echo "今日非交易日" >> MOVE_NAV%nowDate%.log
exit /b 0


:TranDate
cd/dD:\JRisk\Excute_SQLScript\IsTranDate\
sqlcmd -S%server% -U%user% -P%pwd% -i IsTranDate.sql -o IsTranDate.txt
for /f "delims= " %%i in (IsTranDate.txt) do (
if %%i EQU NULL set IsTranDate=N
)
```

###### [function_outer_bat_ex](##bat)
main.bat
```
d:
cd 
call BackupDB.cmd RMX_OSC
```

BackupDB.cmd
```
@echo off
REM 用來產生Log的格式 可以是yyyyMMdd HHmmss if need HHmmss
for /f %%i in ('formatdate.exe yyyyMMdd') do (set logtime=%%i)
set RESTORE_FOLDER=D:\DB

set RESTORE_SERVER=10.40.100.61
set RESTORE_USER=sa
set RESTORE_PASSWORD=u832j/ijdbndle

REM Kill the proc for restore success
sqlcmd -S%RESTORE_SERVER% -U%RESTORE_USER% -P%RESTORE_PASSWORD% -Q "exec master..spj_KillSPID '%1'"

sqlcmd -S%RESTORE_SERVER% -U%RESTORE_USER% -P%RESTORE_PASSWORD% -Q "RESTORE DATABASE %1 FROM DISK = '%RESTORE_FOLDER%\%1.bak' WITH REPLACE" -o%1.restore.%logtime%.log

```
