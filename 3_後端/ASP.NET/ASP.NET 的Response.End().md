---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:

# Question:
當您在 ASP.NET 的程式碼中使用 Response.End() 時，有可能會出現“無法評估運算式，因為程式碼已經最佳化”的錯誤。這是因為在 ASP.NET 的某些版本中，這種方式可能會導致程式碼執行的問題。
# Answer:
為了避免這個問題，您可以改用 Response.Flush() 方法來將數據流刷新到瀏覽器，然後使用 HttpContext.Current.ApplicationInstance.CompleteRequest() 方法來結束頁面的處理。