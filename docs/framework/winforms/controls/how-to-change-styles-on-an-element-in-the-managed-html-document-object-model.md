---
title: 'Procedura: modificare gli stili di un elemento nel Document Object Model HTML gestito'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e833a15e33d0baf80f0078b26758137e7908a8fd
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="cf5a8-102">Procedura: modificare gli stili di un elemento nel Document Object Model HTML gestito</span><span class="sxs-lookup"><span data-stu-id="cf5a8-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="cf5a8-103">È possibile utilizzare gli stili HTML per controllare l'aspetto di un documento e i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="cf5a8-104"><xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> supportano <xref:System.Windows.Forms.HtmlElement.Style%2A> le proprietà che accettano stringhe di formato seguente:</span><span class="sxs-lookup"><span data-stu-id="cf5a8-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>  
  
 `name1:value1;...;nameN:valueN;`  
  
 <span data-ttu-id="cf5a8-105">Ecco un `DIV` con una stringa che imposta il tipo di carattere Arial e tutto il testo da visualizzare in grassetto:</span><span class="sxs-lookup"><span data-stu-id="cf5a8-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 <span data-ttu-id="cf5a8-106">Il problema con la modifica degli stili mediante il <xref:System.Windows.Forms.HtmlElement.Style%2A> proprietà è difficoltà di aggiungere e rimuovere singole impostazioni di stile dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="cf5a8-107">Ad esempio, diventa una procedura complessa per poter eseguire il rendering di testo precedente in corsivo ogni volta che l'utente posiziona il cursore sul `DIV`e intraprendere corsivo quando il cursore viene spostato il `DIV`.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="cf5a8-108">Tempo diventerebbe un problema se si desidera modificare un numero elevato di stili in questo modo.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>  
  
 <span data-ttu-id="cf5a8-109">La procedura seguente contiene codice che consente di gestire facilmente stili in documenti HTML e gli elementi.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="cf5a8-110">La procedura è richiesta la conoscenza di come eseguire attività di base in Windows Form, ad esempio la creazione di un nuovo progetto e aggiungendo un controllo a un form.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="cf5a8-111">Per elaborare le modifiche di stile in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="cf5a8-111">To process style changes in a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="cf5a8-112">Creare un nuovo progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-112">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="cf5a8-113">Creare un nuovo file di classe di estensione appropriato per il linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>  
  
3.  <span data-ttu-id="cf5a8-114">Copia il `StyleGenerator` codice nella sezione esempio di questo argomento della classe nel file di classe e salvare il codice.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>  
  
4.  <span data-ttu-id="cf5a8-115">Salvare il codice HTML seguente in un file denominato htm.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-115">Save the following HTML to a file named Test.htm.</span></span>  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  <span data-ttu-id="cf5a8-116">Aggiungere un <xref:System.Windows.Forms.WebBrowser> controllo denominato `webBrowser1` al form principale del progetto.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>  
  
6.  <span data-ttu-id="cf5a8-117">Aggiungere il codice seguente al file di codice del progetto.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-117">Add the following code to your project's code file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cf5a8-118">Verificare che il `webBrowser1_DocumentCompleted` gestore dell'evento è configurato come un listener per il <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-118">Ensure that the `webBrowser1_DocumentCompleted` event hander is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="cf5a8-119">In Visual Studio, fare doppio clic sul <xref:System.Windows.Forms.WebBrowser> controllo; in un editor di testo, configurare il listener a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  <span data-ttu-id="cf5a8-120">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-120">Run the project.</span></span> <span data-ttu-id="cf5a8-121">Spostare il cursore sulla prima `DIV` e osservare gli effetti del codice.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf5a8-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf5a8-122">Example</span></span>  
 <span data-ttu-id="cf5a8-123">Esempio di codice seguente mostra il codice completo per il `StyleGenerator` (classe), che analizza un valore di stile esistente, supporta l'aggiunta, modifica e rimozione di stili e restituisce un nuovo valore di stile con le modifiche richieste.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cf5a8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf5a8-124">See Also</span></span>  
 <xref:System.Windows.Forms.HtmlElement>
