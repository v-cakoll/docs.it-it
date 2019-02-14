---
title: "Procedura: Implementare comunicazioni bidirezionali tra codice DHTML e il codice dell'applicazione Client"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 9cc6cb747ea5ff80770f18c2e884e72883c9a82f
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261037"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="4d64b-102">Procedura: Implementare comunicazioni bidirezionali tra codice DHTML e il codice dell'applicazione Client</span><span class="sxs-lookup"><span data-stu-id="4d64b-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>
<span data-ttu-id="4d64b-103">È possibile usare il controllo <xref:System.Windows.Forms.WebBrowser> per aggiungere codice HTML dinamico (DHTML) dell'applicazione Web esistente alle applicazioni client Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4d64b-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="4d64b-104">Questa procedura è utile quando in fase di sviluppo si è investito molto tempo nella creazione di controlli basati su DHTML e si desidera usufruire di tutte le capacità offerte dall'interfaccia utente di Windows Form senza dover riscrivere il codice esistente.</span><span class="sxs-lookup"><span data-stu-id="4d64b-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>  
  
 <span data-ttu-id="4d64b-105">Il controllo <xref:System.Windows.Forms.WebBrowser> consente di implementare comunicazioni bidirezionali tra il codice dell'applicazione client e il codice di script della pagina Web mediante le proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> e <xref:System.Windows.Forms.WebBrowser.Document%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d64b-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="4d64b-106">È anche possibile configurare il controllo <xref:System.Windows.Forms.WebBrowser> in modo da poter unire senza problemi i controlli Web agli altri controlli del form dell'applicazione, nascondendo la relativa implementazione DHTML.</span><span class="sxs-lookup"><span data-stu-id="4d64b-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="4d64b-107">A questo scopo, è sufficiente formattare la pagina visualizzata in modo che il colore di sfondo e lo stile visivo corrispondano al resto del form e usare le proprietà <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> e <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> per disabilitare le funzionalità standard del browser.</span><span class="sxs-lookup"><span data-stu-id="4d64b-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="4d64b-108">Per incorporare il codice DHTML in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="4d64b-108">To embed DHTML in your Windows Forms application</span></span>  
  
1.  <span data-ttu-id="4d64b-109">Impostare la proprietà <xref:System.Windows.Forms.WebBrowser> del controllo <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> su `false` per impedire a <xref:System.Windows.Forms.WebBrowser> di aprire i file rilasciati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="4d64b-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  <span data-ttu-id="4d64b-110">Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> del controllo su `false` per impedire la visualizzazione del menu di scelta rapida di <xref:System.Windows.Forms.WebBrowser> quando l'utente fa clic con il pulsante destro del mouse sul controllo.</span><span class="sxs-lookup"><span data-stu-id="4d64b-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  <span data-ttu-id="4d64b-111">Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> del controllo su `false` per impedire che il controllo <xref:System.Windows.Forms.WebBrowser> risponda ai tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4d64b-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  <span data-ttu-id="4d64b-112">Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> nel costruttore del form o in un gestore eventi <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="4d64b-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or a <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
     <span data-ttu-id="4d64b-113">Il codice seguente usa la classe del form per l'oggetto script.</span><span class="sxs-lookup"><span data-stu-id="4d64b-113">The following code uses the form class itself for the scripting object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d64b-114">È necessario che Component Object Model (COM) possa accedere all'oggetto script.</span><span class="sxs-lookup"><span data-stu-id="4d64b-114">Component Object Model (COM) must be able to access the scripting object.</span></span> <span data-ttu-id="4d64b-115">Per rendere visibile il form a COM, aggiungere l'attributo <xref:System.Runtime.InteropServices.ComVisibleAttribute> alla classe del form.</span><span class="sxs-lookup"><span data-stu-id="4d64b-115">To make your form visible to COM, add the <xref:System.Runtime.InteropServices.ComVisibleAttribute> attribute to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  <span data-ttu-id="4d64b-116">Implementare proprietà o metodi pubblici nel codice dell'applicazione che verrà usato dal codice di script.</span><span class="sxs-lookup"><span data-stu-id="4d64b-116">Implement public properties or methods in your application code that your script code will use.</span></span>  
  
     <span data-ttu-id="4d64b-117">Se ad esempio si usa la classe del form per l'oggetto script, aggiungere alla classe il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4d64b-117">For example, if you use the form class for the scripting object, add the following code to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  <span data-ttu-id="4d64b-118">Usare l'oggetto `window.external` nel codice di script per accedere alle proprietà e ai metodi pubblici dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="4d64b-118">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>  
  
     <span data-ttu-id="4d64b-119">Il codice HTML riportato di seguito dimostra come chiamare un metodo nell'oggetto script in seguito alla selezione di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="4d64b-119">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="4d64b-120">Copiare questo codice nell'elemento BODY di un documento HTML che è stato caricato mediante il metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del controllo o a cui è stata assegnata la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="4d64b-120">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  <span data-ttu-id="4d64b-121">Implementare funzioni nel codice di script che verrà usato dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d64b-121">Implement functions in your script code that your application code will use.</span></span>  
  
     <span data-ttu-id="4d64b-122">L'elemento SCRIPT HTML riportato di seguito fornisce una funzione di esempio.</span><span class="sxs-lookup"><span data-stu-id="4d64b-122">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="4d64b-123">Copiare questo codice nell'elemento HEAD di un documento HTML che è stato caricato mediante il metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A> del controllo o a cui è stata assegnata la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="4d64b-123">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  <span data-ttu-id="4d64b-124">Usare la proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A> per accedere al codice di script dal codice dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="4d64b-124">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>  
  
     <span data-ttu-id="4d64b-125">Ad esempio, aggiungere il codice seguente al gestore eventi di un pulsante <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="4d64b-125">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. <span data-ttu-id="4d64b-126">Una volta terminato il debug del codice DHTML, impostare la proprietà <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> del controllo su `true` per impedire al controllo <xref:System.Windows.Forms.WebBrowser> di visualizzare messaggi di errore in caso di problemi nel codice di script.</span><span class="sxs-lookup"><span data-stu-id="4d64b-126">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="4d64b-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d64b-127">Example</span></span>  
 <span data-ttu-id="4d64b-128">L'esempio di codice completo riportato di seguito illustra un'applicazione di prova che può essere usata per comprendere meglio questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d64b-128">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="4d64b-129">Anziché essere caricato da un file HTML separato, il codice HTML viene caricato nel controllo <xref:System.Windows.Forms.WebBrowser> mediante la proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d64b-129">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d64b-130">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4d64b-130">Compiling the Code</span></span>  
 <span data-ttu-id="4d64b-131">Per questo codice sono necessari i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d64b-131">This code requires:</span></span>  
  
-   <span data-ttu-id="4d64b-132">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4d64b-132">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4d64b-133">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4d64b-133">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4d64b-134">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="4d64b-134">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d64b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d64b-135">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4d64b-136">Controllo WebBrowser</span><span class="sxs-lookup"><span data-stu-id="4d64b-136">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)
