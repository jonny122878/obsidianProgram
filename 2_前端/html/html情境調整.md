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
[[bootstrap exception]]
# Note


# 引入副程式
ex:NuGet、using.....

# 解決問題情境步驟
## 表單
### 組成元素
from內一定要有input綁定才會有提交效果
### 偽元素
同個html tag，要寫一起
### [checkbox](######checkbox_ex)
## 排版
### [將div並排](######div_並排_ex)

# 指令樣式
ex:function、object....



## tag
- br 
- p
- header
## 功能
- 單行
- 強制換行
- chorme prase information



# limit
ex:臨界值


###### checkbox_ex
- input of tag **checkbox**
- id of input and for of label are same
```
 <input type="checkbox" id="a" value="a">
 <label for="a">甲</label>
 <input type="checkbox" id="b" value="b">
 <label for="b">乙</label>
 <input type="checkbox" id="c" value="c">
 <label for="c">丙</label>
 <input type="checkbox" id="d" value="d">
 <label for="d">丁</label>
```

###### div_並排_ex
```
<div style = "width:400px">//子元素按照父容器的設定
    <div style = float:left; width:15%></div>
    <div style = float:left; width:85%></div>
</div>
```

