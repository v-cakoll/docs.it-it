---
title: 'Procedura: convalidare e unire PrintTicket'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="63e70-102">Procedura: convalidare e unire PrintTicket</span><span class="sxs-lookup"><span data-stu-id="63e70-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="63e70-103">Il [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [dello Schema di stampa](http://go.microsoft.com/fwlink/?LinkId=186397) include flessibili ed estensibili <xref:System.Printing.PrintCapabilities> e <xref:System.Printing.PrintTicket> elementi.</span><span class="sxs-lookup"><span data-stu-id="63e70-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="63e70-104">Il primo specifica le funzionalità di un dispositivo di stampa e il secondo specifica come il dispositivo deve usare tali funzionalità rispetto a una particolare sequenza di documenti, singoli documenti o singola pagina.</span><span class="sxs-lookup"><span data-stu-id="63e70-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="63e70-105">Una tipica sequenza di attività per un'applicazione che supporta la stampa sarebbe come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="63e70-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="63e70-106">Determinare le funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="63e70-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="63e70-107">Configurare un <xref:System.Printing.PrintTicket> usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="63e70-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="63e70-108">Convalidare il <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="63e70-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="63e70-109">Questo articolo illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="63e70-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e70-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="63e70-110">Example</span></span>  
 <span data-ttu-id="63e70-111">Nel semplice esempio che segue si intende solo se una stampante può supportare la stampa fronte retro, stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="63e70-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="63e70-112">Come indicato di seguito sono riportati i passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="63e70-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="63e70-113">Ottenere un <xref:System.Printing.PrintCapabilities> dell'oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="63e70-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="63e70-114">Verificare la presenza della funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="63e70-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="63e70-115">Nell'esempio seguente, viene testata il <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà del <xref:System.Printing.PrintCapabilities> la presenza di funzionalità di stampa su entrambi i lati di un foglio di carta con la"pagina" dell'oggetto sul lato lungo del foglio.</span><span class="sxs-lookup"><span data-stu-id="63e70-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="63e70-116">Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, viene usato il `Contains` metodo <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="63e70-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="63e70-117">Questo passaggio non è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="63e70-117">This step is not strictly necessary.</span></span> <span data-ttu-id="63e70-118">Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo usata sotto controllerà ogni richiesta di <xref:System.Printing.PrintTicket> rispetto alle funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="63e70-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="63e70-119">Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante sostituirà una richiesta in alternativa il <xref:System.Printing.PrintTicket> restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="63e70-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="63e70-120">Se la stampante supporta duplex, il codice di esempio crea un <xref:System.Printing.PrintTicket> che richiede la stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="63e70-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="63e70-121">Ma l'applicazione non specifica ogni possibile impostazione della stampante disponibile nel <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="63e70-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="63e70-122">Sarebbe dispendiosa del programmatore e ora del programma.</span><span class="sxs-lookup"><span data-stu-id="63e70-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="63e70-123">Al contrario, il codice imposta solo la richiesta di stampa fronte retro e quindi unisce questo <xref:System.Printing.PrintTicket> con un oggetto esistente, completamente configurata e convalidata <xref:System.Printing.PrintTicket>, in questo caso, predefinito dell'utente <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="63e70-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="63e70-124">Di conseguenza, l'esempio chiama il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo per unire il nuovo minimo, <xref:System.Printing.PrintTicket> predefinito dell'utente <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="63e70-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="63e70-125">Restituisce un <xref:System.Printing.ValidationResult> che include il nuovo <xref:System.Printing.PrintTicket> come una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="63e70-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="63e70-126">L'esempio quindi verifica che il nuovo <xref:System.Printing.PrintTicket> richiede duplex.</span><span class="sxs-lookup"><span data-stu-id="63e70-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="63e70-127">In caso affermativo, quindi l'esempio rende il nuovo print ticket per l'utente predefinito.</span><span class="sxs-lookup"><span data-stu-id="63e70-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="63e70-128">Se il passaggio 2 precedente viene omesso e la stampante non supporta la stampa fronte retro lato lungo, quindi il test avrebbe restituito `false`.</span><span class="sxs-lookup"><span data-stu-id="63e70-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="63e70-129">(Vedere sopra).</span><span class="sxs-lookup"><span data-stu-id="63e70-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="63e70-130">È l'ultimo passaggio significativo eseguire il commit per la modifica di <xref:System.Printing.PrintQueue.UserPrintTicket%2A> proprietà del <xref:System.Printing.PrintQueue> con il <xref:System.Printing.PrintQueue.Commit%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="63e70-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="63e70-131">In modo che è possibile verificare rapidamente in questo esempio, la parte restante viene presentata di seguito.</span><span class="sxs-lookup"><span data-stu-id="63e70-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="63e70-132">Creare un progetto e uno spazio dei nomi e quindi incollare i frammenti di codice in questo articolo il blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63e70-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="63e70-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63e70-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="63e70-134">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="63e70-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="63e70-135">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="63e70-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="63e70-136">Schema di stampa</span><span class="sxs-lookup"><span data-stu-id="63e70-136">Print Schema</span></span>](http://go.microsoft.com/fwlink/?LinkId=186397)
