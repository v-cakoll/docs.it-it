---
title: Errori in fase di progettazione in Progettazione Windows Form
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015964"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="d82c0-102">Errori della fase di progettazione nel Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="d82c0-102">Design-time errors in the Windows Forms Designer</span></span>

<span data-ttu-id="d82c0-103">Questo argomento illustra il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Visual Studio quando non è possibile caricare il Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d82c0-103">This topic explains the meaning and use of the design-time error list that appears in Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="d82c0-104">Se viene visualizzato questo elenco di errori non si deve interpretarlo come un bug della progettazione, ma come ausilio per la correzione degli errori nel codice.</span><span class="sxs-lookup"><span data-stu-id="d82c0-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>

<span data-ttu-id="d82c0-105">Una conoscenza di base di questo elenco di errori consentirà di eseguire il debug delle applicazioni fornendo informazioni dettagliate sugli errori e suggerendo le possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="d82c0-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>

## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="d82c0-106">Interfaccia elenco errori in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d82c0-106">The design-time error list interface</span></span>

<span data-ttu-id="d82c0-107">Se non è possibile caricare il Progettazione Windows Form, nella finestra di progettazione viene visualizzato un elenco errori.</span><span class="sxs-lookup"><span data-stu-id="d82c0-107">If the Windows Forms Designer fails to load, an error list appears in the designer.</span></span> <span data-ttu-id="d82c0-108">Gli errori sono raggruppati in categorie.</span><span class="sxs-lookup"><span data-stu-id="d82c0-108">The errors are grouped into categories.</span></span> <span data-ttu-id="d82c0-109">Ad esempio, se si dispone di quattro istanze di variabili non dichiarate, queste verranno raggruppate nella stessa categoria di errori.</span><span class="sxs-lookup"><span data-stu-id="d82c0-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="d82c0-110">Ogni categoria di errori include una breve descrizione che riepiloga l'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-110">Each error category includes a brief description that summarizes the error.</span></span>

<span data-ttu-id="d82c0-111">È possibile espandere o comprimere una categoria di errore facendo clic sull'intestazione della categoria di errori oppure facendo clic sulla freccia di espansione di espansione/compressione.</span><span class="sxs-lookup"><span data-stu-id="d82c0-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="d82c0-112">Quando si espande una categoria di errori, vengono visualizzate le seguenti informazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="d82c0-112">When you expand an error category, the following additional help is displayed:</span></span>

- <span data-ttu-id="d82c0-113">Istanze dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-113">Instances of this error.</span></span>

- <span data-ttu-id="d82c0-114">Informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-114">Help with this error.</span></span>

- <span data-ttu-id="d82c0-115">Post dei forum sull'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-115">Forum posts about this error.</span></span>

### <a name="instances-of-this-error"></a><span data-ttu-id="d82c0-116">Istanze dell'errore</span><span class="sxs-lookup"><span data-stu-id="d82c0-116">Instances of this error</span></span>

<span data-ttu-id="d82c0-117">Nelle informazioni sono elencate tutte le istanze dell'errore nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d82c0-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="d82c0-118">Molti errori evidenziano un percorso esatto nel formato seguente: *[nome progetto]* *[nome modulo]* riga: *[numero riga]* colonna: *[numero colonna]* .</span><span class="sxs-lookup"><span data-stu-id="d82c0-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="d82c0-119">Il collegamento **Vai al codice** consente di visualizzare il percorso nel codice in cui si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>

<span data-ttu-id="d82c0-120">Se uno stack di chiamate è associato all'errore, è possibile selezionare il collegamento **Mostra stack di chiamate** che espande ulteriormente l'errore per visualizzare lo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="d82c0-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="d82c0-121">L'analisi dello stack può fornire informazioni utili sul debug.</span><span class="sxs-lookup"><span data-stu-id="d82c0-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="d82c0-122">Ad esempio, è possibile rilevare le funzioni chiamate prima del verificarsi dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="d82c0-123">Lo stack di chiamate è selezionabile, in modo da poterlo copiare e salvare.</span><span class="sxs-lookup"><span data-stu-id="d82c0-123">The call stack is selectable so that you can copy and save it.</span></span>

> [!NOTE]
> <span data-ttu-id="d82c0-124">In Visual Basic l'elenco degli errori in fase di progettazione non mostra più di un errore, ma è possibile visualizzare più istanze dello stesso errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="d82c0-125">In Visual C++ gli errori non sono dotati di collegamenti per andare al codice o al numero di riga.</span><span class="sxs-lookup"><span data-stu-id="d82c0-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>

### <a name="forum-posts-about-this-error"></a><span data-ttu-id="d82c0-126">Post dei forum sull'errore</span><span class="sxs-lookup"><span data-stu-id="d82c0-126">Forum posts about this error</span></span>

<span data-ttu-id="d82c0-127">La Guida aggiuntiva include un collegamento ai post del forum relativi all'errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-127">The additional help includes a link to forum posts related to the error.</span></span> <span data-ttu-id="d82c0-128">La ricerca viene effettuata nei forum sulla base della stringa del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d82c0-128">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="d82c0-129">È anche possibile provare a eseguire ricerche nei forum seguenti:</span><span class="sxs-lookup"><span data-stu-id="d82c0-129">You can also try searching on the following forums:</span></span>

- [<span data-ttu-id="d82c0-130">Forum Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="d82c0-130">Windows Forms Designer forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [<span data-ttu-id="d82c0-131">Forum Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d82c0-131">Windows Forms forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a><span data-ttu-id="d82c0-132">Ignora e continua</span><span class="sxs-lookup"><span data-stu-id="d82c0-132">Ignore and continue</span></span>

<span data-ttu-id="d82c0-133">È possibile ignorare la condizione di errore e continuare a caricare la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d82c0-133">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="d82c0-134">La scelta di questa azione può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="d82c0-134">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="d82c0-135">Ad esempio, nell'area di progettazione potrebbero non venire visualizzati alcuni controlli.</span><span class="sxs-lookup"><span data-stu-id="d82c0-135">For example, controls may not appear on the design surface.</span></span>

## <a name="see-also"></a><span data-ttu-id="d82c0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82c0-136">See also</span></span>

- <span data-ttu-id="d82c0-137">[Risoluzione dei problemi di sviluppo in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d82c0-137">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="d82c0-138">Risoluzione dei problemi relativi alla modifica di controlli e componenti</span><span class="sxs-lookup"><span data-stu-id="d82c0-138">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="d82c0-139">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d82c0-139">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="d82c0-140">[Messaggi di errore di Progettazione Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d82c0-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>
