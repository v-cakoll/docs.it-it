---
title: 'Procedura: Creare un visualizzatore di documenti HTML in un''applicazione Windows Forms'
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
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58f964be53c6ddb8abf0af539b773344ce09d948
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="3264d-102">Procedura: Creare un visualizzatore di documenti HTML in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3264d-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="3264d-103">È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per visualizzare e stampare documenti HTML senza fornire la funzionalità completa di un browser Internet.</span><span class="sxs-lookup"><span data-stu-id="3264d-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="3264d-104">Ciò è utile quando si desidera avvalersi delle funzionalità di formattazione HTML, ma non si desidera che gli utenti per caricare pagine Web arbitrarie che può contenere i controlli Web non attendibili o codice di script potenzialmente dannosi.</span><span class="sxs-lookup"><span data-stu-id="3264d-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="3264d-105">È possibile limitare la capacità del <xref:System.Windows.Forms.WebBrowser> controllare in questo modo, ad esempio, per utilizzarlo come un visualizzatore di posta elettronica HTML o per fornire la Guida in formato HTML nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3264d-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="3264d-106">Per creare un visualizzatore di documenti HTML</span><span class="sxs-lookup"><span data-stu-id="3264d-106">To create an HTML document viewer</span></span>  
  
1.  <span data-ttu-id="3264d-107">Impostare il <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> proprietà `false` per impedire il <xref:System.Windows.Forms.WebBrowser> aprire i file trascinati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="3264d-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <span data-ttu-id="3264d-108">Impostare il <xref:System.Windows.Forms.WebBrowser.Url%2A> proprietà al percorso del file iniziale da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3264d-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3264d-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3264d-109">Compiling the Code</span></span>  
 <span data-ttu-id="3264d-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3264d-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3264d-111">Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="3264d-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="3264d-112">Riferimenti agli assembly `System` e `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="3264d-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3264d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3264d-113">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [<span data-ttu-id="3264d-114">Panoramica sul controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="3264d-114">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="3264d-115">Sicurezza dei controlli WebBrowser</span><span class="sxs-lookup"><span data-stu-id="3264d-115">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [<span data-ttu-id="3264d-116">Procedura: Passare a un URL con il controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="3264d-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="3264d-117">Procedura: Stampare con un controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="3264d-117">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
