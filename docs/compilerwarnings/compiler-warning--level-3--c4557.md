---
title: "Compiler Warning (level 3) C4557"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4557"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4557"
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
caps.latest.revision: 7
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Compiler Warning (level 3) C4557
'__assume' contains effect 'effect'  
  
 The value passed to an [__assume](../intrinsics/__assume.md) statement2 was modified.  
  
 This warning is off by default. See [Compiler Warnings That Are Off by Default](../c/compiler-warnings-that-are-off-by-default.md) for more information.  
  
 The following sample generates C4557:  
  
```  
// C4557.cpp  
// compile with: /W3  
#pragma warning(default : 4557)  
int main()  
{  
   int i;  
   __assume(i++);   // C4557  
}  
```