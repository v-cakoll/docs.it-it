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
# <a name="using-workflowidentity-and-versioning"></a>Utilizzo di WorkflowIdentity e controllo delle versioni

<xref:System.Activities.WorkflowIdentity> offre agli sviluppatori di applicazioni flusso di lavoro un modo per associare un nome e un elemento <xref:System.Version> a una definizione del flusso di lavoro. Consente inoltre di associare queste informazioni a un'istanza persistente del flusso di lavoro. Queste informazioni di identità possono essere usate dagli sviluppatori di applicazioni flusso di lavoro per scenari quali l'esecuzione affiancata di più versioni di una definizione del flusso di lavoro e costituiscono un elemento fondamentale per altre funzionalità come l'aggiornamento dinamico. In questo argomento viene fornita una panoramica sull'utilizzo di <xref:System.Activities.WorkflowIdentity> con hosting <xref:System.Activities.WorkflowApplication>. Per informazioni sull'esecuzione affiancata delle definizioni del flusso di lavoro in un servizio del flusso di lavoro, vedere [controllo delle versioni side-by-side in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md). Per informazioni sull'aggiornamento dinamico, vedere [aggiornamento dinamico](dynamic-update.md).

## <a name="in-this-topic"></a>In questo argomento

- [Uso di WorkflowIdentity](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [Esecuzione side-by-side con WorkflowIdentity](using-workflowidentity-and-versioning.md#SxS)

- [Aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [Per aggiornare lo schema del database](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a>Uso di WorkflowIdentity

Per usare <xref:System.Activities.WorkflowIdentity>, creare un'istanza, configurarla e associarla a un'istanza di <xref:System.Activities.WorkflowApplication>. L'istanza di <xref:System.Activities.WorkflowIdentity> contiene tre informazioni di identificazione. Le proprietà <xref:System.Activities.WorkflowIdentity.Name%2A> e <xref:System.Activities.WorkflowIdentity.Version%2A> contengono un nome e un oggetto <xref:System.Version> e sono obbligatorie, mentre la proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e può essere usata per specificare una stringa aggiuntiva che contiene informazioni quali il nome dell'assembly o altre informazioni desiderate. Un oggetto <xref:System.Activities.WorkflowIdentity> è univoco se una qualsiasi delle tre relative proprietà è diversa da un altro oggetto <xref:System.Activities.WorkflowIdentity>.

> [!IMPORTANT]
> <xref:System.Activities.WorkflowIdentity> non deve contenere eventuali informazioni identificabili personalmente (PII). Le informazioni su <xref:System.Activities.WorkflowIdentity> usate per creare un'istanza vengono generate a tutti i servizi di rilevamento configurati in vari punti del ciclo di vita di attività dal runtime. La verifica di WF non ha alcun meccanismo per nascondere i PII (dati riservati dell'utente). Di conseguenza, un'istanza di <xref:System.Activities.WorkflowIdentity> non deve contenere dati di PII poiché verrebbe generata dal runtime nei record di rilevamento e può essere visibile agli utenti con accesso alla visualizzazione dei record di rilevamento.

Nell'esempio riportato di seguito, un oggetto <xref:System.Activities.WorkflowIdentity> viene creato e associato a un'istanza di un flusso di lavoro creato usando una definizione del flusso di lavoro di `MortgageWorkflow`.

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

Quando un flusso di lavoro viene nuovamente caricato e ripreso, è necessario usare un oggetto <xref:System.Activities.WorkflowIdentity> configurato per corrispondere all'oggetto <xref:System.Activities.WorkflowIdentity> dell'istanza persistente del flusso di lavoro.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

Se l'oggetto <xref:System.Activities.WorkflowIdentity> usato durante la ricarica dell'istanza del flusso di lavoro non corrisponde l'oggetto <xref:System.Activities.WorkflowIdentity> persistente, viene generata un'eccezione <xref:System.Activities.VersionMismatchException>. Nell'esempio riportato di seguito viene effettuato un tentativo di caricamento dell'istanza di `MortgageWorkflow` che è stata resa persistente nell'esempio precedente. Questo tentativo di caricamento viene eseguito mediante <xref:System.Activities.WorkflowIdentity> configurato per una versione più recente del flusso di lavoro relativo a un'ipoteca che non corrisponde all'istanza persistente.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

Quando viene eseguito il codice precedente, viene generata la seguente eccezione <xref:System.Activities.VersionMismatchException>.

```output
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a>Esecuzione side-by-side con WorkflowIdentity

<xref:System.Activities.WorkflowIdentity> può essere usato per facilitare l'esecuzione di più versioni di un flusso di lavoro affiancate. Uno scenario comune consiste nella modifica dei requisiti aziendali in un flusso di lavoro di lunga durata. Molte istanze di un flusso di lavoro potrebbero essere in esecuzione quando una versione aggiornata viene distribuita. L'applicazione host può essere configurata per usare la definizione aggiornata del flusso di lavoro all'avvio di nuove istanze. È responsabilità dell'applicazione host fornire la definizione del flusso di lavoro corretta quando vengono riprese le istanze. <xref:System.Activities.WorkflowIdentity> può essere usato per identificare e fornire la definizione corrispondente del flusso di lavoro quando vengono riprese le istanze del flusso di lavoro.

Per recuperare l'oggetto <xref:System.Activities.WorkflowIdentity> di un'istanza persistente del flusso di lavoro, viene usato il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A>. Il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A> accetta l'oggetto <xref:System.Activities.WorkflowApplication.Id%2A> dell'istanza persistente del flusso di lavoro e l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> contenente l'istanza persistente e restituisce un oggetto <xref:System.Activities.WorkflowApplicationInstance>. Un oggetto <xref:System.Activities.WorkflowApplicationInstance> contiene informazioni su un'istanza persistente del flusso di lavoro, incluso il relativo oggetto <xref:System.Activities.WorkflowIdentity> associato. Questo oggetto <xref:System.Activities.WorkflowIdentity> associato può essere usato dall'host per fornire la definizione del flusso di lavoro corretta durante il caricamento e la ripresa dell'istanza del flusso di lavoro.

> [!NOTE]
> Un oggetto <xref:System.Activities.WorkflowIdentity> null è valido e può essere usato dall'host per eseguire il mapping delle istanze che sono state salvate in modo permanente senza alcun <xref:System.Activities.WorkflowIdentity> associato alla definizione appropriata del flusso di lavoro. Questo scenario può verificarsi quando un'applicazione flusso di lavoro non è stata inizialmente scritta con il controllo delle versioni del flusso di lavoro o quando un'applicazione viene aggiornata da .NET Framework 4. Per ulteriori informazioni, vedere [aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).

Nell'esempio seguente viene utilizzato un `Dictionary<WorkflowIdentity, Activity>` per associare <xref:System.Activities.WorkflowIdentity> istanze con le relative definizioni del flusso di lavoro corrispondenti e viene avviato un flusso di lavoro utilizzando la definizione del flusso di lavoro `MortgageWorkflow`, associata alla <xref:System.Activities.WorkflowIdentity>`identityV1`.

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

Nell'esempio riportato di seguito, le informazioni sull'istanza persistente del flusso di lavoro derivante dall'esempio precedente vengono recuperate chiamando il metodo <xref:System.Activities.WorkflowApplication.GetInstance%2A>; le informazioni relative all'oggetto <xref:System.Activities.WorkflowIdentity> persistente vengono usate per recuperare la definizione corrispondente del flusso di lavoro. Queste informazioni vengono usate per configurare <xref:System.Activities.WorkflowApplication>, quindi il flusso di lavoro viene caricato. Si noti che dal momento che viene usato l'overload <xref:System.Activities.WorkflowApplication.Load%2A> che accetta <xref:System.Activities.WorkflowApplicationInstance>, l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che era configurato nell'oggetto <xref:System.Activities.WorkflowApplicationInstance> viene usato da <xref:System.Activities.WorkflowApplication>, di conseguenza la relativa proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> non necessita di configurazione.

> [!NOTE]
> Se la proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> è impostata, deve essere impostata con la stessa istanza di <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usata da <xref:System.Activities.WorkflowApplicationInstance>, altrimenti verrà generata un'eccezione <xref:System.ArgumentException> con il messaggio seguente: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.

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

## <a name="UpdatingWF4PersistenceDatabases"></a>Aggiornamento .NET Framework 4 database di persistenza per supportare il controllo delle versioni del flusso di lavoro

Viene fornito uno script di database SqlWorkflowInstanceStoreSchemaUpgrade. SQL per aggiornare i database di persistenza creati usando gli script di database .NET Framework 4. Questo script aggiorna i database per supportare le nuove funzionalità di controllo delle versioni introdotte in .NET Framework 4,5. Le istanze persistenti del flusso di lavoro nei database sono valori predefiniti specificati per il controllo delle versioni e quindi possono partecipare all'esecuzione side-by-side e all'aggiornamento dinamico.

Se un'applicazione flusso di lavoro .NET Framework 4,5 tenta di eseguire qualsiasi operazione di persistenza che utilizza le nuove funzionalità di controllo delle versioni in un database di persistenza che non è stato aggiornato utilizzando lo script fornito, viene generata un'<xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> con un messaggio simile al seguente.

```output
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a>Per aggiornare lo schema del database

1. Aprire SQL Server Management Studio e connettersi al server di database di persistenza, ad esempio **.\SQLEXPRESS**.

2. Scegliere **Apri**dal **menu** **file** . Passare alla cartella seguente: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`

3. Selezionare **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** e fare clic su **Apri**.

4. Selezionare il nome del database di persistenza nell'elenco a discesa **database disponibili** .

5. Scegliere **Esegui** dal menu **query** .

Quando la query viene completata, lo schema di database verrà aggiornato e, se necessario, è possibile visualizzare l'identità predefinita del flusso di lavoro assegnata alle istanze persistenti del flusso di lavoro. Espandere il database di persistenza nel nodo **database** del **Esplora oggetti**, quindi espandere il nodo **visualizzazioni** . Fare clic con il pulsante destro del mouse su **System. Activities. DurableInstancing. Instances** e scegliere **seleziona le prime 1000 righe**. Scorrere fino alla fine delle colonne. si noti che alla vista sono state aggiunte sei colonne aggiuntive: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **minor**e **Revision**. Tutti i flussi di lavoro salvati avranno un valore **null** per questi campi, che rappresenta un'identità del flusso di lavoro null.
