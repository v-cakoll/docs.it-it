---
title: Utilizzare il Document Object Model HTML gestito
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff1004248e709b4b4913b90eb81f0726ab390c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="69a7b-102">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="69a7b-103">Il modello a oggetti documento (DOM) HTML gestito fornisce un wrapper basato sul [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per le classi HTML esposte da Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="69a7b-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="69a7b-104">Usare queste classi per modificare pagine HTML ospitate nel <xref:System.Windows.Forms.WebBrowser> (controllo), o per creare nuove pagine dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="69a7b-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69a7b-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="69a7b-105">In This Section</span></span>  
 [<span data-ttu-id="69a7b-106">Procedura: Accedere al Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="69a7b-107">Viene descritto come ottenere un'istanza valida di <xref:System.Windows.Forms.HtmlDocument> da un'applicazione di Windows Form o un <xref:System.Windows.Forms.UserControl> ospitata in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="69a7b-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="69a7b-108">Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="69a7b-109">Viene descritto come ottenere l'origine HTML originale, non modificato e come ottenere l'origine "live" che riflette lo stato corrente del DOM.</span><span class="sxs-lookup"><span data-stu-id="69a7b-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="69a7b-110">Procedura: Modificare gli stili di un elemento nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="69a7b-111">Viene descritto come modificare gli stili, che consentono di controllare l'aspetto visivo di elementi.</span><span class="sxs-lookup"><span data-stu-id="69a7b-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="69a7b-112">Accesso a frame nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="69a7b-113">Vengono descritte le frame e pagine con frame e come accedere al DOM di un frame.</span><span class="sxs-lookup"><span data-stu-id="69a7b-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="69a7b-114">Accesso ai membri non esposti del Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="69a7b-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="69a7b-115">Viene descritto come accedere ai membri del DOM sottostante che non possiedono un equivalente gestito.</span><span class="sxs-lookup"><span data-stu-id="69a7b-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="69a7b-116">Riferimento</span><span class="sxs-lookup"><span data-stu-id="69a7b-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="69a7b-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="69a7b-117">Related Sections</span></span>  
 [<span data-ttu-id="69a7b-118">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="69a7b-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="69a7b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69a7b-119">See Also</span></span>  
 [<span data-ttu-id="69a7b-120">Sul modello a oggetti DHTML</span><span class="sxs-lookup"><span data-stu-id="69a7b-120">About the DHTML Object Model</span></span>](http://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
