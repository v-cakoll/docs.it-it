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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988394"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="dc9e8-102">Accesso ai membri non esposti del Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="dc9e8-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="dc9e8-103">Il codice HTML Document Object Model (Dom) gestito contiene una classe <xref:System.Windows.Forms.HtmlElement> denominata che espone le proprietà, i metodi e gli eventi di tutti gli elementi HTML in comune.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="dc9e8-104">In alcuni casi, tuttavia, sarà necessario accedere ai membri non esposti direttamente dall'interfaccia gestita.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="dc9e8-105">In questo argomento vengono esaminati due modi per accedere ai membri non esposti, incluse le funzioni JScript e VBScript definite all'interno di una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="dc9e8-106">Accesso ai membri non esposti tramite interfacce gestite</span><span class="sxs-lookup"><span data-stu-id="dc9e8-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="dc9e8-107"><xref:System.Windows.Forms.HtmlDocument>e <xref:System.Windows.Forms.HtmlElement> forniscono quattro metodi che consentono l'accesso ai membri non esposti.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="dc9e8-108">La tabella seguente illustra i tipi e i metodi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="dc9e8-109">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="dc9e8-109">Member Type</span></span>|<span data-ttu-id="dc9e8-110">Metodo/i</span><span class="sxs-lookup"><span data-stu-id="dc9e8-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="dc9e8-111">Proprietà (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="dc9e8-112">Metodi</span><span class="sxs-lookup"><span data-stu-id="dc9e8-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="dc9e8-113">Eventi (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="dc9e8-114">Eventi (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="dc9e8-115">Eventi (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="dc9e8-116">Quando si usano questi metodi, si presuppone che si disponga di un elemento del tipo sottostante corretto.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="dc9e8-117">Si supponga di voler ascoltare l' `Submit` evento di un `FORM` elemento in una pagina HTML, in modo da poter eseguire alcune operazioni di `FORM`pre-elaborazione sui valori di prima che l'utente li invii al server.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="dc9e8-118">Idealmente, se si ha il controllo sul codice HTML, è necessario definire `FORM` per avere un attributo `ID` univoco.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```html  
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
  
 <span data-ttu-id="dc9e8-119">Una volta caricata questa pagina nel <xref:System.Windows.Forms.WebBrowser> controllo, è possibile utilizzare il <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> metodo per recuperare `FORM` in fase di esecuzione utilizzando `form1` come argomento.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="dc9e8-120">Accesso a interfacce non gestite</span><span class="sxs-lookup"><span data-stu-id="dc9e8-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="dc9e8-121">È anche possibile accedere ai membri non esposti sul DOM HTML gestito usando le interfacce di Component Object Model non gestite (COM) esposte da ogni classe DOM.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="dc9e8-122">Questa operazione è consigliata se è necessario effettuare diverse chiamate a membri non esposti o se i membri non esposti restituiscono altre interfacce non gestite non sottoposte a incapsulamento dal DOM HTML gestito.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="dc9e8-123">La tabella seguente mostra tutte le interfacce non gestite esposte tramite il DOM HTML gestito.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="dc9e8-124">Fare clic su ogni collegamento per una spiegazione dell'utilizzo e per il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="dc9e8-125">Type</span><span class="sxs-lookup"><span data-stu-id="dc9e8-125">Type</span></span>|<span data-ttu-id="dc9e8-126">Interfaccia non gestita</span><span class="sxs-lookup"><span data-stu-id="dc9e8-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="dc9e8-127">Il modo più semplice per usare le interfacce COM consiste nell'aggiungere un riferimento alla libreria DOM HTML non gestita (MSHTML. dll) dall'applicazione, anche se questa operazione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="dc9e8-128">Per ulteriori informazioni, vedere l' [articolo della Knowledge Base 934368](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="dc9e8-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="dc9e8-129">Accesso alle funzioni di script</span><span class="sxs-lookup"><span data-stu-id="dc9e8-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="dc9e8-130">Una pagina HTML può definire una o più funzioni utilizzando un linguaggio di scripting, ad esempio JScript o VBScript.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="dc9e8-131">Queste funzioni vengono posizionate all'interno `SCRIPT` di una pagina della pagina e possono essere eseguite su richiesta o in risposta a un evento nel DOM.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="dc9e8-132">È possibile chiamare qualsiasi funzione script definita in una pagina HTML usando il <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="dc9e8-133">Se il metodo di script restituisce un elemento HTML, è possibile usare un cast per convertire il risultato restituito in <xref:System.Windows.Forms.HtmlElement>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="dc9e8-134">Per informazioni dettagliate ed esempi di codice <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>, vedere.</span><span class="sxs-lookup"><span data-stu-id="dc9e8-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9e8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc9e8-135">See also</span></span>

- [<span data-ttu-id="dc9e8-136">Utilizzare il Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="dc9e8-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
