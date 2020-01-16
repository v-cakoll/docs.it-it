---
title: 'Procedura: configurare la persistenza con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 7b65b89db674a624f7dfbf8ca816e0f0c2d2ff80
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963472"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Procedura: configurare la persistenza con WorkflowServiceHost
In questo argomento viene descritto come configurare la funzionalità di archivio di istanze del flusso di lavoro SQL per abilitare la persistenza per i flussi di lavoro ospitati in <xref:System.ServiceModel.Activities.WorkflowServiceHost> tramite un file di configurazione. Prima di usare tale funzionalità è necessario creare un database SQL usato per rendere persistenti le istanze del flusso di lavoro. Per altre informazioni, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Per configurare l'archivio di istanze del flusso di lavoro SQL nella configurazione  
  
1. È possibile configurare le proprietà dell'archivio di istanze del flusso di lavoro SQL mediante <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamento del servizio che consente di modificare le impostazioni tramite la configurazione XML. Nell'esempio di configurazione seguente viene illustrato come configurare l'archivio di istanze del flusso di lavoro SQL utilizzando l'elemento <`sqlWorkflowInstanceStore`> Behavior in un file di configurazione.  
  
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
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     Per ulteriori informazioni su come configurare l'archivio di istanze del flusso di lavoro SQL, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Per ulteriori informazioni sulle singole impostazioni per l'elemento <`sqlWorkflowInstanceStore`> Behavior, vedere [Archivio di istanze del flusso di lavoro SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric fornisce un archivio di persistenza specifico. Per altre informazioni, vedere [persistenza di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))AppFabric.  
  
    > [!NOTE]
    > L'esempio di configurazione precedente usa la configurazione semplificata. Per altre informazioni, vedere [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) .  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a>Per configurare l'archivio di istanze del flusso di lavoro SQL nel codice  
  
1. È possibile configurare le proprietà dell'archivio di istanze del flusso di lavoro SQL mediante <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamento del servizio che consente di modificare le impostazioni tramite il codice. Nell'esempio seguente viene mostrato come configurare l'archivio di istanze del flusso di lavoro SQL tramite l'elemento del comportamento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> nel codice.  
  
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
  
     Per ulteriori informazioni su come configurare l'archivio di istanze del flusso di lavoro SQL, vedere [procedura: abilitare la persistenza SQL per i flussi di lavoro e i servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Per ulteriori informazioni sulle singole impostazioni per l'elemento del comportamento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, vedere [Archivio di istanze del flusso di lavoro SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric fornisce un archivio di persistenza specifico. Per altre informazioni, vedere [persistenza di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))AppFabric.  
  
    > [!NOTE]
    > L'esempio di configurazione precedente usa la configurazione semplificata. Per altre informazioni, vedere [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) .  
  
     Per un esempio di come configurare la persistenza a livello di codice, vedere [procedura: abilitare la persistenza per i flussi di lavoro e i servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Persistenza del flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [Persistenza di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))
