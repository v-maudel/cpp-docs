---
title: "make_pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: ["cpp-cli"]
ms.topic: "reference"
f1_keywords: ["cliext::make_pair"]
dev_langs: ["C++"]
helpviewer_keywords: ["make_pair function [STL/CLR]"]
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
author: "mikeblome"
ms.author: "mblome"
ms.workload: ["cplusplus", "dotnet"]
---
# make_pair (STL/CLR)
Make a `pair` from a pair of values.  
  
## Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### Parameters  
 `Value1`  
 The type of the first wrapped value.  
  
 `Value2`  
 The type of the second wrapped value.  
  
 `first`  
 First value to wrap.  
  
 `second`  
 Second value to wrap.  
  
## Remarks  
 The template function returns `pair<Value1, Value2>(first, second)`. You use it to construct a `pair<Value1, Value2>` object from a pair of values.  
  
## Example  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  
  
## Requirements  
 **Header:** \<cliext/utility>  
  
 **Namespace:** cliext  
  
## See Also  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)