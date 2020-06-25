---
title: 'Procedura: passare a un URL con il controllo WebBrowser'
description: Informazioni su come usare il controllo Windows Forms WebBrowser. Navigate per passare a un URL specifico. Vengono inoltre fornite informazioni su come determinare quando viene caricato il nuovo documento.
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
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325576"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="542e0-104">Procedura: passare a un URL con il controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="542e0-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="542e0-105">Nell'esempio di codice riportato di seguito viene illustrato come spostare il <xref:System.Windows.Forms.WebBrowser> controllo in un URL specifico.</span><span class="sxs-lookup"><span data-stu-id="542e0-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="542e0-106">Per determinare quando il nuovo documento è completamente caricato, gestire l' <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="542e0-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="542e0-107">Per una dimostrazione di questo evento, vedere [procedura: stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="542e0-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="542e0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="542e0-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="542e0-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="542e0-109">Compiling the Code</span></span>
 <span data-ttu-id="542e0-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="542e0-110">This example requires:</span></span>

- <span data-ttu-id="542e0-111">Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="542e0-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="542e0-112">Riferimenti agli assembly `System` e `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="542e0-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="542e0-113">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="542e0-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="542e0-114">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="542e0-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="542e0-115">Procedura: stampare con un controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="542e0-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
