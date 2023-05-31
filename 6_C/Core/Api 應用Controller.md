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

# Evergreen Note
Highlight:
Question:
Answer:
# Summary

#### 若要遵循Restful寫法差異在於?
- 主要是透過Verb去區分CRUD，衍生出沒有Action分類選項
```
api/controller/?param....
```
#### API vs Web Controller?
  - inherit基底不同controller and controllerbase
  - controller除了原本Web API功能之外，還多了View相關
  - return abstract class也不同，API只回傳http code
  - [API解說](https://blog.miniasp.com/post/2019/09/16/ASPNET-Core-22-Web-API-Tips-and-Tricks)
  - [return code解析](https://www.cnblogs.com/landeanfen/p/5501487.html)
但實務面上，return是希望有代碼表了解相關後端錯誤訊息，因此偏好inherit Contoller
ex:
|編碼|對應訊息|
|D0001|查無資料|
```
    public class ResponseModel
    {
        /// <summary>
        /// 是否成功
        /// </summary>
        public bool IsOk { get; set; } = true;

        /// <summary>
        /// 回傳代碼, 參考RETURN_CODE Enum
        /// </summary>
        public string Code { get; set; } = string.Empty;

        /// <summary>
        /// 回傳訊息
        /// </summary>
        public string Msg { get; set; } = string.Empty;

        /// <summary>
        /// 泛型資料
        /// </summary>
        public Object? Data { get; set; }
    }
```
#### 套用ApiController差異再於?
  - 模型驗證失敗Controller內不會再寫Model.IsValid 
  - 取代會輸出JSON並且內部含status code 400
  - 必須搭配RoutePrefix、Route
```
[Route("[controller]/[action]")]  
```
#### API解決的問題
- 當此服務需在多個平台上運行，ex:web、Android、IOS就可帶有類似提煉副程式功能 
- 資料交換的過程中，最重要的一環就是建立共識，或者說是建立原則以降低溝通成本
- 衍生設計為何API不能帶有狀態性?
  - 若此服務需要呼叫2個API，但若其中1個API完成後就斷線了無法處理


# Note
