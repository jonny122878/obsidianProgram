---
data
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:
Author:
Note Type:
Topics:
#資料 

# Evergreen Note
Highlight:
Question:
Answer:
# Summary
#### TempData與ViewData差別?
  - 生命週期可以跨Action，ex:Delete Action沒有畫面成功之後在跳轉回Index 
#### Controller內若不存在ViewData是否可調用?
  - 可以，預設null 
#### Controller參數預設為?
  - 簡單型別[FormQuery]
  - 參考型別[FormBody]
  - IFormFile[FromForm] 

[[Api 應用Controller]]
[[Web應用Controller]]
# Note
#### 引入副程式
ex:NuGet、using.....
- using System.Web.Mvc; (ASP MVC FormCollection)
- using System.Web.Mvc; (SelectList支援集合元件用)

#### 參數種類
|標籤|取值|
|:--|:--|
|FormQuery|網址後面字串|
|FormBody|Request Body|
|FromForm|表單|
|FormHeader|Request Header|

## 表單
### [GET、POST表單](######form_Controller_ex)
### [Scaffold參考](https://ithelp.ithome.com.tw/articles/10243517)
### [Scaffold建立表單載入順序](######Scaffold_order_ex)
### [集合型元件來源函式宣告](######combobox_DataSource_ex)
## 其他
### [檔案下載函式宣告](######file_download_ex)





- return Json是否可對應到名稱cshtml?
  - 無法，只有View型態才行 

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
