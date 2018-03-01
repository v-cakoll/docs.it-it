---
title: 'Procedura: passare a un URL con il controllo WebBrowser'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a447d69eb6dafbff75ddd9d161abd4f78c607cdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedura: passare a un URL con il controllo WebBrowser
Esempio di codice seguente viene illustrato come passare il <xref:System.Windows.Forms.WebBrowser> controllo a un URL specifico.  
  
 Per determinare quando il nuovo documento è stato caricato completamente, gestire il <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. Per una dimostrazione di questo evento, vedere [procedura: stampare con un controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).  
  
## <a name="example"></a>Esempio  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.  
  
-   Riferimenti agli assembly `System` e `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [Controllo WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [Procedura: Stampare con un controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
