---
title: "_mbbtype, _mbbtype_l"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbbtype"
  - "_mbbtype_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbbtype_l"
  - "mbbtype"
  - "mbbtype_l"
  - "_mbbtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbbtype function"
  - "_mbbtype_l function"
  - "mbbtype function"
  - "mbbtype_l function"
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 18
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
# _mbbtype, _mbbtype_l
Returns the byte type, based on the previous byte.  
  
> [!IMPORTANT]
>  This API cannot be used in applications that execute in the [!INCLUDE[wrt](../atl/includes/wrt_md.md)]. For more information, see [CRT functions not supported with /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### Parameters  
 `c`  
 The character to test.  
  
 `type`  
 The type of byte to test for.  
  
 `locale`  
 The locale to use.  
  
## Return Value  
 `_mbbtype` returns the type of byte in a string. This decision is context-sensitive, as specified by the value of `type`, which provides the control test condition. `type` is the type of the previous byte in the string. The manifest constants in the following table are defined in Mbctype.h.  
  
|Value of `type`|`_mbbtype` tests for|Return value|`c`|  
|---------------------|--------------------------|------------------|---------|  
|Any value except 1|Valid single byte or lead byte|`_MBC_SINGLE` (0)|Single byte (0x20 – 0x7E, 0xA1 – 0xDF)|  
|Any value except 1|Valid single byte or lead byte|`_MBC_LEAD` (1)|Lead byte of multibyte character (0x81 – 0x9F, 0xE0 – 0xFC)|  
|Any value except 1|Valid single-byte or lead byte|`_MBC_ILLEGAL`<br /><br /> ( –1)|Invalid character (any value except 0x20 – 0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|  
|1|Valid trail byte|`_MBC_TRAIL` (2)|Trailing byte of multibyte character (0x40 – 0x7E, 0x80 – 0xFC)|  
|1|Valid trail byte|`_MBC_ILLEGAL`<br /><br /> ( –1)|Invalid character (any value except 0x20 – 0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|  
  
## Remarks  
 The `_mbbtype` function determines the type of a byte in a multibyte character. If the value of `type` is any value except 1, `_mbbtype` tests for a valid single-byte or lead byte of a multibyte character. If the value of `type` is 1, `_mbbtype` tests for a valid trail byte of a multibyte character.  
  
 The output value is affected by the setting of the `LC_CTYPE` category setting of the locale; see [setlocale, _wsetlocale](../crt/setlocale--_wsetlocale.md) for more information. The `_mbbtype` version of this function uses the current locale for this locale-dependent behavior; the `_mbbtype_l` version is identical except that it use the locale parameter that's passed in instead. For more information, see [Locale](../crt/locale.md).  
  
 In earlier versions, `_mbbtype` was named `chkctype`. For new code, use `_mbbtype` instead.  
  
## Requirements  
  
|Routine|Required header|Optional header|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* For definitions of manifest constants that are used as return values.  
  
 For more compatibility information, see [Compatibility](../crt/compatibility.md).  
  
## .NET Framework Equivalent  
 Not applicable, but see [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## See Also  
 [Byte Classification](../crt/byte-classification.md)