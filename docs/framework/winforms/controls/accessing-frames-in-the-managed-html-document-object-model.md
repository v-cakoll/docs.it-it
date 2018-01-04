---
title: Accesso a frame nel Document Object Model HTML gestito
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTML [Windows Forms], dOM
- managed HTML DOM
- HTML [Windows Forms], managed
- HTML DOM [Windows Forms], managed
- frames [Windows Forms], accessing
- DOM [Windows Forms], accessing frames in managed HTML
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9355596982025bf9834924a0de8e79e7073fc0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-frames-in-the-managed-html-document-object-model"></a><span data-ttu-id="8c19c-102">Accesso a frame nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="8c19c-102">Accessing Frames in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="8c19c-103">Alcuni documenti HTML sono composti da *frame*, o windows che può contenere i propri documenti HTML distinti.</span><span class="sxs-lookup"><span data-stu-id="8c19c-103">Some HTML documents are composed out of *frames*, or windows that can hold their own distinct HTML documents.</span></span> <span data-ttu-id="8c19c-104">Con i frame è possibile creare facilmente pagine HTML in cui una o più parti della pagina sono statiche, ad esempio una barra di spostamento, mentre il contenuto degli altri frame cambia continuamente.</span><span class="sxs-lookup"><span data-stu-id="8c19c-104">Using frames makes it easy to create HTML pages in which one or more pieces of the page remain static, such as a navigation bar, while other frames constantly change their content.</span></span>  
  
 <span data-ttu-id="8c19c-105">Gli autori di documenti HTML possono creare i frame in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c19c-105">HTML authors can create frames in one of two ways:</span></span>  
  
-   <span data-ttu-id="8c19c-106">Usando i tag `FRAMESET` e `FRAME`, che creano finestre fisse.</span><span class="sxs-lookup"><span data-stu-id="8c19c-106">Using the `FRAMESET` and `FRAME` tags, which create fixed windows.</span></span>  
  
 <span data-ttu-id="8c19c-107">-oppure-</span><span class="sxs-lookup"><span data-stu-id="8c19c-107">-or-</span></span>  
  
-   <span data-ttu-id="8c19c-108">Usando il tag `IFRAME`, che crea una finestra mobile che può essere riposizionata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c19c-108">Using the `IFRAME` tag, which creates a floating window that can be repositioned at run time.</span></span>  
  
1.  <span data-ttu-id="8c19c-109">Poiché i frame contengono documenti HTML, vengono rappresentati in Document Object Model (DOM) sia come elementi finestra che come elementi frame.</span><span class="sxs-lookup"><span data-stu-id="8c19c-109">Because frames contain HTML documents, they are represented in the Document Object Model (DOM) as both window elements and frame elements.</span></span>  
  
2.  <span data-ttu-id="8c19c-110">Quando si accede a un tag `FRAME` o `IFRAME` usando la raccolta Frames di <xref:System.Windows.Forms.HtmlWindow>, si recupererà l'elemento finestra corrispondente al frame.</span><span class="sxs-lookup"><span data-stu-id="8c19c-110">When you access a `FRAME` or `IFRAME` tag by using the Frames collection of <xref:System.Windows.Forms.HtmlWindow>, you are retrieving the window element corresponding to the frame.</span></span> <span data-ttu-id="8c19c-111">Questo rappresenta tutte le proprietà dinamiche del frame, ad esempio l'URL, il documento e le dimensioni correnti.</span><span class="sxs-lookup"><span data-stu-id="8c19c-111">This represents all of the frame's dynamic properties, such as its current URL, document, and size.</span></span>  
  
3.  <span data-ttu-id="8c19c-112">Quando si accede a un tag `FRAME` o `IFRAME` usando la proprietà <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> di <xref:System.Windows.Forms.HtmlWindow>, la raccolta <xref:System.Windows.Forms.HtmlElement.Children%2A> oppure metodi come <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> o <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, si recupererà l'elemento frame.</span><span class="sxs-lookup"><span data-stu-id="8c19c-112">When you access a `FRAME` or `IFRAME` tag by using the <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> property of <xref:System.Windows.Forms.HtmlWindow>, the <xref:System.Windows.Forms.HtmlElement.Children%2A> collection, or methods such as <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> or <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>, you are retrieving the frame element.</span></span> <span data-ttu-id="8c19c-113">Questo rappresenta le proprietà statiche del frame, incluso l'URL specificato nel file HTML originale.</span><span class="sxs-lookup"><span data-stu-id="8c19c-113">This represents the static properties of the frame, including the URL specified in the original HTML file.</span></span>  
  
## <a name="frames-and-security"></a><span data-ttu-id="8c19c-114">Frame e sicurezza</span><span class="sxs-lookup"><span data-stu-id="8c19c-114">Frames and Security</span></span>  
 <span data-ttu-id="8c19c-115">Accesso a frame è complicato dal fatto che il DOM HTML gestito implementa una misura di sicurezza nota come *tra frame sicurezza script*.</span><span class="sxs-lookup"><span data-stu-id="8c19c-115">Access to frames is complicated by the fact that the managed HTML DOM implements a security measure known as *cross-frame scripting security*.</span></span> <span data-ttu-id="8c19c-116">Se un documento contiene un `FRAMESET` con due o più `FRAME` in domini diversi, questi `FRAME` non possono interagire tra loro.</span><span class="sxs-lookup"><span data-stu-id="8c19c-116">If a document contains a `FRAMESET` with two or more `FRAME`s in different domains, these `FRAME`s cannot interact with one another.</span></span> <span data-ttu-id="8c19c-117">In altre parole, un `FRAME` che visualizza contenuto dal sito Web non può accedere alle informazioni di un `FRAME` che ospita un sito di terze parti, ad esempio http://www.adatum.com/.</span><span class="sxs-lookup"><span data-stu-id="8c19c-117">In other words, a `FRAME` that displays content from your Web site cannot access information in a `FRAME` that hosts a third-party site such as http://www.adatum.com/.</span></span> <span data-ttu-id="8c19c-118">Questa misura di sicurezza è implementata a livello della classe <xref:System.Windows.Forms.HtmlWindow>.</span><span class="sxs-lookup"><span data-stu-id="8c19c-118">This security is implemented at the level of the <xref:System.Windows.Forms.HtmlWindow> class.</span></span> <span data-ttu-id="8c19c-119">È possibile ottenere informazioni generali su un `FRAME` che ospita un altro sito Web, ad esempio l'URL, ma non si potrà accedere alla proprietà <xref:System.Windows.Forms.HtmlWindow.Document%2A> o modificare le dimensioni o la posizione del `FRAME` o dell'`IFRAME` di hosting.</span><span class="sxs-lookup"><span data-stu-id="8c19c-119">You can obtain general information about a `FRAME` hosting another Web site, such as its URL, but you will be unable to access its <xref:System.Windows.Forms.HtmlWindow.Document%2A> or change the size or location of its hosting `FRAME` or `IFRAME`.</span></span>  
  
 <span data-ttu-id="8c19c-120">Questa regola si applica anche alle finestre aperte con i metodi <xref:System.Windows.Forms.HtmlWindow.Open%2A> e <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c19c-120">This rule also applies to windows that you open using the <xref:System.Windows.Forms.HtmlWindow.Open%2A> and <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> methods.</span></span> <span data-ttu-id="8c19c-121">Se la finestra aperta è in un dominio diverso da quello della pagina ospitata nel controllo <xref:System.Windows.Forms.WebBrowser>, non sarà possibile spostare la finestra o esaminarne i contenuti.</span><span class="sxs-lookup"><span data-stu-id="8c19c-121">If the window you open is in a different domain from the page hosted in the <xref:System.Windows.Forms.WebBrowser> control, you will not be able to move that window or examine its contents.</span></span> <span data-ttu-id="8c19c-122">Queste restrizioni vengono applicate anche se si usa il controllo <xref:System.Windows.Forms.WebBrowser> per visualizzare un sito Web diverso dal sito Web usato per distribuire l'applicazione basata su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="8c19c-122">These restrictions are also enforced if you use the <xref:System.Windows.Forms.WebBrowser> control to display a Web site that is different from the Web site used to deploy your Windows Forms-based application.</span></span> <span data-ttu-id="8c19c-123">Se si usa la tecnologia di distribuzione [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] per installare l'applicazione dal sito Web A e si usa <xref:System.Windows.Forms.WebBrowser> per visualizzare il sito Web B, non sarà possibile accedere ai dati del sito Web B.</span><span class="sxs-lookup"><span data-stu-id="8c19c-123">If you use [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] deployment technology to install your application from Web site A, and you use the <xref:System.Windows.Forms.WebBrowser> to display Web site B, you will not be able to access Web site B's data.</span></span>  
  
 <span data-ttu-id="8c19c-124">Per ulteriori informazioni sulla creazione di script tra siti, vedere[informazioni sugli script tra Frame e sicurezza](http://msdn.microsoft.com/library/ms533028.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c19c-124">For more information about cross-site scripting, see[About Cross-Frame Scripting and Security](http://msdn.microsoft.com/library/ms533028.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c19c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c19c-125">See Also</span></span>  
 [<span data-ttu-id="8c19c-126">Elemento FRAME &#124; Oggetto frame</span><span class="sxs-lookup"><span data-stu-id="8c19c-126">FRAME Element &#124; frame Object</span></span>](http://msdn.microsoft.com/library/ms535250.aspx)  
 [<span data-ttu-id="8c19c-127">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="8c19c-127">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
