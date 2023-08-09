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
Topics::Test、review

# Unify

#知識 #work 

# Unify
- 元件有**階層性**時，父元件重新選擇時子與孫都需要初始化
- 元件本身**視覺**跟選取值做變動，直覺都只注意視覺，特別注意值也要初始
- 資料庫欄位增加時需考慮**對應投射**使用者元件是否正常
- 測試時要按照全局變數都跑過，ex:新增、編輯、唯讀
- 使用者所有能輸入元件焦點都要考慮防呆，以及輸入順序性


1. #flashcards 
- Highlight:在ASP.NET對應連線資料庫欄位做異動
- Question:ddl擁有SelectedValue無效,因為它不在項目清單中,參數名稱value。為何選擇有的資料帶入就沒問題,有的exception
?
- Answer:若來源資料有就不會exception,反之則有,通常為來源資料庫值有做異動，或是增加新欄位

2. #flashcards 
- Highlight:在Angular中先選取地址之後在選取險種，設計上使用者選取順序如上
- Question:存取資料發生地址UI無值情況
?
- Answer:無考量到選取的焦點UI，可以再次選取

3. #flashcards 
- Highlight:在ASP.NET，客戶希望在原本ddl來源加入一個其他選項，選擇其他會跑出一個textbox讓其能將其他選項相關備註資訊給填入
- Question:客戶反應DB內有不是其他選項的備註欄位也有資訊
?
- Answer:視覺元件須考慮重置初始值，當在選擇其他選項時除了textbox visible之外，內含Text也需清空，避免造成殘留值情況


4. #flashcards 
- Highlight:在ASP.NET
- Question:為何選取ddl會出現如下:
  - ddl.SelectItem.Text=''，並未將物件參考設定為執行個體
  - ddl.SelectedIndexChanged，位置0沒有資料列
?
- Answer:
  - 所點擊ddl帶有**階層特性**，子來源下拉來自父下拉，但是為PostBack觸發子下拉來源尚未載入
  - 使用者尚未選取任何項目，程式**其他邏輯**判別用此來做清空
  - 副程式調用UI狀態時，為了避免切換狀態後又重新切換回來，因此調用時一開始都先再用一次預設狀態


5. #flashcards 
- Highlight:檢查文字框輸入是否正常
- Question:原本寫re丟出錯誤
?
- Answer:防呆時特別考慮**跳脫性類型**,像是使用者元件只能輸入數字型別時,但你再規範re時,不會去判別空字元情況 

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
