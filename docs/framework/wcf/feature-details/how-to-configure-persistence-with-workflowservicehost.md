---
title: 'Procedura: configurare la persistenza con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 4ed9c76f091e75cf6ba7658f0314d2e21bbe962e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599113"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="c71ce-102">Procedura: configurare la persistenza con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="c71ce-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="c71ce-103">In questo argomento viene descritto come configurare la funzionalità di archivio di istanze del flusso di lavoro SQL per abilitare la persistenza per i flussi di lavoro ospitati in <xref:System.ServiceModel.Activities.WorkflowServiceHost> tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c71ce-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="c71ce-104">Prima di usare tale funzionalità è necessario creare un database SQL usato per rendere persistenti le istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c71ce-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="c71ce-105">Per altre informazioni, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="c71ce-106">Per configurare l'archivio di istanze del flusso di lavoro SQL nella configurazione</span><span class="sxs-lookup"><span data-stu-id="c71ce-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="c71ce-107">È possibile configurare le proprietà dell'archivio di istanze del flusso di lavoro SQL mediante <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamento del servizio che consente di modificare le impostazioni tramite la configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="c71ce-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="c71ce-108">Nell'esempio di configurazione seguente viene illustrato come configurare l'archivio di istanze del flusso di lavoro SQL utilizzando l' `sqlWorkflowInstanceStore` elemento <> Behavior in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c71ce-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="c71ce-109">Per ulteriori informazioni su come configurare l'archivio di istanze del flusso di lavoro SQL, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="c71ce-110">Per ulteriori informazioni sulle singole impostazioni per l'elemento <`sqlWorkflowInstanceStore`> Behavior, vedere l' [Archivio di istanze del flusso di lavoro SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="c71ce-111">Windows Server App Fabric fornisce un archivio di persistenza specifico.</span><span class="sxs-lookup"><span data-stu-id="c71ce-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="c71ce-112">Per altre informazioni, vedere [persistenza di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))AppFabric.</span><span class="sxs-lookup"><span data-stu-id="c71ce-112">For more information, see [Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c71ce-113">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="c71ce-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="c71ce-114">Per altre informazioni, vedere [Configurazione semplificata](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="c71ce-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="c71ce-115">Per configurare l'archivio di istanze del flusso di lavoro SQL nel codice</span><span class="sxs-lookup"><span data-stu-id="c71ce-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="c71ce-116">È possibile configurare le proprietà dell'archivio di istanze del flusso di lavoro SQL mediante <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamento del servizio che consente di modificare le impostazioni tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="c71ce-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="c71ce-117">Nell'esempio seguente viene mostrato come configurare l'archivio di istanze del flusso di lavoro SQL tramite l'elemento del comportamento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> nel codice.</span><span class="sxs-lookup"><span data-stu-id="c71ce-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="c71ce-118">Per ulteriori informazioni su come configurare l'archivio di istanze del flusso di lavoro SQL, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="c71ce-119">Per ulteriori informazioni sulle singole impostazioni per l' <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento del comportamento, vedere l' [Archivio di istanze del flusso di lavoro SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="c71ce-120">Windows Server App Fabric fornisce un archivio di persistenza specifico.</span><span class="sxs-lookup"><span data-stu-id="c71ce-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="c71ce-121">Per altre informazioni, vedere [persistenza di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))AppFabric.</span><span class="sxs-lookup"><span data-stu-id="c71ce-121">For more information, see [Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c71ce-122">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="c71ce-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="c71ce-123">Per altre informazioni, vedere [Configurazione semplificata](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="c71ce-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="c71ce-124">Per un esempio di come configurare la persistenza a livello di codice, vedere [procedura: abilitare la persistenza per i flussi di lavoro e i servizi flusso di lavoro](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="c71ce-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71ce-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c71ce-125">See also</span></span>

- [<span data-ttu-id="c71ce-126">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c71ce-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="c71ce-127">Persistenza del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c71ce-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="c71ce-128">[Persistenza di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c71ce-128">[Windows Server App Fabric Persistence](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
