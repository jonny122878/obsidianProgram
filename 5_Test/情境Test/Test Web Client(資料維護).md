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

#金財通 #知識 

# Unify
- 元件有**階層性**時，父元件重新選擇時子與孫都需要初始化
- 元件本身**視覺**跟選取值做變動，直覺都只注意視覺，特別注意值也要初始
- 資料庫欄位增加時需考慮**對應投射**使用者元件是否正常



1. #flashcards 
- Highlight:在ASP.NET對應連線資料庫欄位做異動
- Question:ddl擁有SelectedValue無效,因為它不在項目清單中,參數名稱value。為何選擇有的資料帶入就沒問題,有的exception
?
- Answer:若來源資料有就不會exception,反之則有,通常為來源資料庫值有做異動，或是增加新欄位

2. #flashcards 
- Highlight:
- Question:
?
- Answer:

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
- Highlight:
- Question:
?
- Answer:

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
