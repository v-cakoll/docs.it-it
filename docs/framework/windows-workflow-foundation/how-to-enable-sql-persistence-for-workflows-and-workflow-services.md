---
title: 'Procedura: abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi'
ms.date: 03/30/2017
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: bbbd2e6a5eb3babeb1a4d06976fdefd621581766
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837688"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="315fe-102">Procedura: abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi</span><span class="sxs-lookup"><span data-stu-id="315fe-102">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="315fe-103">In questo argomento viene descritto come configurare la funzionalità di archivio di istanze del flusso di lavoro SQL per abilitare la persistenza per i flussi di lavoro e i relativi servizi sia a livello di codice sia tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for your workflows and workflow services both programmatically and by using a configuration file.</span></span>

<span data-ttu-id="315fe-104">Windows Server AppFabric semplifica il processo di configurazione della persistenza.</span><span class="sxs-lookup"><span data-stu-id="315fe-104">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="315fe-105">Per altre informazioni, vedere [configurazione di persistenza di App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee790848(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="315fe-105">For more information, see [App Fabric Persistence Configuration](https://docs.microsoft.com/previous-versions/appfabric/ee790848(v=azure.10)).</span></span>

<span data-ttu-id="315fe-106">Prima di usare tale funzionalità, creare un database usato dalla funzionalità per rendere persistenti le istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-106">Before using the SQL Workflow Instance Store feature, create a database that the feature uses to persist workflow instances.</span></span> <span data-ttu-id="315fe-107">Il programma di installazione di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] copia i file di script SQL associati alla funzionalità di archivio di istanze del flusso di lavoro SQL nella cartella %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN.</span><span class="sxs-lookup"><span data-stu-id="315fe-107">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] set-up program copies SQL script files associated with the SQL Workflow Instance Store feature to the %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN folder.</span></span> <span data-ttu-id="315fe-108">Eseguire questi file di script in un database di SQL Server 2005 o SQL Server 2008 che si desidera venga usato dall'archivio di istanze del flusso di lavoro SQL per rendere persistenti le istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-108">Run these script files against a SQL Server 2005 or SQL Server 2008 database that you want the SQL Workflow Instance Store to use to persist workflow instances.</span></span> <span data-ttu-id="315fe-109">Eseguire innanzitutto il file SqlWorkflowInstanceStoreSchema.sql, quindi il file SqlWorkflowInstanceStoreLogic.sql.</span><span class="sxs-lookup"><span data-stu-id="315fe-109">Run the SqlWorkflowInstanceStoreSchema.sql file first and then run the SqlWorkflowInstanceStoreLogic.sql file.</span></span>

> [!NOTE]
> <span data-ttu-id="315fe-110">Per pulire il database di persistenza per avere un database aggiornato, eseguire gli script in %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN nell'ordine seguente.</span><span class="sxs-lookup"><span data-stu-id="315fe-110">To clean up the persistence database to have a fresh database, run the scripts in %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN in the following order.</span></span>
>
> 1. <span data-ttu-id="315fe-111">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="315fe-111">SqlWorkflowInstanceStoreSchema.sql</span></span>
> 2. <span data-ttu-id="315fe-112">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="315fe-112">SqlWorkflowInstanceStoreLogic.sql</span></span>

> [!IMPORTANT]
> <span data-ttu-id="315fe-113">Se non si crea un database di persistenza, la funzionalità di archivio di istanze del flusso di lavoro SQL genera un'eccezione simile alla seguente quando un host tenta di rendere persistenti i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-113">If you do not create a persistence database, the SQL Workflow Instance Store feature throws an exception similar to the following one when a host tries to persist workflows.</span></span>
>
> <span data-ttu-id="315fe-114">System.Data.SqlClient.SqlException: Impossibile trovare la stored procedure 'System.Activities.DurableInstancing.CreateLockOwner'</span><span class="sxs-lookup"><span data-stu-id="315fe-114">System.Data.SqlClient.SqlException: Could not find stored procedure 'System.Activities.DurableInstancing.CreateLockOwner'</span></span>

<span data-ttu-id="315fe-115">Nelle sezioni seguenti viene descritto come abilitare la persistenza per i flussi di lavoro e i relativi servizi usando l'archivio di istanze del flusso di lavoro SQL.</span><span class="sxs-lookup"><span data-stu-id="315fe-115">The following sections describe how to enable persistence for workflows and workflow services using the SQL Workflow Instance Store.</span></span> <span data-ttu-id="315fe-116">Per ulteriori informazioni sulle proprietà dell'archivio di istanze del flusso di lavoro SQL, vedere [proprietà dell'archivio di istanze del flusso di lavoro SQL](properties-of-sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="315fe-116">For more information about properties of the SQL Workflow Instance Store, see [Properties of SQL Workflow Instance Store](properties-of-sql-workflow-instance-store.md).</span></span>

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a><span data-ttu-id="315fe-117">Abilitazione della persistenza per i flussi di lavoro indipendenti che usano l'oggetto WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="315fe-117">Enabling Persistence for Self-Hosted Workflows that use WorkflowApplication</span></span>

<span data-ttu-id="315fe-118">È possibile abilitare la persistenza per i flussi di lavoro indipendenti che usano l'oggetto <xref:System.Activities.WorkflowApplication> a livello di codice tramite il modello a oggetti <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="315fe-118">You can enable persistence for self-hosted workflows that use <xref:System.Activities.WorkflowApplication> programmatically by using the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> object model.</span></span> <span data-ttu-id="315fe-119">Nella procedura seguente sono inclusi i passaggi per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-119">The following procedure contains steps to do this.</span></span>

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a><span data-ttu-id="315fe-120">Per abilitare la persistenza per i flussi di lavoro indipendenti</span><span class="sxs-lookup"><span data-stu-id="315fe-120">To enable persistence for self-hosted workflows</span></span>

1. <span data-ttu-id="315fe-121">Aggiungere un riferimento a System. Activities. DurableInstancing. dll.</span><span class="sxs-lookup"><span data-stu-id="315fe-121">Add a reference to System.Activities.DurableInstancing.dll.</span></span>

2. <span data-ttu-id="315fe-122">Aggiungere l'istruzione seguente all'inizio del file di origine dopo le istruzioni "using" esistenti.</span><span class="sxs-lookup"><span data-stu-id="315fe-122">Add the following statement at the top of the source file after the existing "using" statements.</span></span>

    ```csharp
    using System.Activities.DurableInstancing;
    ```

3. <span data-ttu-id="315fe-123">Costruire un oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> e assegnarlo alla proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> dell'oggetto <xref:System.Activities.WorkflowApplication> come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="315fe-123">Construct a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> and assign it to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> of the <xref:System.Activities.WorkflowApplication> as shown in the following code example.</span></span>

    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```

   > [!NOTE]
   > <span data-ttu-id="315fe-124">Il nome del server della stringa di connessione potrebbe essere diverso a seconda dell'edizione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="315fe-124">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

4. <span data-ttu-id="315fe-125">Richiamare il metodo <xref:System.Activities.WorkflowApplication.Persist%2A> sull'oggetto <xref:System.Activities.WorkflowApplication> per rendere persistente un flusso di lavoro o il metodo <xref:System.Activities.WorkflowApplication.Unload%2A> per rendere persistente e scaricare un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-125">Invoke the <xref:System.Activities.WorkflowApplication.Persist%2A> method on the <xref:System.Activities.WorkflowApplication> object to persist a workflow, or <xref:System.Activities.WorkflowApplication.Unload%2A> method to persist and unload a workflow.</span></span> <span data-ttu-id="315fe-126">È anche possibile gestire l'evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> generato dall'oggetto <xref:System.Activities.WorkflowApplication> e restituire il membro (<xref:System.Activities.PersistableIdleAction.Persist> o <xref:System.Activities.PersistableIdleAction.Unload>) appropriato dell'oggetto <xref:System.Activities.PersistableIdleAction>.</span><span class="sxs-lookup"><span data-stu-id="315fe-126">You can also handle the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> event raised by the <xref:System.Activities.WorkflowApplication> object and return appropriate (<xref:System.Activities.PersistableIdleAction.Persist> or <xref:System.Activities.PersistableIdleAction.Unload>) member of <xref:System.Activities.PersistableIdleAction>.</span></span>

   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> <span data-ttu-id="315fe-127">Per istruzioni dettagliate, vedere [procedura: creare ed eseguire un flusso di lavoro con esecuzione prolungata](how-to-create-and-run-a-long-running-workflow.md) dell' [esercitazione Introduzione](getting-started-tutorial.md) .</span><span class="sxs-lookup"><span data-stu-id="315fe-127">See the [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md) step of the [Getting Started Tutorial](getting-started-tutorial.md) for step by step instructions.</span></span>

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a><span data-ttu-id="315fe-128">Abilitazione della persistenza per i servizi flussi di lavoro indipendenti che usano l'oggetto WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="315fe-128">Enabling Persistence for Self-Hosted Workflow Services that use the WorkflowServiceHost</span></span>

<span data-ttu-id="315fe-129">È possibile abilitare la persistenza per i servizi flussi di lavoro indipendenti che usano l'oggetto <xref:System.ServiceModel.WorkflowServiceHost> a livello di codice tramite la classe <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> o <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.</span><span class="sxs-lookup"><span data-stu-id="315fe-129">You can enable persistence for self-hosted workflow services that use <xref:System.ServiceModel.WorkflowServiceHost> programmatically by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class or the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> class.</span></span>

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a><span data-ttu-id="315fe-130">Utilizzo della classe SqlWorkflowInstanceStoreBehavior</span><span class="sxs-lookup"><span data-stu-id="315fe-130">Using the SqlWorkflowInstanceStoreBehavior Class</span></span>

<span data-ttu-id="315fe-131">Nella procedura seguente sono contenuti i passaggi per usare la classe <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> al fine di abilitare la persistenza per i servizi flussi di lavoro indipendenti.</span><span class="sxs-lookup"><span data-stu-id="315fe-131">The following procedure contains steps to use the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class to enable persistence for self-hosted workflow services.</span></span>

#### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a><span data-ttu-id="315fe-132">Per abilitare la persistenza tramite l'oggetto SqlWorkflowInstanceStoreBehavior</span><span class="sxs-lookup"><span data-stu-id="315fe-132">To enable persistence using SqlWorkflowInstanceStoreBehavior</span></span>

1. <span data-ttu-id="315fe-133">Aggiungere un riferimento a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="315fe-133">Add a reference to the System.ServiceModel.dll.</span></span>

2. <span data-ttu-id="315fe-134">Aggiungere l'istruzione seguente all'inizio del file di origine dopo le istruzioni "using" esistenti.</span><span class="sxs-lookup"><span data-stu-id="315fe-134">Add the following statement at the top of the source file after the existing "using" statements.</span></span>

    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3. <span data-ttu-id="315fe-135">Creare un'istanza dell'oggetto `WorkflowServiceHost` e aggiungere gli endpoint per il servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-135">Create an instance of the `WorkflowServiceHost` and add endpoints for the workflow service.</span></span>

    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");
    ```

4. <span data-ttu-id="315fe-136">Costruire un oggetto `SqlWorkflowInstanceStoreBehavior` e impostare le proprietà dell'oggetto di comportamento.</span><span class="sxs-lookup"><span data-stu-id="315fe-136">Construct a `SqlWorkflowInstanceStoreBehavior` object and to set properties of the behavior object.</span></span>

    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5. <span data-ttu-id="315fe-137">Aprire l'host del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="315fe-137">Open the workflow service host.</span></span>

    ```csharp
    host.Open();
    ```

### <a name="using-the-durableinstancingoptions-property"></a><span data-ttu-id="315fe-138">Utilizzo della proprietà DurableInstancingOptions</span><span class="sxs-lookup"><span data-stu-id="315fe-138">Using the DurableInstancingOptions Property</span></span>

<span data-ttu-id="315fe-139">Quando l'oggetto `SqlWorkflowInstanceStoreBehavior` è applicato, l'oggetto `DurableInstancingOptions.InstanceStore` in `WorkflowServiceHost` viene impostato sull'oggetto `SqlWorkflowInstanceStore` creato usando i valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-139">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="315fe-140">Tale operazione può essere eseguita anche a livello di codice per impostare la proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> dell'oggetto `WorkflowServiceHost` senza usare la classe `SqlWorkflowInstanceStoreBehavior` come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="315fe-140">You can do the same programmatically to set the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> property of the `WorkflowServiceHost` without using the `SqlWorkflowInstanceStoreBehavior` class as shown in the following code example.</span></span>

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a><span data-ttu-id="315fe-141">Abilitazione della persistenza per i servizi flussi di lavoro ospitati nel servizio WAS che usano l'oggetto WorkflowServiceHost tramite un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="315fe-141">Enabling Persistence for WAS-Hosted Workflow Services that use the WorkflowServiceHost using a Configuration File</span></span>

<span data-ttu-id="315fe-142">È possibile abilitare la persistenza per i servizi flussi di lavori indipendenti oppure ospitati nel servizio WAS tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-142">You can enable persistence for self-hosted or Windows Process Activation Service (WAS)-hosted workflow services by using a configuration file.</span></span> <span data-ttu-id="315fe-143">Un servizio flusso di lavoro ospitato nel servizio WAS usa l'oggetto WorkflowServiceHost come servizi flussi di lavoro indipendenti.</span><span class="sxs-lookup"><span data-stu-id="315fe-143">A WAS-hosted workflow service uses the WorkflowServiceHost as the self-hosted workflow services do.</span></span>

<span data-ttu-id="315fe-144">Il `SqlWorkflowInstanceStoreBehavior`, un comportamento del servizio che consente di modificare facilmente le proprietà dell' [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md) tramite la configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="315fe-144">The `SqlWorkflowInstanceStoreBehavior`, a service behavior that allows you to conveniently change the [SQL Workflow Instance Store](sql-workflow-instance-store.md) properties through XML configuration.</span></span> <span data-ttu-id="315fe-145">Per i servizi flussi di lavoro ospitati nel servizio WAS, usare il file Web.config.</span><span class="sxs-lookup"><span data-stu-id="315fe-145">For WAS-hosted workflow services, use the Web.config file.</span></span> <span data-ttu-id="315fe-146">Nell'esempio di configurazione seguente viene mostrato come configurare l'archivio di istanze del flusso di lavoro SQL tramite l'elemento del comportamento `sqlWorkflowInstanceStore` in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-146">The following configuration example shows how to configure the SQL Workflow Instance Store by using the `sqlWorkflowInstanceStore` behavior element in a configuration file.</span></span>

```xml
<serviceBehaviors>
    <behavior name="">
        <sqlWorkflowInstanceStore
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"
                    instanceEncodingOption="GZip | None"
                    instanceCompletionAction="DeleteAll | DeleteNothing"
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"
                    hostLockRenewalPeriod="00:00:30"
                    runnableInstancesDetectionPeriod="00:00:05" />

    </behavior>
</serviceBehaviors>
```

<span data-ttu-id="315fe-147">Se non si impostano i valori per la proprietà `connectionString` o `connectionStringName`, l'archivio di istanze del flusso di lavoro SQL usa la stringa di connessione predefinita denominata `DefaultSqlWorkflowInstanceStoreConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="315fe-147">If you do not set values for the `connectionString` or the `connectionStringName` property, the SQL Workflow Instance Store uses the default named connection string `DefaultSqlWorkflowInstanceStoreConnectionString`.</span></span>

<span data-ttu-id="315fe-148">Quando l'oggetto `SqlWorkflowInstanceStoreBehavior` è applicato, l'oggetto `DurableInstancingOptions.InstanceStore` in `WorkflowServiceHost` viene impostato sull'oggetto `SqlWorkflowInstanceStore` creato usando i valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="315fe-148">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="315fe-149">Tale operazione può essere eseguita anche a livello di codice per usare l'oggetto `SqlWorkflowInstanceStore` con l'oggetto `WorkflowServiceHost` senza usare l'elemento del comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="315fe-149">You can do the same programmatically to use the `SqlWorkflowInstanceStore` with `WorkflowServiceHost` without using the service behavior element.</span></span>

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

> [!IMPORTANT]
> <span data-ttu-id="315fe-150">È consigliabile non archiviare nel file Web.config informazioni riservate, quali nomi utente e password.</span><span class="sxs-lookup"><span data-stu-id="315fe-150">It is recommended that you do not store sensitive information such as user names and passwords in the Web.config file.</span></span> <span data-ttu-id="315fe-151">In caso contrario, è necessario proteggere l'accesso a tale file tramite gli elenchi di controllo di accesso (ACL) del file system.</span><span class="sxs-lookup"><span data-stu-id="315fe-151">If you do store sensitive information in the Web.config file, you should secure access to the Web.config file by using file system Access Control Lists (ACLs).</span></span> <span data-ttu-id="315fe-152">Inoltre, è possibile proteggere i valori di configurazione all'interno di un file di configurazione come indicato in [crittografia delle informazioni di configurazione tramite la configurazione protetta](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="315fe-152">In addition, you can also secure the configuration values within a configuration file as mentioned in [Encrypting Configuration Information Using Protected Configuration](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100)).</span></span>

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a><span data-ttu-id="315fe-153">Elementi Machine.config correlati alla funzionalità di archivio di istanze del flusso di lavoro SQL</span><span class="sxs-lookup"><span data-stu-id="315fe-153">Machine.config Elements Related to the SQL Workflow Instance Store Feature</span></span>

<span data-ttu-id="315fe-154">L'installazione di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] comporta l'aggiunta degli elementi seguenti correlati alla funzionalità di archivio di istanze del flusso di lavoro SQL al file Machine.config:</span><span class="sxs-lookup"><span data-stu-id="315fe-154">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] installation adds the following elements related to the SQL Workflow Instance Store feature to the Machine.config file:</span></span>

- <span data-ttu-id="315fe-155">Aggiunge il seguente elemento di estensione del comportamento al file Machine. config in modo da poter utilizzare l'elemento del comportamento del servizio \<sqlWorkflowInstanceStore > nel file di configurazione per configurare la persistenza per i servizi.</span><span class="sxs-lookup"><span data-stu-id="315fe-155">Adds the following behavior extension element to the Machine.config file so that you can use the \<sqlWorkflowInstanceStore> service behavior element in the configuration file to configure persistence for your services.</span></span>

    ```xml
    <configuration>
        <system.serviceModel>
            <extensions>
                <behaviorExtensions>
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                </behaviorExtensions>
            </extensions>
        </system.serviceModel>
    </configuration>
    ```
