[[exception 規範]]

- 疑惑點:用document.setAttribute('text','value')無法將其給指定到textbox?
- 情境:
- 判別:
  - ANS:textbox.Text = document.value 

- 疑惑點:
- 情境:當頁面唯讀狀態讓其不能編輯
- 判別:
  - ANS:document.setAttribute('disabled','disabled')
  - ps:此處連焦點與複製都無法調用


- 疑惑點:用document.getElementByID('ID').value 獲取textbox
- 情境:在aspx網站textbox Visible=false
- 判別:在做解析時會將整個DOM給移除 