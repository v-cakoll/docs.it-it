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
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015820"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="08e65-102">Procedura: Passare a un URL con il controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="08e65-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="08e65-103">Nell'esempio di codice riportato di seguito viene illustrato <xref:System.Windows.Forms.WebBrowser> come spostare il controllo in un URL specifico.</span><span class="sxs-lookup"><span data-stu-id="08e65-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="08e65-104">Per determinare quando il nuovo documento è completamente caricato, gestire l' <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="08e65-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="08e65-105">Per una dimostrazione di questo evento, vedere [procedura: Stampare con un controllo](how-to-print-with-a-webbrowser-control.md)WebBrowser.</span><span class="sxs-lookup"><span data-stu-id="08e65-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="08e65-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="08e65-106">Example</span></span>

```vb
Me.webBrowser1.Navigate("http://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("http://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="08e65-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="08e65-107">Compiling the Code</span></span>
 <span data-ttu-id="08e65-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="08e65-108">This example requires:</span></span>

- <span data-ttu-id="08e65-109">Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="08e65-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="08e65-110">Riferimenti agli assembly `System` e `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="08e65-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="08e65-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08e65-111">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="08e65-112">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="08e65-112">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="08e65-113">Procedura: Stampare con un controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="08e65-113">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
