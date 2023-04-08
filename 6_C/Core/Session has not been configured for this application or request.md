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

# Answer:
若要調用AddHttpContextAccessor一定要先AddSession，二者間有相依性
**模塊引入和流程**都需要調用設定才會生效，AddSession 但無app.UseSession也會丟exception
