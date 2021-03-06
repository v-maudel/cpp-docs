---
title: "CDynamicAccessor::GetBlobHandling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: ["cpp-data"]
ms.topic: "reference"
f1_keywords: ["ATL.CDynamicAccessor.GetBlobHandling", "CDynamicAccessor::GetBlobHandling", "ATL::CDynamicAccessor::GetBlobHandling", "GetBlobHandling", "CDynamicAccessor.GetBlobHandling"]
dev_langs: ["C++"]
helpviewer_keywords: ["GetBlobHandling method"]
ms.assetid: bbc6dda6-e132-42a3-980d-24e455cbe456
author: "mikeblome"
ms.author: "mblome"
ms.workload: ["cplusplus", "data-storage"]
---
# CDynamicAccessor::GetBlobHandling
Retrieves the BLOB handling value for the current row.  
  
## Syntax  
  
```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;  
  
```  
  
## Remarks  
 Returns the BLOB handling value `eBlobHandling` as set by [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md).  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [CDynamicAccessor Class](../../data/oledb/cdynamicaccessor-class.md)