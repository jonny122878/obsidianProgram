# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::
Review::
Restructure::true
http code
debug reflection

#work #知識 
# Unify
- 模塊之間會有相依性
- 通訊衍生相關
- Reflection exception比較不相同
- 端點服務可選擇Api或Web

1. #flashcards 
- Highlight:權限控管要將SESSION injection
- Question:Session has not been configured for this application or request
?
- Answer:若要調用AddHttpContextAccessor一定要先AddSession，二者間有**相依性**
**模塊引入和流程**都需要調用設定才會生效，AddSession 但無app.UseSession也會丟exception

2. #flashcards 
- Highlight:
- Question:localhost目前無法處理此要求 HTTP ERROR 500
?
- Answer:DI Controller but Startup not injection

3. #flashcards 
- Highlight:CORS
- Question:Access to XMLHttpRequest at 'https://localhost:7148/WeatherForecast' from origin 'http://localhost:8080' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
?
- Answer:設定下方後記得重啟瀏覽器清除cookie
```
builder.Services.AddCors(option =>
{
    option.AddPolicy("corsPolicy",builder =>
    {
        builder.AllowAnyOrigin().
        AllowAnyHeader().
        AllowAnyMethod();
    });
});
app.UseCors("corsPolicy");
[EnableCors("corsPolicy")]
```

4. #flashcards 
- Highlight:
- Question:無法啟動網站伺服器,但是debug又無錯誤並且查詢無佔port
?
- Answer:看輸出Microsoft.Extensions.DependencyInjection.dll,組件用命名空間名稱依賴注入錯誤原因

5. #flashcards 
- Highlight:
- Question:Program Api and Razor設定差異
?
- Answer:一個結束路由端點造訪為Api
```
AddControllersWithViews
AddControllers
AddEndpointsApiExplorer
```


6. #flashcards 
- Highlight:
- Question:
?
- Answer:
