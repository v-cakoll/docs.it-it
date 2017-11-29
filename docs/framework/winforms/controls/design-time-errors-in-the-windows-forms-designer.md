---
title: Errori in fase di progettazione in Progettazione Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 819b624e2abac09aea804311d661f78e2a1f5a7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="faddb-102">Errori in fase di progettazione in Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="faddb-102">Design-Time Errors in the Windows Forms Designer</span></span>
<span data-ttu-id="faddb-103">In questo argomento viene illustrato il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Microsoft Visual Studio quando il caricamento di Progettazione Windows Form non riesce.</span><span class="sxs-lookup"><span data-stu-id="faddb-103">This topic explains the meaning and use of the design-time error list that appears in Microsoft Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="faddb-104">Se viene visualizzato questo elenco di errori non si deve interpretarlo come un bug della progettazione, ma come ausilio per la correzione degli errori nel codice.</span><span class="sxs-lookup"><span data-stu-id="faddb-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>  
  
 <span data-ttu-id="faddb-105">Una conoscenza di base di questo elenco di errori consentirà di eseguire il debug delle applicazioni fornendo informazioni dettagliate sugli errori e suggerendo le possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="faddb-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>  
  
## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="faddb-106">L'interfaccia dell'elenco di errori in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="faddb-106">The Design-Time Error List Interface</span></span>  
 <span data-ttu-id="faddb-107">Se Progettazione Windows Form non viene caricato, verrà visualizzato un elenco di errori nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="faddb-107">If the Windows Forms Designer fails to load, an error list will appear in the designer.</span></span> <span data-ttu-id="faddb-108">Gli errori sono raggruppati in categorie.</span><span class="sxs-lookup"><span data-stu-id="faddb-108">The errors are grouped into categories.</span></span> <span data-ttu-id="faddb-109">Ad esempio, se si dispone di quattro istanze di variabili non dichiarate, queste verranno raggruppate nella stessa categoria di errori.</span><span class="sxs-lookup"><span data-stu-id="faddb-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="faddb-110">Ogni categoria di errori include una breve descrizione che riepiloga l'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-110">Each error category includes a brief description that summarizes the error.</span></span>  
  
 <span data-ttu-id="faddb-111">È possibile espandere o comprimere una categoria di errore facendo clic sull'intestazione della categoria di errori oppure facendo clic sulla freccia di espansione di espansione/compressione.</span><span class="sxs-lookup"><span data-stu-id="faddb-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="faddb-112">Quando si espande una categoria di errori, vengono visualizzate le seguenti informazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="faddb-112">When you expand an error category, the following additional help is displayed:</span></span>  
  
-   <span data-ttu-id="faddb-113">Istanze dell'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-113">Instances of this error.</span></span>  
  
-   <span data-ttu-id="faddb-114">Informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-114">Help with this error.</span></span>  
  
-   <span data-ttu-id="faddb-115">Post dei forum sull'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-115">Forum posts about this error.</span></span>  
  
### <a name="instances-of-this-error"></a><span data-ttu-id="faddb-116">Istanze dell'errore</span><span class="sxs-lookup"><span data-stu-id="faddb-116">Instances of This Error</span></span>  
 <span data-ttu-id="faddb-117">Nelle informazioni sono elencate tutte le istanze dell'errore nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="faddb-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="faddb-118">Molti errori evidenziano un percorso esatto nel formato seguente: *[nome progetto]* *[nome modulo]* riga:*[numero riga]* colonna:*[numero colonna]*.</span><span class="sxs-lookup"><span data-stu-id="faddb-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="faddb-119">Il collegamento **Vai al codice** consente di visualizzare il percorso nel codice in cui si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>  
  
 <span data-ttu-id="faddb-120">Se uno stack di chiamate è associato all'errore, è possibile selezionare il collegamento **Mostra stack di chiamate** che espande ulteriormente l'errore per visualizzare lo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="faddb-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="faddb-121">L'analisi dello stack può fornire informazioni utili sul debug.</span><span class="sxs-lookup"><span data-stu-id="faddb-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="faddb-122">Ad esempio, è possibile rilevare le funzioni chiamate prima del verificarsi dell'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="faddb-123">Lo stack di chiamate è selezionabile, in modo da poterlo copiare e salvare.</span><span class="sxs-lookup"><span data-stu-id="faddb-123">The call stack is selectable so that you can copy and save it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faddb-124">In Visual Basic l'elenco degli errori in fase di progettazione non mostra più di un errore, ma è possibile visualizzare più istanze dello stesso errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="faddb-125">In Visual C++ gli errori non sono dotati di collegamenti per andare al codice o al numero di riga.</span><span class="sxs-lookup"><span data-stu-id="faddb-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>  
  
### <a name="help-with-this-error"></a><span data-ttu-id="faddb-126">Informazioni sull'errore</span><span class="sxs-lookup"><span data-stu-id="faddb-126">Help with This Error</span></span>  
 <span data-ttu-id="faddb-127">Se l'errore contiene un collegamento a un argomento della Guida MSDN associato, nelle informazioni aggiuntive verrà incluso un collegamento all'argomento della Guida.</span><span class="sxs-lookup"><span data-stu-id="faddb-127">If the error contains a link to an associated MSDN help topic, the additional help will include a link to the help topic.</span></span> <span data-ttu-id="faddb-128">Quando si fa clic sul collegamento, l'argomento della Guida associato viene visualizzato in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="faddb-128">When you click the link, the associated help topic appears in Visual Studio.</span></span>  
  
### <a name="forum-posts-about-this-error"></a><span data-ttu-id="faddb-129">Post dei forum sull'errore</span><span class="sxs-lookup"><span data-stu-id="faddb-129">Forum posts about this error</span></span>  
 <span data-ttu-id="faddb-130">Nelle informazioni aggiuntive verrà incluso un collegamento ai post del forum MSDN relativi all'errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-130">The additional help will include a link to MSDN forum posts related to the error.</span></span> <span data-ttu-id="faddb-131">La ricerca viene effettuata nei forum sulla base della stringa del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="faddb-131">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="faddb-132">È anche possibile provare a effettuare una ricerca nei seguenti forum:</span><span class="sxs-lookup"><span data-stu-id="faddb-132">You can also try searching the following forums:</span></span>  
  
-   [<span data-ttu-id="faddb-133">Forum di Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="faddb-133">Windows Forms Designer Forum</span></span>](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [<span data-ttu-id="faddb-134">Forum di Windows Form</span><span class="sxs-lookup"><span data-stu-id="faddb-134">Windows Forms Forums</span></span>](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a><span data-ttu-id="faddb-135">Ignora e continua</span><span class="sxs-lookup"><span data-stu-id="faddb-135">Ignore and Continue</span></span>  
 <span data-ttu-id="faddb-136">È possibile ignorare la condizione di errore e continuare a caricare la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="faddb-136">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="faddb-137">La scelta di questa azione può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="faddb-137">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="faddb-138">Ad esempio, nell'area di progettazione potrebbero non venire visualizzati alcuni controlli.</span><span class="sxs-lookup"><span data-stu-id="faddb-138">For example, controls may not appear on the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faddb-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faddb-139">See Also</span></span>  
 [<span data-ttu-id="faddb-140">Risoluzione dei problemi di sviluppo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="faddb-140">Troubleshooting Design-Time Development</span></span>](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="faddb-141">Risoluzione dei problemi relativi alla modifica di controlli e componenti</span><span class="sxs-lookup"><span data-stu-id="faddb-141">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 [<span data-ttu-id="faddb-142">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="faddb-142">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="faddb-143">Messaggi di errore di Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="faddb-143">Windows Forms Designer Error Messages</span></span>](http://msdn.microsoft.com/en-us/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)
