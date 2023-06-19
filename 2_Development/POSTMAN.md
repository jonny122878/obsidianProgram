---
data
aliases
---
# Metadata
Status:發芽
Source Type:江，心得
Source URL:
Project:早點下班、金財通
Author:
Note Type:
Topics:

# Evergreen Note
Highlight:
Question:
Answer:
# Summary
#### POST操作Step
  - 設定Verb
  - 設定資源
  - 設定Header(POST Verb才需要)
    - Key:Content-Type
    - Value:application/x-www-form-urlencoded
    - Value:multipart/form-data(上傳檔案)
  - 組合結果: https://url/Controller/Action?name1=value1&name2=value2
#### POST中FromBody參數設定
- 夾帶位置是否為Body
- 格式是否為raw
- 型別為JSON(application/json)
- 會有直覺錯誤參數情境
```
ActionName ([FromBody] long sysSettingId)
{sysSettingId:10}
10
```
ps:第一行結果為直覺上錯誤，其非JSON並無KEY，直接傳數字即可
- 後端接收reponse參數參考[[Core Controller特性]]和[[Api 應用Controller]]
POSTMAN在發送時相關錯誤資訊參考如下:
- [[http code exception]]
- [[API Prase JSON簽章和參數相關問題]]

#### 應用
- 寫前後分離專案時可先透過此工具模擬server，讓前端先行test
- 撰寫測試案例進行流程驗證
  - 疑問點:API為無狀態，此情況為何需要寫一組測試案例
  - ex:像是第三放認證這種相關需求，假如寫個購物網要扣點，但是必定要先驗證身分，因此就會產生一個以上API交互關係，此種情境就很合適

- [[POSTMAN FastKey情境]]
[Chorme POSTMAN載點](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=zh-TW)
# Note
