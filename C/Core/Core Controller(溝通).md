# 引入副程式
ex:NuGet、using.....
- using System.Web.Mvc; (ASP MVC FormCollection)
- using System.Web.Mvc; (SelectList支援集合元件用)
# 解決問題情境步驟
## Api


|標籤|取值|
|:--|:--|
|FormQuery|網址後面字串|
|FormBody|Request Body|
|FormForm|表單|
|FormHeader|Request Header|

## 表單
### [GET、POST表單](######form_Controller_ex)
### [Scaffold參考](https://ithelp.ithome.com.tw/articles/10243517)
### [Scaffold建立表單載入順序](######Scaffold_order_ex)
### [集合型元件來源函式宣告](######combobox_DataSource_ex)
## 其他
### [檔案下載函式宣告](######file_download_ex)

# 指令樣式
ex:function、object....

# limit
ex:臨界值
- TempData與ViewData差別?
  - 生命週期可以跨Action，ex:Delete Action沒有畫面成功之後在跳轉回Index 
- Controller內若不存在ViewData是否可調用?
  - 可以，預設null 
- API vs Web Controller?
  - inherit基底不同controller and controllerbase
  - controller除了原本Web API功能之外，還多了View相關
  - return abstract class也不同，API只回傳http code
  - [API解說](https://blog.miniasp.com/post/2019/09/16/ASPNET-Core-22-Web-API-Tips-and-Tricks)
  - [return code解析](https://www.cnblogs.com/landeanfen/p/5501487.html)
- 串接API return "ExceptionMessage": "找到多個符合下列要求的動作?
  - Controller參數預設型態宣告不能再宣告同樣，ex:[FormBody] class
- 串接API return "Message": "此資源不支援要求實體的媒體類型 'application/javascript'。"?
  - Controller參數預設型態串接不符，class = json
- POSTMAN串接API用js內語法不符?
  - POSTMAN都要雙引號 "Name":"add", 
- 套用ApiController差異再於?
  - 模型驗證失敗Controller內不會再寫Model.IsValid 
  - 取代會輸出JSON並且內部含status code 400
  - 必須搭配[RoutePrefix("Member")]、[Route("Get")] 
- Controller參數預設為?
  - 簡單型別[FormQuery]
  - 參考型別[FormBody]
  - IFormFile[FormForm] 
- Api優勢再於?
  - 當此服務需在多個平台上運行，ex:web、Android、IOS就可帶有類似提煉副程式功能 
- RESTful API不能帶有狀態性?
  - 若此服務需要呼叫2個API，但若其中1個API完成後就斷線了無法處理
- API核心要解決問題?
  - 資料交換的過程中，最重要的一環就是建立共識，或者說是建立原則以降低溝通成本
- return Json是否可對應到名稱cshtml?
  - 無法，只有View型態才行 
- API安全術語含義?
- API冪等術語含義? 
- 呼叫Api的Action找不到路徑?
  - api Router default為Controller/id,因為沒有加Action所以找不到
  - default參數要記得設定,否則會造成參數一定要打值情況
###### combobox_DataSource_ex
```
ViewData["pairClassIdNames"] = this.GetClassIdNames();
private List<KeyValuePair<string,string>> GetClassIdNames() 
{
    return this._dbContext.BookClass.GroupBy(r => new { r.BookClassId,r.BookClassName }).
        Select(r => new KeyValuePair<string,string>(r.Key.BookClassId,r.Key.BookClassName)).ToList();
}   
```

###### Scaffold_order_ex
- 先導出帶有CRUD Controller，名稱要抽換為Model表格名
- 將每個Action再推導出View


###### form_Controller_ex
- 載入頁面GET是否要載入集合型元件
- 提交頁面POST是否要載入集合型元件
- 防呆錯誤邏輯
- 驗證成功資料庫寫入與跳轉邏輯
```
public ActionResult Create()
{
    ViewData["pairClassIdNames"] = this.GetClassIdNames();
    return View();
}

// POST: BookController/Create
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create(BookData bookData)
{
    ViewData["pairClassIdNames"] = this.GetClassIdNames();

    if (ModelState.IsValid)
    {                
        bookData.BookStatus = "A";
        bookData.BookKeeper = "";
        bookData.CreateDate = DateTime.Now;
        bookData.CreateUser = "CreateUser";
        this._dbContext.BookData.Add(bookData);
        this._dbContext.SaveChanges();
        return RedirectToAction("Index");
    }

    return View(bookData);   
}

```

###### file_download_ex
```
using Microsoft.AspNetCore.StaticFiles;
public IActionResult GetFile()
{
    string file = @"C:\Program_Tsai\edit20220409網頁程式    \edit20210512\edit20210325\edit20210325\wwwroot\Debug.zip";
    string contentType = "";
    var provider = new FileExtensionContentTypeProvider();
    provider.TryGetContentType(file, out contentType);
    byte[] fileBytes = System.IO.File.ReadAllBytes(file);
    return File(fileBytes, contentType, "Debug.zip");
}
```
