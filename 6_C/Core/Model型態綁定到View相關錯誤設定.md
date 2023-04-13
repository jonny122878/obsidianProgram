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
1.the ViewDataDictionary instance requires a model item of type ToList()
2.View An error occurred while processing youre request Request ID:..... 
# Answer:
1.為了EF效能最後在呈現時遺漏做實體化
2.View Prase Model傳來**object**並無按照原本型別去Prase