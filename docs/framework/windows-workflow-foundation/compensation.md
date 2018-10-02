---
title: Compensazione
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: 840730acd9289fd394906c49186846e3204c4a99
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863468"
---
# <a name="compensation"></a><span data-ttu-id="3589d-102">Compensazione</span><span class="sxs-lookup"><span data-stu-id="3589d-102">Compensation</span></span>
<span data-ttu-id="3589d-103">La compensazione in Windows Workflow Foundation (WF) è il meccanismo mediante il quale in precedenza il lavoro completato può essere annullato o compensato (seguendo la logica definita dall'applicazione) quando si verifica un errore successivo.</span><span class="sxs-lookup"><span data-stu-id="3589d-103">Compensation in Windows Workflow Foundation (WF) is the mechanism by which previously completed work can be undone or compensated (following the logic defined by the application) when a subsequent failure occurs.</span></span> <span data-ttu-id="3589d-104">Contenuto della sezione viene illustrato come usare la compensazione nei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3589d-104">This section describes how to use compensation in workflows.</span></span>  
  
## <a name="compensation-vs-transactions"></a><span data-ttu-id="3589d-105">Differenze tra compensazioni e Transazioni</span><span class="sxs-lookup"><span data-stu-id="3589d-105">Compensation vs. Transactions</span></span>  
 <span data-ttu-id="3589d-106">Una transazione consente di combinare più operazioni in un'unica unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3589d-106">A transaction allows you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="3589d-107">Quando viene usata una transazione, l'applicazione può annullare, ovvero eseguire il rollback, di tutte le modifiche eseguite dall'interno della transazione se si verificano errori durante qualsiasi parte del processo della transazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-107">Using a transaction gives your application the ability to abort (roll back) all changes executed from within the transaction if any errors occur during any part of the transaction process.</span></span> <span data-ttu-id="3589d-108">L'utilizzo di transazioni potrebbe tuttavia non essere adatto per un lavoro a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="3589d-108">However, using transactions may not be appropriate if the work is long running.</span></span> <span data-ttu-id="3589d-109">Ad esempio, un'applicazione di pianificazione di viaggi viene implementata come flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3589d-109">For example, a travel planning application is implemented as a workflow.</span></span> <span data-ttu-id="3589d-110">I passaggi del flusso di lavoro possono essere costituiti dalla prenotazione di un volo, dall'attesa dell'approvazione da parte del responsabile e dal pagamento del volo.</span><span class="sxs-lookup"><span data-stu-id="3589d-110">The steps of the workflow may consist of booking a flight, waiting for manager approval, and then paying for the flight.</span></span> <span data-ttu-id="3589d-111">Questo processo potrebbe richiedere molti giorni e non è funzionale che i passaggi di prenotazione e pagamento del volo prendano parte alla stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-111">This process could take many days and it is not practical for the steps of booking and paying for the flight to participate in the same transaction.</span></span> <span data-ttu-id="3589d-112">In uno scenario come questo, la compensazione potrebbe essere usata per annullare il passaggio di prenotazione del flusso di lavoro se, successivamente, si verifica un errore nell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-112">In a scenario such as this, compensation could be used to undo the booking step of the workflow if there is a failure later in the processing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3589d-113">In questo argomento viene illustrato il concetto di compensazione nei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3589d-113">This topic covers compensation in workflows.</span></span> <span data-ttu-id="3589d-114">Per altre informazioni sulle transazioni nei flussi di lavoro, vedere [transazioni](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md) e <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="3589d-114">For more information about transactions in workflows, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md) and <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="3589d-115">Per altre informazioni sulle transazioni, vedere <xref:System.Transactions?displayProperty=nameWithType> e <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3589d-115">For more information about transactions, see <xref:System.Transactions?displayProperty=nameWithType> and <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span></span>  
  
## <a name="using-compensableactivity"></a><span data-ttu-id="3589d-116">Uso di CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="3589d-116">Using CompensableActivity</span></span>  
 <span data-ttu-id="3589d-117">L'oggetto <xref:System.Activities.Statements.CompensableActivity> è l'attività di compensazione principale di [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3589d-117"><xref:System.Activities.Statements.CompensableActivity> is the core compensation activity in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="3589d-118">Qualsiasi attività che esegue un lavoro che necessita di compensazione viene inserita nell'oggetto <xref:System.Activities.Statements.CompensableActivity.Body%2A> di un oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-118">Any activities that perform work that may need to be compensated are placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="3589d-119">In questo esempio il passaggio di prenotazione relativo all'acquisto di un volo viene inserito nell'oggetto <xref:System.Activities.Statements.CompensableActivity.Body%2A> di un oggetto <xref:System.Activities.Statements.CompensableActivity>, mentre l'annullamento della prenotazione viene inserito nell'oggetto <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="3589d-119">In this example, the reservation step of purchasing a flight is placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> and the cancellation of the reservation is placed into the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span></span> <span data-ttu-id="3589d-120">Subito dopo l'oggetto <xref:System.Activities.Statements.CompensableActivity> nel flusso di lavoro si trovano due attività che attendono l'approvazione del responsabile e successivamente completano il passaggio di acquisto del volo.</span><span class="sxs-lookup"><span data-stu-id="3589d-120">Immediately following the <xref:System.Activities.Statements.CompensableActivity> in the workflow are two activities that wait for manager approval and then complete the purchasing step of the flight.</span></span> <span data-ttu-id="3589d-121">Se una condizione di errore provoca l'annullamento del flusso di lavoro dopo il corretto completamento dell'oggetto <xref:System.Activities.Statements.CompensableActivity>, le attività nel gestore <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> vengono pianificate e il volo viene annullato.</span><span class="sxs-lookup"><span data-stu-id="3589d-121">If an error condition causes the workflow to be canceled after the <xref:System.Activities.Statements.CompensableActivity> has successfully completed, then the activities in the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> handler are scheduled and the flight is canceled.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#1](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 <span data-ttu-id="3589d-122">L'esempio seguente è il flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="3589d-122">The following example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="3589d-123">Quando il flusso di lavoro viene richiamato, l'output seguente viene visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="3589d-123">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="3589d-124">**ReserveFlight: Ticket è riservato.**</span><span class="sxs-lookup"><span data-stu-id="3589d-124">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="3589d-125">**ManagerApproval: Approvazione del responsabile ricevuto.** </span><span class="sxs-lookup"><span data-stu-id="3589d-125">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="3589d-126">**PurchaseFlight: Ticket viene acquistata.** </span><span class="sxs-lookup"><span data-stu-id="3589d-126">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="3589d-127">**Flusso di lavoro completato con stato: chiuso.**</span><span class="sxs-lookup"><span data-stu-id="3589d-127">**Workflow completed successfully with status: Closed.**</span></span>    
> [!NOTE]
>  <span data-ttu-id="3589d-128">Nelle attività di esempio in questo argomento, quale `ReserveFlight`, vengono visualizzati nome e scopo nella console per consentire di illustrare l'ordine in cui vengono eseguite le attività quando si verifica la compensazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-128">The sample activities in this topic such as `ReserveFlight` display their name and purpose to the console to help illustrate the order in which the activities are executed when compensation occurs.</span></span>  
  
### <a name="default-workflow-compensation"></a><span data-ttu-id="3589d-129">Compensazione del flusso di lavoro predefinita</span><span class="sxs-lookup"><span data-stu-id="3589d-129">Default Workflow Compensation</span></span>  
 <span data-ttu-id="3589d-130">Per impostazione predefinita, se il flusso di lavoro viene annullato, viene eseguita la logica di compensazione per qualsiasi attività compensabile che è stata completata correttamente e non è stata già confermata o compensata.</span><span class="sxs-lookup"><span data-stu-id="3589d-130">By default, if the workflow is canceled, the compensation logic is run for any compensable activity that has successfully completely and has not already been confirmed or compensated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3589d-131">Quando un <xref:System.Activities.Statements.CompensableActivity> viene *confermato*, compensazione per l'attività non può essere richiamata.</span><span class="sxs-lookup"><span data-stu-id="3589d-131">When a <xref:System.Activities.Statements.CompensableActivity> is *confirmed*, compensation for the activity can no longer be invoked.</span></span> <span data-ttu-id="3589d-132">Il processo di conferma verrà illustrato più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3589d-132">The confirmation process is described later in this section.</span></span>  
  
 <span data-ttu-id="3589d-133">In questo esempio viene generata un'eccezione dopo la prenotazione del volo ma prima del passaggio di approvazione da parte del responsabile.</span><span class="sxs-lookup"><span data-stu-id="3589d-133">In this example, an exception is thrown after the flight is reserved but before the manager approval step.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#2](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 <span data-ttu-id="3589d-134">In questo esempio viene illustrato il flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="3589d-134">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 <span data-ttu-id="3589d-135">Quando viene richiamato il flusso di lavoro, l'eccezione della condizione di errore simulata viene gestita dall'applicazione host in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, il flusso di lavoro viene annullato e la logica di compensazione viene richiamata.</span><span class="sxs-lookup"><span data-stu-id="3589d-135">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the compensation logic is invoked.</span></span>  
  
 <span data-ttu-id="3589d-136">**ReserveFlight: Ticket è riservato.**</span><span class="sxs-lookup"><span data-stu-id="3589d-136">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="3589d-137">**SimulatedErrorCondition: Generazione di un'eccezione ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="3589d-137">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="3589d-138">**Eccezione non gestita del flusso di lavoro:** </span><span class="sxs-lookup"><span data-stu-id="3589d-138">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="3589d-139">**System. ApplicationException: Condizione di errore simulata nel flusso di lavoro.** </span><span class="sxs-lookup"><span data-stu-id="3589d-139">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="3589d-140">**CancelFlight: Ticket viene annullata.** </span><span class="sxs-lookup"><span data-stu-id="3589d-140">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="3589d-141">**Flusso di lavoro completato con stato: annullata.**</span><span class="sxs-lookup"><span data-stu-id="3589d-141">**Workflow completed successfully with status: Canceled.**</span></span>    
### <a name="cancellation-and-compensableactivity"></a><span data-ttu-id="3589d-142">Annullamento e CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="3589d-142">Cancellation and CompensableActivity</span></span>  
 <span data-ttu-id="3589d-143">Se le attività in <xref:System.Activities.Statements.CompensableActivity.Body%2A> di un oggetto <xref:System.Activities.Statements.CompensableActivity> non sono state completate e l'attività è annullata, vengono eseguite le attività in <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="3589d-143">If the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled, the activities in the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> are executed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3589d-144"><xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> viene richiamato solo se le attività nell'oggetto <xref:System.Activities.Statements.CompensableActivity.Body%2A> dell'oggetto <xref:System.Activities.Statements.CompensableActivity> non sono state completate e l'attività è annullata.</span><span class="sxs-lookup"><span data-stu-id="3589d-144">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is only invoked if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled.</span></span> <span data-ttu-id="3589d-145"><xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> viene eseguito solo se le attività nell'oggetto <xref:System.Activities.Statements.CompensableActivity.Body%2A> dell'oggetto <xref:System.Activities.Statements.CompensableActivity> sono state completate correttamente e viene successivamente richiamata la compensazione sull'attività.</span><span class="sxs-lookup"><span data-stu-id="3589d-145">The <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> is only executed if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have successfully completed and compensation is subsequently invoked on the activity.</span></span>  
  
 <span data-ttu-id="3589d-146"><xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> fornisce offre agli autori del flusso di lavoro la possibilità per fornire la logica di annullamento appropriata.</span><span class="sxs-lookup"><span data-stu-id="3589d-146">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gives workflow authors the opportunity to provide any appropriate cancellation logic.</span></span> <span data-ttu-id="3589d-147">Nell'esempio seguente viene generata un'eccezione durante l'esecuzione di <xref:System.Activities.Statements.CompensableActivity.Body%2A>, quindi viene richiamato <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="3589d-147">In the following example, an exception is thrown during the execution of the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, and then the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is invoked.</span></span>  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 <span data-ttu-id="3589d-148">Questo esempio è il flusso di lavoro in XAML</span><span class="sxs-lookup"><span data-stu-id="3589d-148">This example is the workflow in XAML</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="3589d-149">Quando viene richiamato il flusso di lavoro, l'eccezione della condizione di errore simulata viene gestita dall'applicazione host in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, il flusso di lavoro viene annullato e viene richiamata la logica di cancellazione di <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-149">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the cancellation logic of the <xref:System.Activities.Statements.CompensableActivity> is invoked.</span></span> <span data-ttu-id="3589d-150">In questo esempio, la logica di compensazione e la logica di annullamento hanno obiettivi differenti.</span><span class="sxs-lookup"><span data-stu-id="3589d-150">In this example, the compensation logic and the cancellation logic have different goals.</span></span> <span data-ttu-id="3589d-151">Se <xref:System.Activities.Statements.CompensableActivity.Body%2A> è stato completato correttamente, questo significa che è stato effettuato il prelievo dalla carta di credito e il volo è stato prenotato, pertanto la compensazione dovrebbe annullare entrambi i passaggi.</span><span class="sxs-lookup"><span data-stu-id="3589d-151">If the <xref:System.Activities.Statements.CompensableActivity.Body%2A> completed successfully, then this means the credit card was charged and the flight booked, so the compensation should undo both steps.</span></span> <span data-ttu-id="3589d-152">In questo esempio, l'annullamento del volo annulla automaticamente l'addebito sulla carta di credito. Tuttavia, se <xref:System.Activities.Statements.CompensableActivity> viene annullato, questo significa che <xref:System.Activities.Statements.CompensableActivity.Body%2A> non è stato completato e la logica di <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> deve essere in grado di determinare il metodo migliore di gestire l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="3589d-152">(In this example, canceling the flight automatically cancels the credit card charges.) However, if the <xref:System.Activities.Statements.CompensableActivity> is canceled, this means the <xref:System.Activities.Statements.CompensableActivity.Body%2A> did not complete and so the logic of the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> needs to be able to determine how to best handle the cancellation.</span></span> <span data-ttu-id="3589d-153">In questo esempio, <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> annulla l'addebito sulla carta di credito, tuttavia, poiché `ReserveFlight` era l'ultima attività in <xref:System.Activities.Statements.CompensableActivity.Body%2A>, non tenta di annullare il volo.</span><span class="sxs-lookup"><span data-stu-id="3589d-153">In this example, the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancels the credit card charge, but since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, it does not attempt to cancel the flight.</span></span> <span data-ttu-id="3589d-154">Dal momento che `ReserveFlight` era l'ultima attività in <xref:System.Activities.Statements.CompensableActivity.Body%2A>, se fosse stata completata correttamente, l'oggetto <xref:System.Activities.Statements.CompensableActivity.Body%2A> sarebbe stato completato e non sarebbe stato possibile alcun annullamento.</span><span class="sxs-lookup"><span data-stu-id="3589d-154">Since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, if it had successfully completed then the <xref:System.Activities.Statements.CompensableActivity.Body%2A> would have completed and no cancellation would be possible.</span></span>  
  
 <span data-ttu-id="3589d-155">**ChargeCreditCard: Carta di credito addebito per volo.**</span><span class="sxs-lookup"><span data-stu-id="3589d-155">**ChargeCreditCard: Charge credit card for flight.**</span></span>  
<span data-ttu-id="3589d-156">**SimulatedErrorCondition: Generazione di un'eccezione ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="3589d-156">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="3589d-157">**Eccezione non gestita del flusso di lavoro:** </span><span class="sxs-lookup"><span data-stu-id="3589d-157">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="3589d-158">**System. ApplicationException: Condizione di errore simulata nel flusso di lavoro.** </span><span class="sxs-lookup"><span data-stu-id="3589d-158">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="3589d-159">**CancelCreditCard: Annullamento delle spese della carta di credito.** </span><span class="sxs-lookup"><span data-stu-id="3589d-159">**CancelCreditCard: Cancel credit card charges.** </span></span>  
<span data-ttu-id="3589d-160">**Flusso di lavoro completato con stato: annullata.**</span><span class="sxs-lookup"><span data-stu-id="3589d-160">**Workflow completed successfully with status: Canceled.**</span></span>  <span data-ttu-id="3589d-161">Per altre informazioni sull'annullamento, vedere [annullamento](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="3589d-161">For more information about cancellation, see [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a><span data-ttu-id="3589d-162">Compensazione esplicita tramite l'attività Compensate</span><span class="sxs-lookup"><span data-stu-id="3589d-162">Explicit Compensation Using the Compensate Activity</span></span>  
 <span data-ttu-id="3589d-163">Nella sezione precedente è stata illustrata la compensazione implicita.</span><span class="sxs-lookup"><span data-stu-id="3589d-163">In the previous section, implicit compensation was covered.</span></span> <span data-ttu-id="3589d-164">Si tratta di un tipo di compensazione che può risultare appropriata per scenari semplici, ma se occorre un controllo più esplicito sulla pianificazione della gestione della compensazione è possibile usare l'attività <xref:System.Activities.Statements.Compensate>.</span><span class="sxs-lookup"><span data-stu-id="3589d-164">Implicit compensation can be appropriate for simple scenarios, but if more explicit control is required over the scheduling of compensation handling then the <xref:System.Activities.Statements.Compensate> activity can be used.</span></span> <span data-ttu-id="3589d-165">Per iniziare il processo di compensazione con l'attività <xref:System.Activities.Statements.Compensate>, viene usato l'oggetto <xref:System.Activities.Statements.CompensationToken> dell'oggetto <xref:System.Activities.Statements.CompensableActivity> per il quale si desidera la compensazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-165">To initiate the compensation process with the <xref:System.Activities.Statements.Compensate> activity, the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> for which compensation is desired is used.</span></span> <span data-ttu-id="3589d-166">L'attività <xref:System.Activities.Statements.Compensate> può essere usata per iniziare la compensazione su qualsiasi oggetto <xref:System.Activities.Statements.CompensableActivity> completato che non è stato confermato o compensato.</span><span class="sxs-lookup"><span data-stu-id="3589d-166">The <xref:System.Activities.Statements.Compensate> activity can be used to initiate compensation on any completed <xref:System.Activities.Statements.CompensableActivity> that has not been confirmed or compensated.</span></span> <span data-ttu-id="3589d-167">Ad esempio, un'attività <xref:System.Activities.Statements.Compensate> potrebbe essere usata nella sezione <xref:System.Activities.Statements.TryCatch.Catches%2A> di un'attività <xref:System.Activities.Statements.TryCatch> o in qualsiasi momento dopo il completamento dell'oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-167">For example, a <xref:System.Activities.Statements.Compensate> activity could be used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity, or any time after the <xref:System.Activities.Statements.CompensableActivity> has completed.</span></span> <span data-ttu-id="3589d-168">In questo esempio l'attività <xref:System.Activities.Statements.Compensate> viene usata nella sezione <xref:System.Activities.Statements.TryCatch.Catches%2A> di un'attività <xref:System.Activities.Statements.TryCatch> per invertire l'azione dell'oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-168">In this example, the <xref:System.Activities.Statements.Compensate> activity is used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity to reverse the action of the <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#3](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 <span data-ttu-id="3589d-169">In questo esempio viene illustrato il flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="3589d-169">This example is the workflow in XAML.</span></span>  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 <span data-ttu-id="3589d-170">Quando il flusso di lavoro viene richiamato, l'output seguente viene visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="3589d-170">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="3589d-171">**ReserveFlight: Ticket è riservato.**</span><span class="sxs-lookup"><span data-stu-id="3589d-171">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="3589d-172">**SimulatedErrorCondition: Generazione di un'eccezione ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="3589d-172">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="3589d-173">**CancelFlight: Ticket viene annullata.** </span><span class="sxs-lookup"><span data-stu-id="3589d-173">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="3589d-174">**Flusso di lavoro completato con stato: chiuso.**</span><span class="sxs-lookup"><span data-stu-id="3589d-174">**Workflow completed successfully with status: Closed.**</span></span>    
### <a name="confirming-compensation"></a><span data-ttu-id="3589d-175">Conferma della compensazione</span><span class="sxs-lookup"><span data-stu-id="3589d-175">Confirming Compensation</span></span>  
 <span data-ttu-id="3589d-176">Per impostazione predefinita, le attività compensabili possono essere compensate in qualsiasi momento una volta completate.</span><span class="sxs-lookup"><span data-stu-id="3589d-176">By default, compensable activities can be compensated any time after they have completed.</span></span> <span data-ttu-id="3589d-177">In alcuni casi però questo potrebbe non essere appropriato.</span><span class="sxs-lookup"><span data-stu-id="3589d-177">In some scenarios this may not be appropriate.</span></span> <span data-ttu-id="3589d-178">Nell'esempio precedente la compensazione relativa alla prenotazione del biglietto consisteva nell'annullamento della prenotazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-178">In the previous example the compensation to reserving the ticket was to cancel the reservation.</span></span> <span data-ttu-id="3589d-179">Tuttavia, una volta completato il volo, questo passaggio di compensazione non è più valido.</span><span class="sxs-lookup"><span data-stu-id="3589d-179">However, after the flight has been completed this compensation step is no longer valid.</span></span> <span data-ttu-id="3589d-180">La conferma dell'attività compensabile richiama l'attività specificata da <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="3589d-180">Confirming the compensable activity invokes the activity specified by the <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span></span> <span data-ttu-id="3589d-181">Un possibile utilizzo consiste nel consentire a qualsiasi risorsa necessaria di eseguire la compensazione da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="3589d-181">One possible use for this is to allow any resources that are necessary to perform the compensation to be released.</span></span> <span data-ttu-id="3589d-182">Una volta confermata, un'attività compensabile non può essere compensata e se si tenta tale operazione, verrà generata un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="3589d-182">After a compensable activity is confirmed it is not possible for it to be compensated, and if this is attempted an <xref:System.InvalidOperationException> exception is thrown.</span></span> <span data-ttu-id="3589d-183">Quando un flusso di lavoro viene completato correttamente, tutte le attività compensabili non confermate e non compensate completate correttamente vengono confermate nell'ordine inverso rispetto al completamento.</span><span class="sxs-lookup"><span data-stu-id="3589d-183">When a workflow completes successfully, all non-confirmed and non-compensated compensable activities that completed successfully are confirmed in reverse order of completion.</span></span> <span data-ttu-id="3589d-184">In questo esempio il volo è prenotato, acquistato e completato, quindi l'attività compensabile è confermata.</span><span class="sxs-lookup"><span data-stu-id="3589d-184">In this example the flight is reserved, purchased, and completed, and then the compensable activity is confirmed.</span></span> <span data-ttu-id="3589d-185">Per confermare un oggetto <xref:System.Activities.Statements.CompensableActivity>, usare l'attività <xref:System.Activities.Statements.Confirm> e specificare l'oggetto <xref:System.Activities.Statements.CompensationToken> dell'oggetto <xref:System.Activities.Statements.CompensableActivity> da confermare.</span><span class="sxs-lookup"><span data-stu-id="3589d-185">To confirm a <xref:System.Activities.Statements.CompensableActivity>, use the <xref:System.Activities.Statements.Confirm> activity and specify the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> to confirm.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#4](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 <span data-ttu-id="3589d-186">In questo esempio viene illustrato il flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="3589d-186">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
<span data-ttu-id="3589d-187">Quando il flusso di lavoro viene richiamato, l'output seguente viene visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="3589d-187">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
<span data-ttu-id="3589d-188">**ReserveFlight: Ticket è riservato.**</span><span class="sxs-lookup"><span data-stu-id="3589d-188">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="3589d-189">**ManagerApproval: Approvazione del responsabile ricevuto.** </span><span class="sxs-lookup"><span data-stu-id="3589d-189">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="3589d-190">**PurchaseFlight: Ticket viene acquistata.** </span><span class="sxs-lookup"><span data-stu-id="3589d-190">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="3589d-191">**TakeFlight: Volo viene completata.** </span><span class="sxs-lookup"><span data-stu-id="3589d-191">**TakeFlight: Flight is completed.** </span></span>  
<span data-ttu-id="3589d-192">**ConfirmFlight: Volo non è stato usato, Nessun compenso possibili.** </span><span class="sxs-lookup"><span data-stu-id="3589d-192">**ConfirmFlight: Flight has been taken, no compensation possible.** </span></span>  
<span data-ttu-id="3589d-193">**Flusso di lavoro completato con stato: chiuso.**</span><span class="sxs-lookup"><span data-stu-id="3589d-193">**Workflow completed successfully with status: Closed.**</span></span>   

## <a name="nesting-compensation-activities"></a><span data-ttu-id="3589d-194">Annidamento delle attività di compensazione</span><span class="sxs-lookup"><span data-stu-id="3589d-194">Nesting Compensation Activities</span></span>  

<span data-ttu-id="3589d-195">Un oggetto <xref:System.Activities.Statements.CompensableActivity> può essere posizionato nella sezione <xref:System.Activities.Statements.CompensableActivity.Body%2A> di un altro oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-195">A <xref:System.Activities.Statements.CompensableActivity> can be placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> section of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="3589d-196">Un oggetto <xref:System.Activities.Statements.CompensableActivity> non può essere inserito in un gestore di un altro oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="3589d-196">A <xref:System.Activities.Statements.CompensableActivity> may not be placed into a handler of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="3589d-197">È responsabilità di un oggetto <xref:System.Activities.Statements.CompensableActivity> padre garantire che quando viene annullato, confermato o compensato, tutte le attività figlio compensabili che sono state completate correttamente e non sono state già confermate o compensate siano confermate o compensate prima dell'annullamento, la conferma o la compensazione del padre.</span><span class="sxs-lookup"><span data-stu-id="3589d-197">It is the responsibility of a parent <xref:System.Activities.Statements.CompensableActivity> to ensure that when it is canceled, confirmed, or compensated, all child compensable activities that have completed successfully and have not already been confirmed or compensated must be confirmed or compensated before the parent completes cancellation, confirmation, or compensation.</span></span> <span data-ttu-id="3589d-198">Se questo comportamento non è determinato in modo esplicito, l'oggetto <xref:System.Activities.Statements.CompensableActivity> padre compenserà in modo implicito le attività figlio compensabili se ha ricevuto l'indicazione di annullamento o compensazione.</span><span class="sxs-lookup"><span data-stu-id="3589d-198">If this is not modeled explicitly the parent <xref:System.Activities.Statements.CompensableActivity> will implicitly compensate child compensable activities if the parent received the cancel or compensate signal.</span></span> <span data-ttu-id="3589d-199">Se il padre ha ricevuto l'indicazione di conferma, confermerà in modo implicito le attività figlio compensabili.</span><span class="sxs-lookup"><span data-stu-id="3589d-199">If the parent received the confirm signal the parent will implicitly confirm child compensable activities.</span></span> <span data-ttu-id="3589d-200">Se la logica di gestione di un annullamento, una conferma o una compensazione è modellata in modo esplicito nel gestore dell'oggetto <xref:System.Activities.Statements.CompensableActivity> padre, qualsiasi oggetto figlio non esplicitamente gestito verrà confermato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="3589d-200">If the logic to handle cancellation, confirmation, or compensation is explicitly modeled in the handler of the parent <xref:System.Activities.Statements.CompensableActivity>, any child not explicitly handled will be implicitly confirmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3589d-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3589d-201">See Also</span></span>

- <xref:System.Activities.Statements.CompensableActivity>  
- <xref:System.Activities.Statements.Compensate>  
- <xref:System.Activities.Statements.Confirm>  
- <xref:System.Activities.Statements.CompensationToken>