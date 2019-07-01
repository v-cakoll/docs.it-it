---
title: 'Procedura: Accedere al Document Object Model HTML gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 2a195dc6583d5a0a72bd08b66f8933f4002e879a
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487279"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="01cbf-102">Procedura: Accedere al Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="01cbf-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="01cbf-103">È possibile accedere a Document Object Model (DOM) HTML gestito da due tipi di applicazione:</span><span class="sxs-lookup"><span data-stu-id="01cbf-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
- <span data-ttu-id="01cbf-104">Un'applicazione Windows Form (con estensione EXE) che ha ospitato il controllo gestito <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="01cbf-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="01cbf-105">Queste due tecnologie sono complementari: il controllo <xref:System.Windows.Forms.WebBrowser> visualizza la pagina all'utente e DOM HTML rappresenta la struttura logica del documento.</span><span class="sxs-lookup"><span data-stu-id="01cbf-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
- <span data-ttu-id="01cbf-106">Una classe <xref:System.Windows.Forms.UserControl> Windows Form ospitata in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="01cbf-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="01cbf-107">Si può accedere a DOM HTML che rappresenta la pagina in cui è ospitata la classe <xref:System.Windows.Forms.UserControl> per modificare la struttura del documento o aprire finestre di dialogo modali, tra le molte altre possibilità.</span><span class="sxs-lookup"><span data-stu-id="01cbf-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="01cbf-108">Per accedere a DOM da un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01cbf-108">To access DOM from a Windows Forms application</span></span>  
  
1. <span data-ttu-id="01cbf-109">Ospitare un controllo <xref:System.Windows.Forms.WebBrowser> nell'applicazione Windows Form e verificare la presenza dell'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.</span><span class="sxs-lookup"><span data-stu-id="01cbf-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="01cbf-110">Per altre informazioni su come ospitare i controlli e verificare gli eventi, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="01cbf-110">For details on hosting controls and monitoring for events, see [Events](../../../standard/events/index.md).</span></span>  
  
2. <span data-ttu-id="01cbf-111">Recuperare la classe <xref:System.Windows.Forms.HtmlDocument> per la pagina corrente accedendo alla proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> del controllo <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="01cbf-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="01cbf-112">Per accedere a DOM da una classe UserControl ospitata in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="01cbf-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1. <span data-ttu-id="01cbf-113">Creare una classe personalizzata derivata dalla classe <xref:System.Windows.Forms.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="01cbf-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="01cbf-114">Per altre informazioni, vedere [Procedura: Modificare controlli compositi](how-to-author-composite-controls.md).</span><span class="sxs-lookup"><span data-stu-id="01cbf-114">For more information, see [How to: Author Composite Controls](how-to-author-composite-controls.md).</span></span>  
  
2. <span data-ttu-id="01cbf-115">Inserire il codice seguente nel gestore eventi Load per la classe <xref:System.Windows.Forms.UserControl> personalizzata:</span><span class="sxs-lookup"><span data-stu-id="01cbf-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="01cbf-116">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="01cbf-116">Robust Programming</span></span>  
  
1. <span data-ttu-id="01cbf-117">Quando si usa DOM tramite il controllo <xref:System.Windows.Forms.WebBrowser>, è consigliabile attendere sempre finché si verifica l'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> prima di provare ad accedere alla proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> del controllo <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="01cbf-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="01cbf-118">L'evento <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> viene generato dopo il caricamento dell'intero documento. Se si usa DOM prima che l'evento sia generato, si rischia di causare un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="01cbf-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="01cbf-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="01cbf-119">.NET Framework Security</span></span>  
  
1. <span data-ttu-id="01cbf-120">L'applicazione o la classe <xref:System.Windows.Forms.UserControl> richiederà l'attendibilità totale per accedere a DOM HTML gestito.</span><span class="sxs-lookup"><span data-stu-id="01cbf-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="01cbf-121">Se si distribuisce un'applicazione Windows Forms con ClickOnce, è possibile richiedere con attendibilità totale utilizzando l'elevazione delle autorizzazioni o la distribuzione di applicazioni attendibili. visualizzare [protezione di applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="01cbf-121">If you are deploying a Windows Forms application using ClickOnce, you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cbf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01cbf-122">See also</span></span>

- [<span data-ttu-id="01cbf-123">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="01cbf-123">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
