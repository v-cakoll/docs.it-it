---
title: Utilizzo di WorkflowIdentity e controllo delle versioni
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 97224caa24b38a00a1cbb4fa76781eea3a10faaf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787921"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="93d6d-102">Utilizzo di WorkflowIdentity e controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="93d6d-102">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="93d6d-103"><xref:System.Activities.WorkflowIdentity> offre agli sviluppatori di applicazioni flusso di lavoro un modo per associare un nome e un elemento <xref:System.Version> a una definizione del flusso di lavoro. Consente inoltre di associare queste informazioni a un'istanza persistente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="93d6d-104">Queste informazioni di identità possono essere usate dagli sviluppatori di applicazioni flusso di lavoro per scenari quali l'esecuzione affiancata di più versioni di una definizione del flusso di lavoro e costituiscono un elemento fondamentale per altre funzionalità come l'aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="93d6d-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="93d6d-105">In questo argomento viene fornita una panoramica sull'utilizzo di <xref:System.Activities.WorkflowIdentity> con hosting <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="93d6d-106">Per informazioni sull'esecuzione affiancata delle definizioni del flusso di lavoro in un servizio del flusso di lavoro, vedere [controllo delle versioni side-by-side in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span><span class="sxs-lookup"><span data-stu-id="93d6d-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="93d6d-107">Per informazioni sull'aggiornamento dinamico, vedere [aggiornamento dinamico](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="93d6d-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="93d6d-108">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="93d6d-108">In this topic</span></span>

- [<span data-ttu-id="93d6d-109">Uso di WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="93d6d-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="93d6d-110">Esecuzione side-by-side con WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="93d6d-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="93d6d-111">Aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="93d6d-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="93d6d-112">Per aggiornare lo schema del database</span><span class="sxs-lookup"><span data-stu-id="93d6d-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a><span data-ttu-id="93d6d-113">Uso di WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="93d6d-113">Using WorkflowIdentity</span></span>

<span data-ttu-id="93d6d-114">Per usare <xref:System.Activities.WorkflowIdentity>, creare un'istanza, configurarla e associarla a un'istanza di <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="93d6d-115">L'istanza di <xref:System.Activities.WorkflowIdentity> contiene tre informazioni di identificazione.</span><span class="sxs-lookup"><span data-stu-id="93d6d-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="93d6d-116">Le proprietà <xref:System.Activities.WorkflowIdentity.Name%2A> e <xref:System.Activities.WorkflowIdentity.Version%2A> contengono un nome e un oggetto <xref:System.Version> e sono obbligatorie, mentre la proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e può essere usata per specificare una stringa aggiuntiva che contiene informazioni quali il nome dell'assembly o altre informazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="93d6d-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="93d6d-117">Un oggetto <xref:System.Activities.WorkflowIdentity> è univoco se una qualsiasi delle tre relative proprietà è diversa da un altro oggetto <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93d6d-118"><xref:System.Activities.WorkflowIdentity> non deve contenere eventuali informazioni identificabili personalmente (PII).</span><span class="sxs-lookup"><span data-stu-id="93d6d-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="93d6d-119">Le informazioni su <xref:System.Activities.WorkflowIdentity> usate per creare un'istanza vengono generate a tutti i servizi di rilevamento configurati in vari punti del ciclo di vita di attività dal runtime.</span><span class="sxs-lookup"><span data-stu-id="93d6d-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="93d6d-120">La verifica di WF non ha alcun meccanismo per nascondere i PII (dati riservati dell'utente).</span><span class="sxs-lookup"><span data-stu-id="93d6d-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="93d6d-121">Di conseguenza, un'istanza di <xref:System.Activities.WorkflowIdentity> non deve contenere dati di PII poiché verrebbe generata dal runtime nei record di rilevamento e può essere visibile agli utenti con accesso alla visualizzazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="93d6d-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="93d6d-122">Nell'esempio riportato di seguito, un oggetto <xref:System.Activities.WorkflowIdentity> viene creato e associato a un'istanza di un flusso di lavoro creato usando una definizione del flusso di lavoro di `MortgageWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="93d6d-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="93d6d-123">Quando un flusso di lavoro viene nuovamente caricato e ripreso, è necessario usare un oggetto <xref:System.Activities.WorkflowIdentity> configurato per corrispondere all'oggetto <xref:System.Activities.WorkflowIdentity> dell'istanza persistente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="93d6d-124">Se l'oggetto <xref:System.Activities.WorkflowIdentity> usato durante la ricarica dell'istanza del flusso di lavoro non corrisponde l'oggetto <xref:System.Activities.WorkflowIdentity> persistente, viene generata un'eccezione <xref:System.Activities.VersionMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="93d6d-125">Nell'esempio riportato di seguito viene effettuato un tentativo di caricamento dell'istanza di `MortgageWorkflow` che è stata resa persistente nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="93d6d-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="93d6d-126">Questo tentativo di caricamento viene eseguito mediante <xref:System.Activities.WorkflowIdentity> configurato per una versione più recente del flusso di lavoro relativo a un'ipoteca che non corrisponde all'istanza persistente.</span><span class="sxs-lookup"><span data-stu-id="93d6d-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="93d6d-127">Quando viene eseguito il codice precedente, viene generata la seguente eccezione <xref:System.Activities.VersionMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```output
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a><span data-ttu-id="93d6d-128">Esecuzione side-by-side con WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="93d6d-128">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="93d6d-129"><xref:System.Activities.WorkflowIdentity> può essere usato per facilitare l'esecuzione di più versioni di un flusso di lavoro affiancate.</span><span class="sxs-lookup"><span data-stu-id="93d6d-129"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="93d6d-130">Uno scenario comune consiste nella modifica dei requisiti aziendali in un flusso di lavoro di lunga durata.</span><span class="sxs-lookup"><span data-stu-id="93d6d-130">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="93d6d-131">Molte istanze di un flusso di lavoro potrebbero essere in esecuzione quando una versione aggiornata viene distribuita.</span><span class="sxs-lookup"><span data-stu-id="93d6d-131">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="93d6d-132">L'applicazione host può essere configurata per usare la definizione aggiornata del flusso di lavoro all'avvio di nuove istanze. È responsabilità dell'applicazione host fornire la definizione del flusso di lavoro corretta quando vengono riprese le istanze.</span><span class="sxs-lookup"><span data-stu-id="93d6d-132">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="93d6d-133"><xref:System.Activities.WorkflowIdentity> può essere usato per identificare e fornire la definizione corrispondente del flusso di lavoro quando vengono riprese le istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-133"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="93d6d-134">Per recuperare l'oggetto <xref:System.Activities.WorkflowIdentity> di un'istanza persistente del flusso di lavoro, viene usato il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-134">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="93d6d-135">Il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A> accetta l'oggetto <xref:System.Activities.WorkflowApplication.Id%2A> dell'istanza persistente del flusso di lavoro e l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> contenente l'istanza persistente e restituisce un oggetto <xref:System.Activities.WorkflowApplicationInstance>.</span><span class="sxs-lookup"><span data-stu-id="93d6d-135">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="93d6d-136">Un oggetto <xref:System.Activities.WorkflowApplicationInstance> contiene informazioni su un'istanza persistente del flusso di lavoro, incluso il relativo oggetto <xref:System.Activities.WorkflowIdentity> associato.</span><span class="sxs-lookup"><span data-stu-id="93d6d-136">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="93d6d-137">Questo oggetto <xref:System.Activities.WorkflowIdentity> associato può essere usato dall'host per fornire la definizione del flusso di lavoro corretta durante il caricamento e la ripresa dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-137">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="93d6d-138">Un oggetto <xref:System.Activities.WorkflowIdentity> null è valido e può essere usato dall'host per eseguire il mapping delle istanze che sono state salvate in modo permanente senza alcun <xref:System.Activities.WorkflowIdentity> associato alla definizione appropriata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-138">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="93d6d-139">Questo scenario può verificarsi quando un'applicazione flusso di lavoro non è stata inizialmente scritta con il controllo delle versioni del flusso di lavoro o quando un'applicazione viene aggiornata da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="93d6d-139">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from .NET Framework 4.</span></span> <span data-ttu-id="93d6d-140">Per ulteriori informazioni, vedere [aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span><span class="sxs-lookup"><span data-stu-id="93d6d-140">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="93d6d-141">Nell'esempio seguente viene utilizzato un `Dictionary<WorkflowIdentity, Activity>` per associare <xref:System.Activities.WorkflowIdentity> istanze con le relative definizioni del flusso di lavoro corrispondenti e viene avviato un flusso di lavoro utilizzando la definizione del flusso di lavoro `MortgageWorkflow`, associata alla <xref:System.Activities.WorkflowIdentity>`identityV1`.</span><span class="sxs-lookup"><span data-stu-id="93d6d-141">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="93d6d-142">Nell'esempio riportato di seguito, le informazioni sull'istanza persistente del flusso di lavoro derivante dall'esempio precedente vengono recuperate chiamando il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A>; le informazioni relative all'oggetto <xref:System.Activities.WorkflowIdentity> persistente vengono usate per recuperare la definizione corrispondente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-142">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="93d6d-143">Queste informazioni vengono usate per configurare <xref:System.Activities.WorkflowApplication>, quindi il flusso di lavoro viene caricato.</span><span class="sxs-lookup"><span data-stu-id="93d6d-143">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="93d6d-144">Si noti che dal momento che viene usato l'overload <xref:System.Activities.WorkflowApplication.Load%2A> che accetta <xref:System.Activities.WorkflowApplicationInstance>, l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che era configurato nell'oggetto <xref:System.Activities.WorkflowApplicationInstance> viene usato da <xref:System.Activities.WorkflowApplication>, di conseguenza la relativa proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> non necessita di configurazione.</span><span class="sxs-lookup"><span data-stu-id="93d6d-144">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
> <span data-ttu-id="93d6d-145">Se la proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> è impostata, deve essere impostata con la stessa istanza di <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usata da <xref:System.Activities.WorkflowApplicationInstance>, altrimenti verrà generata un'eccezione <xref:System.ArgumentException> con il messaggio seguente: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span><span class="sxs-lookup"><span data-stu-id="93d6d-145">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="UpdatingWF4PersistenceDatabases"></a><span data-ttu-id="93d6d-146">Aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="93d6d-146">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="93d6d-147">Viene fornito uno script di database SqlWorkflowInstanceStoreSchemaUpgrade. SQL per aggiornare i database di persistenza creati usando gli script di database .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="93d6d-147">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts.</span></span> <span data-ttu-id="93d6d-148">Questo script aggiorna i database per supportare le nuove funzionalità di controllo delle versioni introdotte in .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="93d6d-148">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="93d6d-149">Le istanze persistenti del flusso di lavoro nei database sono valori predefiniti specificati per il controllo delle versioni e quindi possono partecipare all'esecuzione side-by-side e all'aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="93d6d-149">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="93d6d-150">Se un'applicazione flusso di lavoro .NET Framework 4,5 tenta di eseguire qualsiasi operazione di persistenza che utilizza le nuove funzionalità di controllo delle versioni in un database di persistenza che non è stato aggiornato utilizzando lo script fornito, viene generata un'<xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> con un messaggio simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="93d6d-150">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```output
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a><span data-ttu-id="93d6d-151">Per aggiornare lo schema del database</span><span class="sxs-lookup"><span data-stu-id="93d6d-151">To upgrade the database schema</span></span>

1. <span data-ttu-id="93d6d-152">Aprire SQL Server Management Studio e connettersi al server di database di persistenza, ad esempio **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="93d6d-152">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="93d6d-153">Scegliere **Apri**dal **menu** **file** .</span><span class="sxs-lookup"><span data-stu-id="93d6d-153">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="93d6d-154">Passare alla cartella seguente: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="93d6d-154">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="93d6d-155">Selezionare **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="93d6d-155">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="93d6d-156">Selezionare il nome del database di persistenza nell'elenco a discesa **database disponibili** .</span><span class="sxs-lookup"><span data-stu-id="93d6d-156">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="93d6d-157">Scegliere **Esegui** dal menu **query** .</span><span class="sxs-lookup"><span data-stu-id="93d6d-157">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="93d6d-158">Quando la query viene completata, lo schema di database verrà aggiornato e, se necessario, è possibile visualizzare l'identità predefinita del flusso di lavoro assegnata alle istanze persistenti del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="93d6d-158">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="93d6d-159">Espandere il database di persistenza nel nodo **database** del **Esplora oggetti**, quindi espandere il nodo **visualizzazioni** .</span><span class="sxs-lookup"><span data-stu-id="93d6d-159">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="93d6d-160">Fare clic con il pulsante destro del mouse su **System. Activities. DurableInstancing. Instances** e scegliere **seleziona le prime 1000 righe**.</span><span class="sxs-lookup"><span data-stu-id="93d6d-160">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="93d6d-161">Scorrere fino alla fine delle colonne. si noti che alla vista sono state aggiunte sei colonne aggiuntive: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **minor**e **Revision**.</span><span class="sxs-lookup"><span data-stu-id="93d6d-161">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="93d6d-162">Tutti i flussi di lavoro salvati avranno un valore **null** per questi campi, che rappresenta un'identità del flusso di lavoro null.</span><span class="sxs-lookup"><span data-stu-id="93d6d-162">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
