---
title: 'Procedura: abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi'
ms.date: 03/30/2017
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: bef95dbeaaa96678a66ba94494a0207c7314c326
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802583"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a>Procedura: abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi

In questo argomento viene descritto come configurare la funzionalità di archivio di istanze del flusso di lavoro SQL per abilitare la persistenza per i flussi di lavoro e i relativi servizi sia a livello di codice sia tramite un file di configurazione.

Windows Server AppFabric semplifica il processo di configurazione della persistenza. Per altre informazioni, vedere [configurazione di persistenza di App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee790848(v=azure.10)).

Prima di usare tale funzionalità, creare un database usato dalla funzionalità per rendere persistenti le istanze del flusso di lavoro. Il programma di installazione di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] copia i file di script SQL associati alla funzionalità di archivio di istanze del flusso di lavoro SQL nella cartella %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN. Eseguire questi file di script in un database di SQL Server 2005 o SQL Server 2008 che si desidera venga usato dall'archivio di istanze del flusso di lavoro SQL per rendere persistenti le istanze del flusso di lavoro. Eseguire innanzitutto il file SqlWorkflowInstanceStoreSchema.sql, quindi il file SqlWorkflowInstanceStoreLogic.sql.

> [!NOTE]
> Per pulire il database di persistenza per avere un database aggiornato, eseguire gli script in %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN nell'ordine seguente.
>
> 1. SqlWorkflowInstanceStoreSchema.sql
> 2. SqlWorkflowInstanceStoreLogic.sql

> [!IMPORTANT]
> Se non si crea un database di persistenza, la funzionalità di archivio di istanze del flusso di lavoro SQL genera un'eccezione simile alla seguente quando un host tenta di rendere persistenti i flussi di lavoro.
>
> System.Data.SqlClient.SqlException: Impossibile trovare la stored procedure 'System.Activities.DurableInstancing.CreateLockOwner'

Nelle sezioni seguenti viene descritto come abilitare la persistenza per i flussi di lavoro e i relativi servizi usando l'archivio di istanze del flusso di lavoro SQL. Per ulteriori informazioni sulle proprietà dell'archivio di istanze del flusso di lavoro SQL, vedere [proprietà dell'archivio di istanze del flusso di lavoro SQL](properties-of-sql-workflow-instance-store.md).

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a>Abilitazione della persistenza per i flussi di lavoro indipendenti che usano l'oggetto WorkflowApplication

È possibile abilitare la persistenza per i flussi di lavoro indipendenti che usano l'oggetto <xref:System.Activities.WorkflowApplication> a livello di codice tramite il modello a oggetti <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. Nella procedura seguente sono inclusi i passaggi per eseguire questa operazione.

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a>Per abilitare la persistenza per i flussi di lavoro indipendenti

1. Aggiungere un riferimento a System. Activities. DurableInstancing. dll.

2. Aggiungere l'istruzione seguente all'inizio del file di origine dopo le istruzioni "using" esistenti.

    ```csharp
    using System.Activities.DurableInstancing;
    ```

3. Costruire un oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> e assegnarlo alla proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> dell'oggetto <xref:System.Activities.WorkflowApplication> come mostrato nell'esempio di codice seguente.

    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```

   > [!NOTE]
   > Il nome del server della stringa di connessione potrebbe essere diverso a seconda dell'edizione di SQL Server.

4. Richiamare il metodo <xref:System.Activities.WorkflowApplication.Persist%2A> sull'oggetto <xref:System.Activities.WorkflowApplication> per rendere persistente un flusso di lavoro o il metodo <xref:System.Activities.WorkflowApplication.Unload%2A> per rendere persistente e scaricare un flusso di lavoro. È anche possibile gestire l'evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> generato dall'oggetto <xref:System.Activities.WorkflowApplication> e restituire il membro (<xref:System.Activities.PersistableIdleAction.Persist> o <xref:System.Activities.PersistableIdleAction.Unload>) appropriato dell'oggetto <xref:System.Activities.PersistableIdleAction>.

   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> Per istruzioni dettagliate, vedere [procedura: creare ed eseguire un flusso di lavoro con esecuzione prolungata](how-to-create-and-run-a-long-running-workflow.md) dell' [esercitazione Introduzione](getting-started-tutorial.md) .

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a>Abilitazione della persistenza per i servizi flussi di lavoro indipendenti che usano l'oggetto WorkflowServiceHost

È possibile abilitare la persistenza per i servizi flussi di lavoro indipendenti che usano l'oggetto <xref:System.ServiceModel.WorkflowServiceHost> a livello di codice tramite la classe <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> o <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a>Utilizzo della classe SqlWorkflowInstanceStoreBehavior

Nella procedura seguente sono contenuti i passaggi per usare la classe <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> al fine di abilitare la persistenza per i servizi flussi di lavoro indipendenti.

#### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a>Per abilitare la persistenza tramite l'oggetto SqlWorkflowInstanceStoreBehavior

1. Aggiungere un riferimento a System.ServiceModel.dll.

2. Aggiungere l'istruzione seguente all'inizio del file di origine dopo le istruzioni "using" esistenti.

    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3. Creare un'istanza dell'oggetto `WorkflowServiceHost` e aggiungere gli endpoint per il servizio flusso di lavoro.

    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");
    ```

4. Costruire un oggetto `SqlWorkflowInstanceStoreBehavior` e impostare le proprietà dell'oggetto di comportamento.

    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5. Aprire l'host del servizio flusso di lavoro.

    ```csharp
    host.Open();
    ```

### <a name="using-the-durableinstancingoptions-property"></a>Utilizzo della proprietà DurableInstancingOptions

Quando l'oggetto `SqlWorkflowInstanceStoreBehavior` è applicato, l'oggetto `DurableInstancingOptions.InstanceStore` in `WorkflowServiceHost` viene impostato sull'oggetto `SqlWorkflowInstanceStore` creato usando i valori di configurazione. Tale operazione può essere eseguita anche a livello di codice per impostare la proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> dell'oggetto `WorkflowServiceHost` senza usare la classe `SqlWorkflowInstanceStoreBehavior` come mostrato nell'esempio di codice seguente.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a>Abilitazione della persistenza per i servizi flussi di lavoro ospitati nel servizio WAS che usano l'oggetto WorkflowServiceHost tramite un file di configurazione

È possibile abilitare la persistenza per i servizi flussi di lavori indipendenti oppure ospitati nel servizio WAS tramite un file di configurazione. Un servizio flusso di lavoro ospitato nel servizio WAS usa l'oggetto WorkflowServiceHost come servizi flussi di lavoro indipendenti.

Il `SqlWorkflowInstanceStoreBehavior`, un comportamento del servizio che consente di modificare facilmente le proprietà dell' [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md) tramite la configurazione XML. Per i servizi flussi di lavoro ospitati nel servizio WAS, usare il file Web.config. Nell'esempio di configurazione seguente viene mostrato come configurare l'archivio di istanze del flusso di lavoro SQL tramite l'elemento del comportamento `sqlWorkflowInstanceStore` in un file di configurazione.

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

Se non si impostano i valori per la proprietà `connectionString` o `connectionStringName`, l'archivio di istanze del flusso di lavoro SQL usa la stringa di connessione predefinita denominata `DefaultSqlWorkflowInstanceStoreConnectionString`.

Quando l'oggetto `SqlWorkflowInstanceStoreBehavior` è applicato, l'oggetto `DurableInstancingOptions.InstanceStore` in `WorkflowServiceHost` viene impostato sull'oggetto `SqlWorkflowInstanceStore` creato usando i valori di configurazione. Tale operazione può essere eseguita anche a livello di codice per usare l'oggetto `SqlWorkflowInstanceStore` con l'oggetto `WorkflowServiceHost` senza usare l'elemento del comportamento del servizio.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

> [!IMPORTANT]
> È consigliabile non archiviare nel file Web.config informazioni riservate, quali nomi utente e password. In caso contrario, è necessario proteggere l'accesso a tale file tramite gli elenchi di controllo di accesso (ACL) del file system. Inoltre, è possibile proteggere i valori di configurazione all'interno di un file di configurazione come indicato in [crittografia delle informazioni di configurazione tramite la configurazione protetta](https://docs.microsoft.com/en-us/previous-versions/aspnet/53tyfkaw(v=vs.100)).

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a>Elementi Machine.config correlati alla funzionalità di archivio di istanze del flusso di lavoro SQL

L'installazione di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] comporta l'aggiunta degli elementi seguenti correlati alla funzionalità di archivio di istanze del flusso di lavoro SQL al file Machine.config:

- Aggiunge il seguente elemento di estensione del comportamento al file Machine. config in modo da poter utilizzare l'elemento del comportamento del servizio \<sqlWorkflowInstanceStore > nel file di configurazione per configurare la persistenza per i servizi.

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
