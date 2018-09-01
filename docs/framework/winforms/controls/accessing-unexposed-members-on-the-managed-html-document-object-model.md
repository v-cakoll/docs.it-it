---
title: Accesso ai membri non esposti del Document Object Model HTML gestito
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 8767ef0fb484d43ffad4888affebb9d6bb74cc3a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384640"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="9ceab-102">Accesso ai membri non esposti del Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="9ceab-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="9ceab-103">Il documento oggetto Model (DOM) HTML gestito contiene una classe denominata <xref:System.Windows.Forms.HtmlElement> che espone le proprietà, metodi ed eventi che hanno in comune di tutti gli elementi HTML.</span><span class="sxs-lookup"><span data-stu-id="9ceab-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="9ceab-104">In alcuni casi, tuttavia, è necessario accedere ai membri che l'interfaccia gestita non espone direttamente.</span><span class="sxs-lookup"><span data-stu-id="9ceab-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="9ceab-105">In questo argomento esamina due modi per l'accesso a membri non esposti, tra cui [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] e le funzioni VBScript definite all'interno di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="9ceab-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="9ceab-106">L'accesso ai membri non esposti tramite interfacce gestite</span><span class="sxs-lookup"><span data-stu-id="9ceab-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="9ceab-107"><xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> forniscono quattro metodi che consentono l'accesso ai membri non esposti.</span><span class="sxs-lookup"><span data-stu-id="9ceab-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="9ceab-108">Nella tabella seguente illustra i tipi e i relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="9ceab-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="9ceab-109">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="9ceab-109">Member Type</span></span>|<span data-ttu-id="9ceab-110">Metodi</span><span class="sxs-lookup"><span data-stu-id="9ceab-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9ceab-111">Proprietà (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="9ceab-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="9ceab-112">Metodi</span><span class="sxs-lookup"><span data-stu-id="9ceab-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="9ceab-113">Eventi (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="9ceab-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="9ceab-114">Eventi (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="9ceab-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="9ceab-115">Eventi (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="9ceab-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="9ceab-116">Quando si utilizzano questi metodi, si presuppone che si dispone di un elemento del tipo sottostante corretto.</span><span class="sxs-lookup"><span data-stu-id="9ceab-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="9ceab-117">Si supponga che si desidera essere in ascolto per il `Submit` eventi di un `FORM` pagina elemento in un elemento HTML, in modo che sia possibile eseguire alcune operazioni di pre-elaborazione nel `FORM`del valori prima che l'utente li invia al server.</span><span class="sxs-lookup"><span data-stu-id="9ceab-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="9ceab-118">In teoria, è possibile controllare il codice HTML, è possibile definire le `FORM` per avere un valore univoco `ID` attributo.</span><span class="sxs-lookup"><span data-stu-id="9ceab-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="9ceab-119">Dopo il caricamento della pagina nel <xref:System.Windows.Forms.WebBrowser> (controllo), è possibile usare il <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> metodo per recuperare le `FORM` in fase di esecuzione tramite `form1` come argomento.</span><span class="sxs-lookup"><span data-stu-id="9ceab-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="9ceab-120">L'accesso a interfacce non gestite</span><span class="sxs-lookup"><span data-stu-id="9ceab-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="9ceab-121">È anche possibile accedere membri non esposti del DOM HTML gestito tramite le interfacce non gestite modello COM (Component Object) esposte da ogni classe DOM.</span><span class="sxs-lookup"><span data-stu-id="9ceab-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="9ceab-122">Ciò è consigliabile se è necessario effettuare diverse chiamate con membri non esposti, o se i membri non esposti restituiscano altre interfacce non gestite non integrate in DOM. HTML gestito</span><span class="sxs-lookup"><span data-stu-id="9ceab-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="9ceab-123">Nella tabella seguente mostra tutte le interfacce non gestite esposte tramite DOM. HTML gestito</span><span class="sxs-lookup"><span data-stu-id="9ceab-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="9ceab-124">Fare clic su ogni collegamento per una spiegazione dell'utilizzo e, ad esempio codice.</span><span class="sxs-lookup"><span data-stu-id="9ceab-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="9ceab-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ceab-125">Type</span></span>|<span data-ttu-id="9ceab-126">Interfaccia non gestita</span><span class="sxs-lookup"><span data-stu-id="9ceab-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="9ceab-127">Il modo più semplice per usare le interfacce COM consiste nell'aggiungere un riferimento alla libreria DOM HTML (Mshtml. dll) non gestita dall'applicazione, anche se ciò non è supportata.</span><span class="sxs-lookup"><span data-stu-id="9ceab-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="9ceab-128">Per altre informazioni, vedere [934368 articolo della Knowledge Base](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="9ceab-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="9ceab-129">L'accesso a funzioni di Script</span><span class="sxs-lookup"><span data-stu-id="9ceab-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="9ceab-130">Una pagina HTML può definire una o più funzioni con un linguaggio di scripting, ad esempio [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript.</span><span class="sxs-lookup"><span data-stu-id="9ceab-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="9ceab-131">Queste funzioni vengono posizionate all'interno di un `SCRIPT` nella pagina e può essere eseguito su richiesta o in risposta a un evento in DOM.</span><span class="sxs-lookup"><span data-stu-id="9ceab-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="9ceab-132">È possibile chiamare qualsiasi funzione di script è definita in una pagina HTML utilizzando la <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="9ceab-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="9ceab-133">Se il metodo di script restituisce un elemento HTML, è possibile usare un cast per convertire il risultato in un <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="9ceab-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="9ceab-134">Per dettagli ed esempio di codice, vedere <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ceab-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ceab-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ceab-135">See Also</span></span>  
 [<span data-ttu-id="9ceab-136">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="9ceab-136">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
