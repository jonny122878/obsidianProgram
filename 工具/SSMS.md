 ctrl+u 切換資料表


## 新
- ctrl+k,x (fast crate table,storeduce)
## 刪
## 修
## 查
- f4 (物件總管)
- f8 (物件屬性)
- ctrl+w+l (伺服器總管)
- 檢視 => 其他視窗 => 套件管理主控台(PowerShell)
- ctrl+m (可瀏覽執行計劃)
## 移
- ctrl+tab (previous next sql) 
- f6 (移動各區塊)
## 顯示
- alt+arrow (hidden)


# 資源
- [sql server download](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
- download a free specialized edition選Developer
- [ssms download](https://docs.microsoft.com/zh-tw/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)

# 問題情境
## 清除ldf
- [ ] SQL Server Agent => BackupDatabase排程
- [ ] 資料庫 => 屬性 => 選項 => 復原模式 => 完整 => 簡單
- [ ] 資料庫 => 屬性 => 檔案 => 紀錄檔
- [ ] 資料庫 => 屬性 => 選項 => 復原模式 => 簡單 => 完整
- [ ] click右鍵彈出選單=> 工作 => 壓縮 => 檔案 => combobox 記錄檔,checkbox 20

# limit
- sqlcmd找不到指令?
  - 確認SQL PowerShell有無安裝，環境變數有無設定 
- 開啟SSMS發現伺服器名稱無自動帶入，並且無法用.連線
  - SQLEXPRESS重新啟動
  - SQL Server服務重啟
- 為何下載會區分執行個體和SSMS?
  - 執行個體和SSMS是二個不同的東西，要分開來裝
- 用bat但SQL Script無法寫入?
  - 檢查檔案編碼，在不同台電腦支援不同編碼
  