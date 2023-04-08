ASPX特性:
- 疑惑點:Literal Label差異點
- 情境:
- 判別:Label為帶有html標籤,Literal則為純文字
- 疑惑點:button在OnClientClick用js防呆時,並無中斷PostBack到後端
- 情境:
- 判別:在調用時除了js function內部要return,OnClientClick = **return**
- 疑惑點:DropDownList怎麼選項怎麼切event就是無trigger
- 情境:
- 判別:
- 檢查是否有加入AutoPostBack屬性
- event是否有掛載



UI常見問題點:



- 疑惑點:將A元件event內寫ddl.DataSource=null並無將畫面來源給清空
- 情境:下拉選單來源為一層一層式選取,ex:選A => B => C(下拉選單),選B時會計算出C來源，當在重新選A時C(下拉選單)需要清空
- 判別:指令理解含意問題，應是ddl.Item.Clear()

- 錯誤訊息:ddl擁有的SelectIndex無效，因為它不在項目清單中
- 情境:同上為一層一層式選取結構，當已經選過C，再透過A控件重新觸發時，跳出exception
- 判別:清空來源時不需再加入ddl.DataBind(); 
  - ddl.Item.Clear(); //清畫面
  - ddl.DataSource=null; //清來源









要考慮到全域狀態又更新回去問題
ex:
InitUI按照目前全域狀態更新
但是再回填資料時，呼叫副程式true or false狀態
又把原本狀態給修改回去
