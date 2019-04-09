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
ms.openlocfilehash: 750234a7073b3931b4f3ce5674f3989fe119c50c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199947"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="73a4b-102">Procedura: Convalidare e unire PrintTicket</span><span class="sxs-lookup"><span data-stu-id="73a4b-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="73a4b-103">Il [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [printschema](https://go.microsoft.com/fwlink/?LinkId=186397) include flessibili ed estensibili <xref:System.Printing.PrintCapabilities> e <xref:System.Printing.PrintTicket> elementi.</span><span class="sxs-lookup"><span data-stu-id="73a4b-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="73a4b-104">Il primo indica in modo dettagliato le funzionalità di un dispositivo di stampa e specifica il secondo modo in cui il dispositivo deve usare tali funzionalità rispetto a una determinata sequenza di documenti, singoli documenti o singola pagina.</span><span class="sxs-lookup"><span data-stu-id="73a4b-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="73a4b-105">Una tipica sequenza di attività per un'applicazione che supporta la stampa sarebbe come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="73a4b-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="73a4b-106">Determinare le funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="73a4b-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="73a4b-107">Configurare un <xref:System.Printing.PrintTicket> usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="73a4b-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="73a4b-108">Convalidare il <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="73a4b-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="73a4b-109">Questo articolo illustra come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="73a4b-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73a4b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="73a4b-110">Example</span></span>  
 <span data-ttu-id="73a4b-111">Nel semplice esempio seguente, si è interessati solo se una stampante può supportare la stampa fronte retro-stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="73a4b-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="73a4b-112">Come indicato di seguito sono riportati i passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="73a4b-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="73a4b-113">Ottenere un <xref:System.Printing.PrintCapabilities> dell'oggetto con il <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="73a4b-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="73a4b-114">Verificare la presenza della funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="73a4b-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="73a4b-115">Nell'esempio seguente, viene eseguito il test di <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> proprietà del <xref:System.Printing.PrintCapabilities> la presenza di funzionalità di stampa su entrambi i lati di un foglio di carta con la"pagina" dell'oggetto sul lato lungo del foglio.</span><span class="sxs-lookup"><span data-stu-id="73a4b-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="73a4b-116">Poiché <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> è una raccolta, usiamo il `Contains` metodo <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="73a4b-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73a4b-117">Questo passaggio non è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="73a4b-117">This step is not strictly necessary.</span></span> <span data-ttu-id="73a4b-118">Il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> metodo seguente verificherà ogni richiesta <xref:System.Printing.PrintTicket> rispetto alle funzionalità della stampante.</span><span class="sxs-lookup"><span data-stu-id="73a4b-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="73a4b-119">Se la funzionalità richiesta non è supportata dalla stampante, il driver della stampante consente di sostituire una richiesta in alternativa il <xref:System.Printing.PrintTicket> restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="73a4b-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="73a4b-120">Se la stampante supporta la stampa fronte retro, il codice di esempio crea un <xref:System.Printing.PrintTicket> che richiede la stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="73a4b-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="73a4b-121">Ma l'applicazione non specifica ogni stampante possibili impostazione disponibile nel <xref:System.Printing.PrintTicket> elemento.</span><span class="sxs-lookup"><span data-stu-id="73a4b-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="73a4b-122">Sarebbe dispendioso di programmatore e ora del programma.</span><span class="sxs-lookup"><span data-stu-id="73a4b-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="73a4b-123">Al contrario, il codice imposta solo la richiesta di stampa fronte retro e quindi unisce questo <xref:System.Printing.PrintTicket> con un oggetto esistente, completamente configurata e convalidata <xref:System.Printing.PrintTicket>, in questo caso, predefinita dell'utente <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="73a4b-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="73a4b-124">Di conseguenza, l'esempio chiama il <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> per unire il nuovo metodo minima in quando <xref:System.Printing.PrintTicket> predefinito dell'utente <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="73a4b-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="73a4b-125">Restituisce un <xref:System.Printing.ValidationResult> che include il nuovo <xref:System.Printing.PrintTicket> come una delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="73a4b-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="73a4b-126">L'esempio verifica quindi che il nuovo <xref:System.Printing.PrintTicket> richiede la stampa fronte retro.</span><span class="sxs-lookup"><span data-stu-id="73a4b-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="73a4b-127">In caso affermativo, quindi l'esempio rende il nuovo print ticket per l'utente predefinito.</span><span class="sxs-lookup"><span data-stu-id="73a4b-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="73a4b-128">Se viene omesso il passaggio 2 precedente e la stampante non supporta la stampa fronte retro lungo il lato lungo, quindi il test avrebbe comportato `false`.</span><span class="sxs-lookup"><span data-stu-id="73a4b-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="73a4b-129">(Vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="73a4b-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="73a4b-130">L'ultimo elemento significativo è eseguire il commit per la modifica di <xref:System.Printing.PrintQueue.UserPrintTicket%2A> proprietà del <xref:System.Printing.PrintQueue> con il <xref:System.Printing.PrintQueue.Commit%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="73a4b-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="73a4b-131">In modo che è possibile testare rapidamente in questo esempio, la parte restante viene presentata di seguito.</span><span class="sxs-lookup"><span data-stu-id="73a4b-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="73a4b-132">Creare un progetto e uno spazio dei nomi e quindi incollare entrambi i frammenti di codice in questo articolo il blocco dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73a4b-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="73a4b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73a4b-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="73a4b-134">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="73a4b-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="73a4b-135">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="73a4b-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="73a4b-136">Schema di stampa</span><span class="sxs-lookup"><span data-stu-id="73a4b-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
