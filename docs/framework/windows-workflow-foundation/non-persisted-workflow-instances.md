---
title: Istanze del flusso di lavoro non persistenti
ms.date: 03/30/2017
ms.assetid: 5e01af77-6b14-4964-91a5-7dfd143449c0
ms.openlocfilehash: 2f28e7b44f951151b47a6424670e5101960e91eb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649346"
---
# <a name="non-persisted-workflow-instances"></a><span data-ttu-id="3240e-102">Istanze del flusso di lavoro non persistenti</span><span class="sxs-lookup"><span data-stu-id="3240e-102">Non-Persisted Workflow Instances</span></span>
<span data-ttu-id="3240e-103">Quando viene creata una nuova istanza di un flusso di lavoro che mantiene persistente lo stato in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, nell'host del servizio viene creata una voce per il servizio specifico nell'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="3240e-103">When a new instance of a workflow is created that persists its state in the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the service host creates an entry for that service in the instance store.</span></span> <span data-ttu-id="3240e-104">Successivamente, quando l'istanza del flusso di lavoro viene resa persistente per la prima volta, in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> viene archiviato lo stato dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="3240e-104">Subsequently, when the workflow instance is persisted for the first time, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> stores the current instance state.</span></span> <span data-ttu-id="3240e-105">Se il flusso di lavoro è ospitato nel servizio Attivazione processo Windows, anche i dati della distribuzione del servizio vengono scritti nell'archivio di istanze quando l'istanza è stata resa persistente per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3240e-105">If the workflow is hosted in the Windows Process Activation Service, the service deployment data is also written to the instance store when the instance is persisted for the first time.</span></span>  
  
 <span data-ttu-id="3240e-106">Fino a quando non è stata resa persistente l'istanza del flusso di lavoro, è in un **non persistenti** dello stato.</span><span class="sxs-lookup"><span data-stu-id="3240e-106">As long as the workflow instance has not been persisted, it is in a **non-persisted** state.</span></span> <span data-ttu-id="3240e-107">In questo stato non è possibile recuperare l'istanza del flusso di lavoro dopo un riciclo del dominio applicazione oppure un errore dell'host o del computer.</span><span class="sxs-lookup"><span data-stu-id="3240e-107">While in this state, the workflow instance cannot be recovered after an application domain recycle, host failure, or computer failure.</span></span>  
  
## <a name="the-non-persisted-state"></a><span data-ttu-id="3240e-108">Stato non persistente</span><span class="sxs-lookup"><span data-stu-id="3240e-108">The Non-Persisted State</span></span>  
 <span data-ttu-id="3240e-109">Le istanze del flusso di lavoro durevoli che non sono ancora state rese persistenti rimangono in uno stato non persistente nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3240e-109">Durable workflow instances that have not been persisted remain in a non-persisted state in the following cases:</span></span>  
  
- <span data-ttu-id="3240e-110">L'host del servizio si arresta in modo anomalo prima che l'istanza del flusso di lavoro venga resa persistente per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3240e-110">The service host crashes before the workflow instance is persisted for the first time.</span></span> <span data-ttu-id="3240e-111">L'istanza rimane nell'archivio di istanze e non viene recuperata.</span><span class="sxs-lookup"><span data-stu-id="3240e-111">The workflow instance remains in the instance store and is not recovered.</span></span> <span data-ttu-id="3240e-112">In caso di arrivo di un messaggio correlato, l'istanza del flusso di lavoro diventa nuovamente attiva.</span><span class="sxs-lookup"><span data-stu-id="3240e-112">If a correlated message arrives, the workflow instance becomes active again.</span></span>  
  
- <span data-ttu-id="3240e-113">Si verifica un'eccezione dell'istanza del flusso di lavoro prima che questa venga resa persistente per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3240e-113">The workflow instance experiences an exception before it is persisted for the first time.</span></span> <span data-ttu-id="3240e-114">A seconda dell'elemento <xref:System.Activities.UnhandledExceptionAction> restituito, possono verificarsi gli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="3240e-114">Depending on the <xref:System.Activities.UnhandledExceptionAction> returned, the following scenarios occur:</span></span>  
  
    - <span data-ttu-id="3240e-115"><xref:System.Activities.UnhandledExceptionAction> è impostato su <xref:System.Activities.UnhandledExceptionAction.Abort>: Quando si verifica un'eccezione, informazioni sulla distribuzione di servizio viene scritto nell'archivio di istanze e l'istanza del flusso di lavoro viene scaricata dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="3240e-115"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Abort>: When an exception occurs, service deployment information is written to the instance store, and the workflow instance is unloaded from memory.</span></span> <span data-ttu-id="3240e-116">L'istanza del flusso di lavoro rimane in uno stato non persistente e non può essere ricaricata.</span><span class="sxs-lookup"><span data-stu-id="3240e-116">The workflow instance remains in a non-persisted state and cannot be reloaded.</span></span>  
  
    - <span data-ttu-id="3240e-117"><xref:System.Activities.UnhandledExceptionAction> è impostato su <xref:System.Activities.UnhandledExceptionAction.Cancel> o <xref:System.Activities.UnhandledExceptionAction.Terminate>: Quando si verifica un'eccezione, informazioni sulla distribuzione di servizio vengono scritte nell'archivio di istanze e lo stato dell'istanza attività è impostato su <xref:System.Activities.ActivityInstanceState.Closed>.</span><span class="sxs-lookup"><span data-stu-id="3240e-117"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Cancel> or <xref:System.Activities.UnhandledExceptionAction.Terminate>: When an exception occurs, service deployment information is written to the instance store, and the activity instance state is set to <xref:System.Activities.ActivityInstanceState.Closed>.</span></span>  
  
 <span data-ttu-id="3240e-118">Per ridurre il rischio di incontrare istanze del flusso di lavoro scaricate e non persistenti, si consiglia di rendere persistente il flusso di lavoro nelle fasi iniziali del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="3240e-118">To minimize the risk of encountering unloaded non-persisted workflow instances, we recommend persisting the workflow early in its life cycle.</span></span>  
  
## <a name="detection-and-removal-of-non-persisted-instances"></a><span data-ttu-id="3240e-119">Rilevamento e rimozione di istanze non persistenti</span><span class="sxs-lookup"><span data-stu-id="3240e-119">Detection and Removal of Non-Persisted Instances</span></span>  
 <span data-ttu-id="3240e-120"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> non rimuove alcuna istanza del flusso di lavoro non persistente dall'archivio di istanze</span><span class="sxs-lookup"><span data-stu-id="3240e-120">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> does not remove any non-persisted workflow instances from the instance store.</span></span> <span data-ttu-id="3240e-121">né rimuove alcun proprietario del blocco scaduto a cui sono associate istanze del flusso di lavoro non persistenti.</span><span class="sxs-lookup"><span data-stu-id="3240e-121">It also does not remove any expired lock owners that have non-persisted workflow instances associated with them.</span></span>  
  
 <span data-ttu-id="3240e-122">Si consiglia all'amministratore di verificare periodicamente nell'archivio di istanze la presenza di istanze non persistenti.</span><span class="sxs-lookup"><span data-stu-id="3240e-122">We recommend that the administrator periodically checks the instance store for non-persisted instances.</span></span> <span data-ttu-id="3240e-123">Gli amministratori possono rimuovere tali istanze dall'archivio finché sono certi che il flusso di lavoro specifico non riceverà messaggi correlati.</span><span class="sxs-lookup"><span data-stu-id="3240e-123">Administrators can remove those instances from the instance store as long as they know that this workflow will not receive correlated messages.</span></span> <span data-ttu-id="3240e-124">Ad esempio, se l'istanza è presente nel database da diversi mesi e si è a conoscenza che il flusso di lavoro ha in genere una durata di alcuni giorni, è possibile presupporre con sicurezza che si tratta di un'istanza non inizializzata che si era arrestata in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="3240e-124">For example, if the instance has been in the database for several months and it is known that the workflow typically has a lifetime of several days, it would be safe to assume that this was an initialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="3240e-125">Per trovare istanze non persistenti nell'archivio di istanze del flusso di lavoro di SQL, è possibile usare le query SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="3240e-125">To find non-persisted instances in the SQL Workflow Instance Store you can use the following SQL queries:</span></span>  
  
- <span data-ttu-id="3240e-126">Questa query trova tutte le istanze che non sono state rese persistenti e restituisce l'ID e l'ora di creazione (ora UTC) relativi.</span><span class="sxs-lookup"><span data-stu-id="3240e-126">This query finds all instances that have not been persisted, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0  
    ```  
  
- <span data-ttu-id="3240e-127">Questa query trova tutte le istanze che non sono state rese persistenti e che non sono caricate e restituisce l'ID e l'ora di creazione (ora UTC) relativi.</span><span class="sxs-lookup"><span data-stu-id="3240e-127">This query finds all instances that have not been persisted, and that are not loaded, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and CurrentMachine is NULL  
    ```  
  
- <span data-ttu-id="3240e-128">Questa query trova tutte le istanze sospese che non sono state rese persistenti e restituisce l'ID, l'ora di creazione (ora UTC), il motivo della sospensione e il nome dell'eccezione relativi.</span><span class="sxs-lookup"><span data-stu-id="3240e-128">This query finds all suspended instances that have not been persisted, and returns the ID, creation time (stored in UTC time), suspension reason, and exception name for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and IsSuspended = 1  
    ```  
  
 <span data-ttu-id="3240e-129">È necessario prestare attenzione quando si eliminano istanze non persistenti.</span><span class="sxs-lookup"><span data-stu-id="3240e-129">Use care when you are deleting non-persisted instances.</span></span> <span data-ttu-id="3240e-130">In generale, è consigliabile rimuovere le istanze non persistenti create da <xref:System.ServiceModel.Activities.WorkflowServiceHost> che sono sospese o non caricate.</span><span class="sxs-lookup"><span data-stu-id="3240e-130">In general, it is safe to remove non-persisted instances created by <xref:System.ServiceModel.Activities.WorkflowServiceHost> that are suspended or are not loaded.</span></span> <span data-ttu-id="3240e-131">Tali istanze specifiche possono essere eliminate dall'archivio rimuovendole dalla visualizzazione `[System.Activities.DurableInstancing].[Instances]` tramite il comando SQL seguente, sostituendo l'ID istanza corretto.</span><span class="sxs-lookup"><span data-stu-id="3240e-131">Those specific instances can be deleted from the store by deleting them from the `[System.Activities.DurableInstancing].[Instances]` view by using the following SQL command, substituting the correct instance ID.</span></span>  
  
```sql  
delete [System.Activities.DurableInstancing].[Instances]   
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’  
```  
  
> [!WARNING]
>  <span data-ttu-id="3240e-132">Non è consigliabile rimuovere tutte le istanze non persistenti perché potrebbero venire incluse istanze appena create non ancora rese persistenti.</span><span class="sxs-lookup"><span data-stu-id="3240e-132">We do not recommend removing all non-persisted instances because this includes instances that have just been created and have not yet been persisted.</span></span>
