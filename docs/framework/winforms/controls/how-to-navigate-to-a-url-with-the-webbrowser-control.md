---
title: 'Procedura: Passare a un URL con il controllo WebBrowser'
ms.date: 03/30/2017
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
ms.openlocfilehash: 8d592aea972a95a582cc35ecb14227edec5860ce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707235"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedura: Passare a un URL con il controllo WebBrowser
Esempio di codice seguente viene illustrato come passare il <xref:System.Windows.Forms.WebBrowser> controllo a un URL specifico.  
  
 Per determinare quando il nuovo documento è stato caricato completamente, gestire il <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. Per una dimostrazione di questo evento, vedere [come: Stampa con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md).  
  
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
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [Controllo WebBrowser](webbrowser-control-windows-forms.md)
- [Procedura: Stampa con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
