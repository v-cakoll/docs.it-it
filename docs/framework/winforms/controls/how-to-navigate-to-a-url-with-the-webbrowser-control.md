---
title: 'Procedura: passare a un URL con il controllo WebBrowser'
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
ms.openlocfilehash: f6cb26ff247bba75cc351d453314bade2d38d9f5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144838"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Procedura: passare a un URL con il controllo WebBrowser
Nell'esempio di codice riportato di seguito viene illustrato come spostare il <xref:System.Windows.Forms.WebBrowser> controllo in un URL specifico.

 Per determinare quando il nuovo documento è completamente caricato, gestire l' <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento. Per una dimostrazione di questo evento, vedere [procedura: stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md).

## <a name="example"></a>Esempio

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a>Compilazione del codice
 L'esempio presenta i requisiti seguenti:

- Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.

- Riferimenti agli assembly `System` e `System.Windows.Forms`.

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [Controllo WebBrowser](webbrowser-control-windows-forms.md)
- [Procedura: stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
