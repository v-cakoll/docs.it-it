---
title: Persistenza del flusso di lavoro
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2278762895978f90d80977f9e538b0e10a4f3f8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-persistence"></a><span data-ttu-id="27769-102">Persistenza del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="27769-102">Workflow Persistence</span></span>
<span data-ttu-id="27769-103">La persistenza del flusso di lavoro è l'acquisizione durevole di uno stato di un'istanza del flusso di lavoro, indipendentemente dalle informazioni relative al processo o al computer.</span><span class="sxs-lookup"><span data-stu-id="27769-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="27769-104">In questo modo viene fornito un punto noto di ripristino dell'istanza del flusso di lavoro in caso di errore di sistema o viene conservata memoria scaricando istanze del flusso di lavoro il cui funzionamento non viene eseguito in modo attivo o ancora viene spostato lo stato dell'istanza del flusso di lavoro da un nodo a un altro in una server farm.</span><span class="sxs-lookup"><span data-stu-id="27769-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="27769-105">La persistenza abilita agilità di processo, scalabilità, ripristino nonostante errori e la possibilità di gestire la memoria in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="27769-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="27769-106">Il processo di persistenza include l'identificazione di un punto di persistenza, la raccolta dei dati da salvare e infine la delega dell'archiviazione effettiva dei dati a un provider di persistenza.</span><span class="sxs-lookup"><span data-stu-id="27769-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="27769-107">Per abilitare la persistenza per un flusso di lavoro, è necessario associare un archivio di istanze con il **WorkflowApplication** o **WorkflowServiceHost** come indicato nella [procedura: abilitare la persistenza per Flussi di lavoro e i servizi flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="27769-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="27769-108">Il **WorkflowApplication** e **WorkflowServiceHost** utilizzare l'archivio di istanze associata per consentire di rendere persistenti le istanze del flusso di lavoro in un archivio di persistenza e il caricamento di istanze del flusso di lavoro in memoria in base ai dati di istanza del flusso di lavoro archiviati nell'archivio di persistenza.</span><span class="sxs-lookup"><span data-stu-id="27769-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="27769-109">Il [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] viene fornito con il **SqlWorkflowInstanceStore** (classe), che consente la persistenza dei dati e i metadati relativi a istanze di flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="27769-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="27769-110">Vedere [archivio di istanze del flusso di lavoro SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="27769-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="27769-111">Per archiviare e caricare i dati specifici dell'applicazione insieme alle informazioni correlate all'istanza del flusso di lavoro, è possibile creare partecipanti di persistenza che estendono la classe <xref:System.Activities.Persistence.PersistenceParticipant>.</span><span class="sxs-lookup"><span data-stu-id="27769-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="27769-112">Un partecipante di persistenza fa parte del processo di persistenza per salvare dati serializzabili personalizzati nell'archivio di persistenza, per caricare i dati dall'archivio di istanze in memoria ed eseguire qualsiasi logica aggiuntiva in una transazione di persistenza.</span><span class="sxs-lookup"><span data-stu-id="27769-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="27769-113">Per ulteriori informazioni, vedere [i partecipanti di persistenza](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span><span class="sxs-lookup"><span data-stu-id="27769-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="27769-114">Windows Server AppFabric semplifica il processo di configurazione della persistenza.</span><span class="sxs-lookup"><span data-stu-id="27769-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="27769-115">Per altre informazioni, vedere [concetti di persistenza con Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="27769-115">For more information, see [Persistence Concepts with Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="27769-116">Punti di persistenza impliciti</span><span class="sxs-lookup"><span data-stu-id="27769-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="27769-117">Nell'elenco seguente sono contenuti esempi di condizioni in base alle quali un flusso di lavoro viene reso persistente quando un archivio di istanze è associato a un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27769-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="27769-118">Quando un **TransactionScope** al completamento dell'attività o un **TransactedReceiveScope** al completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="27769-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="27769-119">Quando un'istanza del flusso di lavoro diventa inattiva e **WorkflowIdleBehavior** viene impostato sull'host del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27769-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="27769-120">Ciò si verifica, ad esempio, quando si usano attività di messaggistica o **ritardo** attività.</span><span class="sxs-lookup"><span data-stu-id="27769-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="27769-121">Quando WorkflowApplication diventa inattivo e **PersistableIdle** dell'applicazione è impostata su **Persistableidleaction**.</span><span class="sxs-lookup"><span data-stu-id="27769-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="27769-122">Quando a un'applicazione host viene richiesto di rendere persistente o scaricare un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="27769-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="27769-123">Quando un'istanza del flusso di lavoro viene terminata o termina.</span><span class="sxs-lookup"><span data-stu-id="27769-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="27769-124">Quando un **Persist** attività viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="27769-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="27769-125">Quando un'istanza di un flusso di lavoro sviluppata usando una versione precedente di Windows Workflow Foundation incontra un punto di persistenza durante l'esecuzione interoperativa.</span><span class="sxs-lookup"><span data-stu-id="27769-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27769-126">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="27769-126">In This Section</span></span>  
  
-   [<span data-ttu-id="27769-127">Archivio di istanze del flusso di lavoro SQL</span><span class="sxs-lookup"><span data-stu-id="27769-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="27769-128">Archivi di istanze</span><span class="sxs-lookup"><span data-stu-id="27769-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="27769-129">Partecipanti di persistenza</span><span class="sxs-lookup"><span data-stu-id="27769-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="27769-130">Procedure consigliate per la persistenza</span><span class="sxs-lookup"><span data-stu-id="27769-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="27769-131">Istanze del flusso di lavoro non persistenti</span><span class="sxs-lookup"><span data-stu-id="27769-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="27769-132">Sospensione e ripresa di un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="27769-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
