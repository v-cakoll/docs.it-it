---
title: Aggiungere funzionalità del browser Web all'app
description: Informazioni su come aggiungere funzionalità del browser Web a una Windows Forms Application con il controllo WebBrowser.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: a5a33961ac8301bda86bb5f34e65ac159308987f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174549"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="8606d-103">Come aggiungere funzionalità del browser Web a un Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="8606d-103">How to add web browser capabilities to a Windows Forms application</span></span>

<span data-ttu-id="8606d-104">Il controllo <xref:System.Windows.Forms.WebBrowser> consente di aggiungere funzionalità del Web browser all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8606d-104">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="8606d-105">Per impostazione predefinita, il controllo funziona come un Web browser.</span><span class="sxs-lookup"><span data-stu-id="8606d-105">The control works like a Web browser by default.</span></span> <span data-ttu-id="8606d-106">Dopo aver caricato un URL iniziale mediante l'impostazione della proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A>, è possibile fare clic sui collegamenti ipertestuali o usare i tasti di scelta rapida per muoversi in avanti o all'indietro nella cronologia di spostamento.</span><span class="sxs-lookup"><span data-stu-id="8606d-106">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="8606d-107">Per impostazione predefinita, è possibile accedere ad altre funzionalità del browser mediante il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="8606d-107">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="8606d-108">È anche possibile aprire nuovi documenti trascinandoli e rilasciandoli sul controllo.</span><span class="sxs-lookup"><span data-stu-id="8606d-108">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="8606d-109">Il controllo <xref:System.Windows.Forms.WebBrowser> dispone anche di numerose proprietà, metodi ed eventi che possono essere usati per implementare funzionalità dell'interfaccia utente simili a quelle disponibili in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8606d-109">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>

<span data-ttu-id="8606d-110">Nell'esempio di codice seguente vengono implementati una barra degli indirizzi, i tipici pulsanti del browser, un menu **File**, una barra di stato e una barra del titolo contenente il titolo della pagina corrente.</span><span class="sxs-lookup"><span data-stu-id="8606d-110">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>

## <a name="example"></a><span data-ttu-id="8606d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8606d-111">Example</span></span>

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a><span data-ttu-id="8606d-112">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="8606d-112">Compile the code</span></span>

<span data-ttu-id="8606d-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8606d-113">This example requires:</span></span>

- <span data-ttu-id="8606d-114">Riferimenti agli assembly `System`, `System.Drawing` e `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="8606d-114">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="8606d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8606d-115">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="8606d-116">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="8606d-116">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
