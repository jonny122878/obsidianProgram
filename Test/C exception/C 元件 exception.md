
[[exception 規範]]


- 疑惑點:將A元件event內寫ddl.DataSource=null並無將畫面來源給清空
- 情境:下拉選單來源為一層一層式選取,ex:選A => B => C(下拉選單),選B時會計算出C來源，當在重新選A時C(下拉選單)需要清空
- 判別:指令理解含意問題，應是ddl.Item.Clear()

- 錯誤訊息:ddl擁有的SelectIndex無效，因為它不在項目清單中
- 情境:同上為一層一層式選取結構，當已經選過C，再透過A控件重新觸發時，跳出exception
- 判別:清空來源時不需再加入ddl.DataBind(); 
  - ddl.Item.Clear(); //清畫面
  - ddl.DataSource=null; //清來源


- 錯誤訊息:名稱XXX元件,不存在目前的內容之中
- 情境:aspx原本是CodeFile轉換成CodeBehind
- 判別:確認檔案是否沒有轉成Web應用程式



- 疑惑點:Literal Label差異點
- 情境:
- 判別:Label為帶有html標籤,Literal則為純文字

- 疑惑點:DropDownList怎麼選項怎麼切event就是無trigger
- 情境:
- 判別:
- 檢查是否有加入AutoPostBack屬性
- event是否有掛載

- 疑惑點:button在OnClientClick用js防呆時,並無中斷PostBack到後端
- 情境:
- 判別:在調用時除了js function內部要return,OnClientClick = **return**


- 錯誤訊息:
  - ddl.SelectItem.Text=''，並未將物件參考設定為執行個體
  - ddl.SelectedIndexChanged，位置0沒有資料列
- 情境:
- 判別:
  - 子來源下拉來自父下拉，但是為PostBack觸發子下拉來源尚未載入
  - 使用者尚未選取任何項目，程式其他邏輯判別用此來做清空
  - 副程式調用UI狀態時，為了避免切換狀態後又重新切換回來，因此調用時一開始都先再用一次預設狀態

- 錯誤訊息:ddl擁有SelectedValue無效,因為它不在項目清單中,參數名稱value
- 情境:選擇有的資料帶入就沒問題,有的exception
- 判別:若來源資料有就不會exception,反之則有,重新檢查來源規則


## excel匯入失敗，出現insert很多欄位空白訊息
- 底部列位有空白列
- 上方列位也空白列
- 先推測其判別讀取列位中斷條件是再那欄
- 讀取sheet預設是那個




要考慮到全域狀態又更新回去問題
ex:
InitUI按照目前全域狀態更新
但是再回填資料時，呼叫副程式true or false狀態
又把原本狀態給修改回去
