

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
AP頁面上有textbox與cocmbobox,textbox.Enabled = false,用jQuery做類似selenium自動填單效果,讓其**不透過combobox 後台SelectIndexChanged event**去控制 textbox.Enabled,就可直接填單並將資料送入後台

# Question:
透過jQuery.removeAttr()...去移除掉ASP Prase **readonly、class**屬性,AP畫面上呈現是可開放給user填單並且有值,但後台接收值是空字元 textbox.Text = ""

# Answer:
因為不是透過[[ASP.NET機制]],所以後台要取值必須走原始HTTP協定去取值
```
Request.Form["Key"]
```
上述範例為html form method=post中UI元件
可透過[[VS Short Key]]監看式Requset.Form.AllKey去瀏覽

