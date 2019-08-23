---
title: 'Procedura: Convalidare e unire PrintTicket'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 9e5242c07179501e6b39840a36f8dd6364d65b84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918353"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="20cc1-102">Procedura: Convalidare e unire PrintTicket</span><span class="sxs-lookup"><span data-stu-id="20cc1-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="20cc1-103">Lo [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [schema di stampa](https://go.microsoft.com/fwlink/?LinkId=186397) include gli elementi e <xref:System.Printing.PrintCapabilities> <xref:System.Printing.PrintTicket> flessibili ed estendibili.</span><span class="sxs-lookup"><span data-stu-id="20cc1-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="20cc1-104">Il primo rilevare le funzionalità di un dispositivo di stampa e il secondo specifica il modo in cui il dispositivo deve usare tali funzionalità rispetto a una particolare sequenza di documenti, documento singolo o singola pagina.</span><span class="sxs-lookup"><span data-stu-id="20cc1-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="20cc1-105">Di seguito è riportata una sequenza di attività tipica per un'applicazione che supporta la stampa.</span><span class="sxs-lookup"><span data-stu-id="20cc1-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="20cc1-106">Determinare le funzionalità di una stampante.</span><span class="sxs-lookup"><span data-stu-id="20cc1-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="20cc1-107"><xref:System.Printing.PrintTicket> Configurare per usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="20cc1-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="20cc1-108">Convalidare l'oggetto <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="20cc1-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="20cc1-109">Questo articolo illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="20cc1-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20cc1-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="20cc1-110">Example</span></span>  
 <span data-ttu-id="20cc1-111">Nell'esempio semplice riportato di seguito, si è interessati solo a se una stampante può supportare il duplexing, ovvero la stampa su due lati.</span><span class="sxs-lookup"><span data-stu-id="20cc1-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="20cc1-112">I passaggi principali sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="20cc1-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="20cc1-113">Ottenere un <xref:System.Printing.PrintCapabilities> oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="20cc1-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="20cc1-114">Verificare la presenza delle funzionalità desiderate.</span><span class="sxs-lookup"><span data-stu-id="20cc1-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="20cc1-115">Nell'esempio seguente viene testata la <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà <xref:System.Printing.PrintCapabilities> dell'oggetto per la presenza della funzionalità di stampa su entrambi i lati di un foglio di carta con la "trasformazione della pagina" lungo il lato lungo del foglio.</span><span class="sxs-lookup"><span data-stu-id="20cc1-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="20cc1-116">Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, viene usato il `Contains` metodo di <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="20cc1-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="20cc1-117">Questo passaggio non è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="20cc1-117">This step is not strictly necessary.</span></span> <span data-ttu-id="20cc1-118">Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo usato di seguito consente di controllare ogni richiesta <xref:System.Printing.PrintTicket> in rispetto alle funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="20cc1-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="20cc1-119">Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante sostituirà una richiesta alternativa nell' <xref:System.Printing.PrintTicket> oggetto restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="20cc1-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="20cc1-120">Se la stampante supporta la duplexing, il codice di esempio <xref:System.Printing.PrintTicket> crea un oggetto che richiede il duplexing.</span><span class="sxs-lookup"><span data-stu-id="20cc1-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="20cc1-121">Tuttavia, l'applicazione non specifica ogni possibile impostazione della stampante disponibile nell' <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="20cc1-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="20cc1-122">Questo sarebbe uno spreco di tempo per programmatore e programma.</span><span class="sxs-lookup"><span data-stu-id="20cc1-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="20cc1-123">Al contrario, il codice imposta solo la richiesta duplex, quindi unisce questo <xref:System.Printing.PrintTicket> oggetto a un oggetto esistente, completamente configurato e convalidato, <xref:System.Printing.PrintTicket>, in questo caso, il valore <xref:System.Printing.PrintTicket>predefinito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="20cc1-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="20cc1-124">Di conseguenza, l'esempio chiama <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> il metodo per unire il nuovo, minimo <xref:System.Printing.PrintTicket> , con il valore predefinito <xref:System.Printing.PrintTicket>dell'utente.</span><span class="sxs-lookup"><span data-stu-id="20cc1-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="20cc1-125">Restituisce un oggetto <xref:System.Printing.ValidationResult> che include il nuovo <xref:System.Printing.PrintTicket> oggetto come una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="20cc1-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="20cc1-126">Nell'esempio viene quindi testato il nuovo <xref:System.Printing.PrintTicket> duplex delle richieste.</span><span class="sxs-lookup"><span data-stu-id="20cc1-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="20cc1-127">In caso contrario, l'esempio lo rende il nuovo ticket di stampa predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="20cc1-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="20cc1-128">Se il passaggio 2 precedente era stato interrotto e la stampante non supportava il duplex lungo il lato lungo, il test avrebbe avuto esito `false`.</span><span class="sxs-lookup"><span data-stu-id="20cc1-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="20cc1-129">(Vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="20cc1-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="20cc1-130">L'ultimo passaggio significativo consiste nel eseguire il commit della modifica <xref:System.Printing.PrintQueue.UserPrintTicket%2A> alla proprietà <xref:System.Printing.PrintQueue> di con il <xref:System.Printing.PrintQueue.Commit%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="20cc1-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="20cc1-131">Per poter testare rapidamente questo esempio, il resto viene presentato di seguito.</span><span class="sxs-lookup"><span data-stu-id="20cc1-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="20cc1-132">Creare un progetto e uno spazio dei nomi e quindi incollare entrambi i frammenti di codice di questo articolo nel blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="20cc1-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="20cc1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20cc1-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="20cc1-134">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="20cc1-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="20cc1-135">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="20cc1-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="20cc1-136">Stampa schema</span><span class="sxs-lookup"><span data-stu-id="20cc1-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
