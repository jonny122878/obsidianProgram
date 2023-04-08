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

# Note
Cookie 是存儲在客戶端瀏覽器上的小文件，通常包含一些關於用戶的信息，例如用戶名稱和密碼，或者用戶的偏好設置。當用戶發送請求到 Web 應用時，瀏覽器會自動在請求中包含這些 Cookie，Web 應用可以使用這些 Cookie 來識別用戶和維護會話狀態。

Session 是一個在伺服器端維護的會話，它通常用來保存用戶的狀態信息，例如登錄狀態、購物車內容等。當用戶發送請求時，Web 應用會使用一個 Session ID 識別用戶的會話，並在伺服器端維護用戶的狀態。Session ID 通常是一個隨機生成的字串，可以存儲在 Cookie 中，也可以在 URL 參數中傳遞。

以下是 Cookie 和 Session 的應用：

1.  身份驗證：可以使用 Cookie 或 Session 來保存用戶的登錄狀態，當用戶成功登錄後，Web 應用可以在客戶端設置一個登錄用的 Cookie 或 Session，並在後續的請求中使用它來驗證用戶的身份。
    
2.  購物車：可以使用 Session 來保存用戶的購物車內容，當用戶添加商品到購物車中時，Web 應用可以在伺服器端維護用戶的購物車內容，並將 Session ID 存儲在 Cookie 中。
    
3.  多語言支持：可以使用 Cookie 或 Session 來保存用戶的語言偏好設置，當用戶首次訪問 Web 應用時，Web 應用可以通過瀏覽器的語言設置來猜測用戶的語言偏好，並將其存儲在 Cookie 或 Session 中。
    

總之，Cookie 和 Session 是 Web 應用中常見的狀態管理機制，它們可以用於身份驗證、購物車、多語言支持等方面，可以幫助開發人員實現更豐富、更具交互性的 Web 應用。