---
title: 'Procedura: Visualizzare la Guida in un''applicazione Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f407f1c17c67ec99f4499b89c49932a4ba6d32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="79875-102">Procedura: Visualizzare la Guida in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="79875-102">How to: Provide Help in a Windows Application</span></span>
<span data-ttu-id="79875-103">È possibile utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per collegare gli argomenti della Guida all'interno di un file della Guida in controlli specifici in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="79875-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="79875-104">Il file della Guida può essere in formato HTML o HTMLHelp 1. x o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="79875-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79875-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="79875-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="79875-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="79875-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="79875-107">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="79875-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-provide-help"></a><span data-ttu-id="79875-108">Per visualizzare la Guida</span><span class="sxs-lookup"><span data-stu-id="79875-108">To provide Help</span></span>  
  
1.  <span data-ttu-id="79875-109">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.HelpProvider> componente al form.</span><span class="sxs-lookup"><span data-stu-id="79875-109">From the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>  
  
     <span data-ttu-id="79875-110">Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="79875-110">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="79875-111">Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà al file della Guida con estensione chm, col o htm.</span><span class="sxs-lookup"><span data-stu-id="79875-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>  
  
3.  <span data-ttu-id="79875-112">Selezionare un altro controllo, si dispone sul form e nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79875-112">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>  
  
     <span data-ttu-id="79875-113">Questa è la stringa passata attraverso il <xref:System.Windows.Forms.HelpProvider> componente al file della Guida per richiamare l'argomento della Guida appropriato.</span><span class="sxs-lookup"><span data-stu-id="79875-113">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>  
  
4.  <span data-ttu-id="79875-114">Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> un valore di proprietà il <xref:System.Windows.Forms.HelpNavigator> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="79875-114">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>  
  
     <span data-ttu-id="79875-115">Questa impostazione determina il modo in cui la proprietà **HelpKeyword** viene passata al sistema della Guida.</span><span class="sxs-lookup"><span data-stu-id="79875-115">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="79875-116">La tabella seguente elenca le impostazioni possibili e le relative descrizioni.</span><span class="sxs-lookup"><span data-stu-id="79875-116">The following table shows the possible settings and their descriptions.</span></span>  
  
    |<span data-ttu-id="79875-117">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="79875-117">Member Name</span></span>|<span data-ttu-id="79875-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79875-118">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="79875-119">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="79875-119">AssociateIndex</span></span>|<span data-ttu-id="79875-120">Specifica che l'indice di un argomento specificato viene eseguito nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="79875-120">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|  
    |<span data-ttu-id="79875-121">Find</span><span class="sxs-lookup"><span data-stu-id="79875-121">Find</span></span>|<span data-ttu-id="79875-122">Specifica che viene visualizzata la pagina di ricerca di un URL specificato.</span><span class="sxs-lookup"><span data-stu-id="79875-122">Specifies that the search page of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="79875-123">Indice</span><span class="sxs-lookup"><span data-stu-id="79875-123">Index</span></span>|<span data-ttu-id="79875-124">Specifica che viene visualizzato l'indice di un URL specificato.</span><span class="sxs-lookup"><span data-stu-id="79875-124">Specifies that the index of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="79875-125">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="79875-125">KeywordIndex</span></span>|<span data-ttu-id="79875-126">Specifica una parola chiave da cercare e l'azione da eseguire nell'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="79875-126">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|  
    |<span data-ttu-id="79875-127">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="79875-127">TableOfContents</span></span>|<span data-ttu-id="79875-128">Specifica che viene visualizzato il sommario del file della Guida HTML 1.0.</span><span class="sxs-lookup"><span data-stu-id="79875-128">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|  
    |<span data-ttu-id="79875-129">Argomento</span><span class="sxs-lookup"><span data-stu-id="79875-129">Topic</span></span>|<span data-ttu-id="79875-130">Specifica che viene visualizzato l'argomento a cui fa riferimento l'URL specificato.</span><span class="sxs-lookup"><span data-stu-id="79875-130">Specifies that the topic referenced by the specified URL is displayed.</span></span>|  
  
 <span data-ttu-id="79875-131">In fase di esecuzione, premere F1 quando il controllo, per cui impostare il **HelpKeyword** e **HelpNavigator** proprietà, ovvero ha lo stato attivo verrà aperto il file della Guida che è associata <xref:System.Windows.Forms.HelpProvider> componente.</span><span class="sxs-lookup"><span data-stu-id="79875-131">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>  
  
 <span data-ttu-id="79875-132">Attualmente, la proprietà **HelpNamespace** supporta i file della Guida nei tre formati seguenti: HTMLHelp 1.x, HTMLHelp 2.0 e HTML.</span><span class="sxs-lookup"><span data-stu-id="79875-132">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="79875-133">Pertanto, è possibile impostare la proprietà **HelpNamespace** su un indirizzo http://, ad esempio una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="79875-133">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="79875-134">In tal caso, nel browser predefinito verrà visualizzata la pagina Web con la stringa specificata nella proprietà **HelpKeyword** usata come ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="79875-134">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="79875-135">L'ancoraggio viene usato per passare direttamente a una parte specifica di una pagina HTML.</span><span class="sxs-lookup"><span data-stu-id="79875-135">The anchor is used to jump to a specific part of an HTML page.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79875-136">Assicurarsi di verificare tutte le informazioni inviate da un client prima di usarle nell'applicazione,</span><span class="sxs-lookup"><span data-stu-id="79875-136">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="79875-137">dal momento che utenti malintenzionati potrebbero tentare di inviare script eseguibili, istruzioni SQL o altro codice.</span><span class="sxs-lookup"><span data-stu-id="79875-137">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="79875-138">Prima di visualizzare l'input di un utente, archiviarlo in un database o usarlo, assicurarsi che non contenga informazioni potenzialmente pericolose.</span><span class="sxs-lookup"><span data-stu-id="79875-138">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="79875-139">Un modo per effettuare questo controllo consiste nell'usare un'espressione regolare per cercare parole chiave come "SCRIPT" quando si riceve input da un utente.</span><span class="sxs-lookup"><span data-stu-id="79875-139">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>  
  
 <span data-ttu-id="79875-140">È inoltre possibile utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per visualizzare la Guida rapida, anche se è stato configurato per visualizzare i file della Guida per i controlli in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="79875-140">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="79875-141">Per altre informazioni, vedere [Procedura: Visualizzare la Guida rapida](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="79875-141">For more information, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79875-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79875-142">See Also</span></span>  
 [<span data-ttu-id="79875-143">Procedura: Visualizzare la Guida rapida</span><span class="sxs-lookup"><span data-stu-id="79875-143">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [<span data-ttu-id="79875-144">Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi</span><span class="sxs-lookup"><span data-stu-id="79875-144">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="79875-145">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="79875-145">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="79875-146">Windows Form</span><span class="sxs-lookup"><span data-stu-id="79875-146">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
