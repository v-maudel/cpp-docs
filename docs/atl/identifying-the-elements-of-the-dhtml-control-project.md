---
title: "Identifying the Elements of the DHTML Control Project"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HTML controls, ATL support"
  - "DHTML controls, ATL support"
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: 9
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Identifying the Elements of the DHTML Control Project
Most DHTML control code is exactly like that created for any ATL control. For a basic understanding of the generic code, work through the [ATL tutorial](../atl/active-template-library--atl--tutorial.md), and read the sections [Creating an ATL Project](../atl/creating-an-atl-project.md) and [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md).  
  
 A DHTML control is similar to any ATL control, except:  
  
-   In addition to the regular interfaces a control implements, it implements an additional interface that is used to communicate between the C++ code and the HTML user interface (UI). The HTML UI calls into C++ code using this interface.  
  
-   It creates an HTML resource for the control UI.  
  
-   It allows access to the DHTML object model through the member variable `m_spBrowser`, which is a smart pointer of type [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx). Use this pointer to access any part of the DHTML object model.  
  
 The following graphic illustrates the relationship between your DLL, the DHTML control, the Web browser, and the HTML resource.  
  
 ![Elements of a DHTML control project](../atl/media/vc52en1.gif "vc52EN1")  
  
> [!NOTE]
>  The names on this graphic are placeholders. The names of your HTML resource and the interfaces exposed on your control are based on the names you assign them in the ATL Control Wizard.  
  
 In this graphic, the elements are:  
  
-   **My DLL** The DLL created using the ATL Project Wizard.  
  
-   **DHTML Control** (`m_spBrowser`)   The DHTML control, created using the ATL Object Wizard. This control accesses the Web browser object and its methods through the Web browser object's interface, **IWebBrowser2**. The control itself exposes the following two interfaces, in addition to the other standard interfaces required for a control.  
  
    -   **IDHCTL1** The interface exposed by the control for use only by the container.  
  
    -   **IDHCTLUI1** The dispatch interface for communicating between the C++ code and the HTML user interface. The Web browser uses the control's dispatch interface to display the control. You can call various methods of this dispatch interface from the control's user interface by invoking `window.external`, followed by the method name on this dispatch interface that you want to invoke. You would access `window.external` from a SCRIPT tag within the HTML that makes up the UI for this control. For more information about invoking external methods in the resource file, see [Calling C++ Code from DHTML](../atl/calling-c---code-from-dhtml.md).  
  
-   **IDR_CTL1** The resource ID of the HTML resource. Its file name, in this case, is DHCTL1UI.htm. The DHTML control uses an HTML resource that contains standard HTML tags and external window dispatch commands that you can edit using the Text editor.  
  
-   **Web Browser** The Web browser displays the control's UI, based on the HTML in the HTML resource. A pointer to the Web browser's **IWebBrowser2** interface is available in the DHTML control to allow access to the DHTML object model.  
  
 The ATL Control Wizard generates a control with default code in both the HTML resource and the .cpp file. You can compile and run the control as generated by the wizard, and then view the control in either the Web browser or the ActiveX Control Test Container. The picture below shows the default ATL DHTML control with three buttons displayed in Test Container:  
  
 ![ATL DHTML control](../atl/media/vc52en2.gif "vc52EN2")  
  
 See [Creating an ATL DHTML Control](../atl/creating-an-atl-dhtml-control.md) to get started building a DHTML control. See [Testing Properties and Events with Test Container](../mfc/testing-properties-and-events-with-test-container.md) for information on how to access Test Container.  
  
## See Also  
 [Support for DHTML Control](../atl/atl-support-for-dhtml-controls.md)