---
title: 'Procedura: creare un archivio di istanze personalizzato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db9f09236764697aff4e57ace593827193c6e07d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-instance-store"></a><span data-ttu-id="c63d4-102">Procedura: creare un archivio di istanze personalizzato</span><span class="sxs-lookup"><span data-stu-id="c63d4-102">How to: Create a Custom Instance Store</span></span>
<span data-ttu-id="c63d4-103">In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] è presente <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, un archivio di istanze che usa SQL Server per rendere persistenti i dati del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c63d4-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] contains <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, an instance store that uses SQL Server to persist workflow data.</span></span> <span data-ttu-id="c63d4-104">Se l'applicazione deve rendere persistenti i dati del flusso di lavoro in un altro supporto, ad esempio un altro database o un file system, è possibile implementare un archivio di istanze personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c63d4-104">If your application is required to persist workflow data to another medium, such as a different database or a file system, you can implement a custom instance store.</span></span> <span data-ttu-id="c63d4-105">L'archivio di istanze personalizzato viene creato estendendo la classe astratta <xref:System.Runtime.DurableInstancing.InstanceStore> e implementando i metodi obbligatori per l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c63d4-105">A custom instance store is created by extending the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class and implementing the methods that are required for the implementation.</span></span> <span data-ttu-id="c63d4-106">Per un'implementazione completa di un archivio di istanze personalizzato, vedere il [processo di acquisto aziendale](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="c63d4-106">For a complete implementation of a custom instance store, see the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span>  
  
## <a name="implementing-the-begintrycommand-method"></a><span data-ttu-id="c63d4-107">Implementazione del metodo BeginTryCommand</span><span class="sxs-lookup"><span data-stu-id="c63d4-107">Implementing the BeginTryCommand method</span></span>  
 <span data-ttu-id="c63d4-108">Il metodo <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> viene inviato all'archivio di istanze dal motore di persistenza.</span><span class="sxs-lookup"><span data-stu-id="c63d4-108">The <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> is sent to the instance store by the persistence engine.</span></span> <span data-ttu-id="c63d4-109">Il tipo del parametro `command` indica il comando che è in esecuzione; questo parametro può essere dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="c63d4-109">The type of the `command` parameter indicates which command is being executed; this parameter can be of the following types:</span></span>  
  
-   <span data-ttu-id="c63d4-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze quando occorre rendere persistente un flusso di lavoro nel supporto di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c63d4-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be persisted to the storage medium.</span></span> <span data-ttu-id="c63d4-111">I dati di persistenza del flusso di lavoro vengono forniti al metodo nel membro <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> del parametro `command`.</span><span class="sxs-lookup"><span data-stu-id="c63d4-111">The workflow persistence data is provided to the method in the <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> member of the `command` parameter.</span></span>  
  
-   <span data-ttu-id="c63d4-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze quando occorre caricare un flusso di lavoro dal supporto di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c63d4-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be loaded from the storage medium.</span></span> <span data-ttu-id="c63d4-113">L'ID dell'istanza del flusso di lavoro da caricare viene fornito al metodo nel parametro `instanceId` della proprietà <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> del parametro `context`.</span><span class="sxs-lookup"><span data-stu-id="c63d4-113">The instance ID of the workflow to be loaded is provided to the method in the `instanceId` parameter of the <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> property of the `context` parameter.</span></span>  
  
-   <span data-ttu-id="c63d4-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze quando occorre registrare un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> come proprietario di blocco.</span><span class="sxs-lookup"><span data-stu-id="c63d4-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when a <xref:System.ServiceModel.Activities.WorkflowServiceHost> must be registered as a lock owner.</span></span> <span data-ttu-id="c63d4-115">L'ID dell'istanza del flusso di lavoro corrente deve essere fornito all'archivio di istanze usando il metodo <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> del parametro `context`.</span><span class="sxs-lookup"><span data-stu-id="c63d4-115">The instance ID of the current workflow should be provided to the instance store using <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> method of the `context` parameter.</span></span>  
  
     <span data-ttu-id="c63d4-116">Nel frammento di codice riportato di seguito viene illustrato come implementare il comando CreateWorkflowOwner per assegnare un proprietario di blocco esplicito.</span><span class="sxs-lookup"><span data-stu-id="c63d4-116">The following code snippet demonstrates how to implement the CreateWorkflowOwner command to assign an explicit lock owner.</span></span>  
  
    ```  
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");  
    ...  
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()  
    {  
        InstanceOwnerMetadata =  
        {  
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },  
        }  
    };  
    InstanceHandle ownerHandle = store.CreateInstanceHandle();  
    store.DefaultInstanceOwner = store.Execute(  
                                   ownerHandle,  
                                   createCommand,  
                                   TimeSpan.FromSeconds(30)).InstanceOwner;  
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });  
    ```  
  
-   <span data-ttu-id="c63d4-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze quando l'ID di istanza di un proprietario di blocco può essere rimosso dall'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="c63d4-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when the instance ID of a lock owner can be removed from the instance store.</span></span> <span data-ttu-id="c63d4-118">Come con <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, l'ID del proprietario di blocco deve essere fornito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c63d4-118">As with <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, the ID of the lock owner should be provided by the application.</span></span>  
  
     <span data-ttu-id="c63d4-119">Nel frammento di codice riportato di seguito viene mostrato come rilasciare un blocco usando <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span><span class="sxs-lookup"><span data-stu-id="c63d4-119">The following code snippet demonstrates how to release a lock using <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span></span>  
  
    ```  
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)  
    {  
        handle.Free();  
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);  
        try  
        {  
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.  
            Thread.Sleep(10000);  
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));  
        }  
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }  
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }  
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }  
        catch (Exception ex) { Log.Inform(ex.Message); }  
        finally  
        {  
            handle.Free();  
            store.DefaultInstanceOwner = null;  
        }  
    }  
    ```  
  
     <span data-ttu-id="c63d4-120">Il metodo sopra indicato deve essere chiamato in un blocco Try/Catch quando viene eseguita un'istanza figlio.</span><span class="sxs-lookup"><span data-stu-id="c63d4-120">The above method should be called in a Try/Catch block when a child instance is run.</span></span>  
  
    ```  
    try  
    {  
        childInstance.Run();  
    }  
    catch (Exception)  
    {  
        throw ;  
    }  
    finally  
    {  
        FreeHandleAndDeleteOwner(store, ownerHandle);  
    }  
    ```  
  
-   <span data-ttu-id="c63d4-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze quando occorre caricare un'istanza del flusso di lavoro usando la chiave di istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c63d4-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: The persistence engine sends this command to the instance store when a workflow instance is to be loaded using the workflow’s instance key.</span></span> <span data-ttu-id="c63d4-122">L'ID della chiave di istanza può essere determinato tramite il parametro <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> del comando.</span><span class="sxs-lookup"><span data-stu-id="c63d4-122">The ID of the instance key can be determined by using the <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parameter of the command.</span></span>  
  
-   <span data-ttu-id="c63d4-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze per recuperare i parametri di attivazione per i flussi di lavoro persistenti al fine di creare un host del flusso di lavoro che possa successivamente caricare i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c63d4-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: The persistence engine sends this command to the instance store to retrieve activation parameters for persisted workflows in order to create a workflow host that can then load workflows.</span></span> <span data-ttu-id="c63d4-124">Questo comando viene inviato dal motore in risposta all'archivio di istanze che genera <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> all'host quando individua un'istanza che può essere attivata.</span><span class="sxs-lookup"><span data-stu-id="c63d4-124">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> to the host when it locates an instance that can be activated.</span></span> <span data-ttu-id="c63d4-125">Un archivio di istanze deve essere sottoposto a polling per determinare se sono presenti flussi di lavoro che possono essere attivati.</span><span class="sxs-lookup"><span data-stu-id="c63d4-125">The instance store should be polled to determine if there are workflows that can be activated.</span></span>  
  
-   <span data-ttu-id="c63d4-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: il comando viene inviato dal motore di persistenza all'archivio di istanze per caricare le istanze del flusso di lavoro eseguibili.</span><span class="sxs-lookup"><span data-stu-id="c63d4-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: The persistence engine sends this command to the instance store to load runnable workflow instances.</span></span> <span data-ttu-id="c63d4-127">Questo comando viene inviato dal motore in risposta all'archivio di istanze che genera <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> all'host quando individua un'istanza che può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="c63d4-127">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> to the host when it locates an instance that can be run.</span></span> <span data-ttu-id="c63d4-128">L'archivio di istanze deve effettuare il polling dei flussi di lavoro che possono essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="c63d4-128">The instance store should poll for workflows that can be run.</span></span> <span data-ttu-id="c63d4-129">Nel frammento di codice riportato di seguito viene illustrato il polling dei flussi di lavoro che possono essere eseguiti o attivati nell'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="c63d4-129">The following code snippet demonstrates polling an instance store for workflows that can be run or activated.</span></span>  
  
    ```  
    public void PollForEvents()  
    {  
        InstanceOwner[] storeOwners = this.GetInstanceOwners();  
  
        foreach (InstanceOwner owner in storeOwners)  
        {  
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))  
            {  
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))  
                {  
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivable);  
                    if (hasRunnable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))  
                {  
                   bool hasActivable = GetActivableEvents(this.StoreId, owner.InstanceOwnerId);  
                   if (hasActivable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="c63d4-130">Nel frammento di codice precedente, viene eseguita una query dall'archivio di istanze sugli eventi disponibili e ciascun evento viene esaminato per determinare se è un evento <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>.</span><span class="sxs-lookup"><span data-stu-id="c63d4-130">In the above code snippet, the instance store queries the events available and examines each one to determine if it is a <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> event.</span></span> <span data-ttu-id="c63d4-131">Se viene trovato un evento di questo tipo, viene chiamato il metodo <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> per indicare all'host di inviare un comando all'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="c63d4-131">If one is found, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> is called to signal the host to send a command to the instance store.</span></span>  <span data-ttu-id="c63d4-132">Nel frammento di codice riportato di seguito viene illustrata un'implementazione di un gestore per questo comando.</span><span class="sxs-lookup"><span data-stu-id="c63d4-132">The following code snippet demonstrates an implementation of a handler for this command.</span></span>  
  
    ```  
    If (command is TryLoadRunnableWorkflowCommand)  
    {  
        Owner owner;  
        CheckOwner(context, command.Name, out owner);                          
        // Checking instance.Owner is like an InstanceLockQueryResult.  
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));  
  
        XName ownerService = null;  
        InstanceValue value;  
        Instance runnableInstance = default(Instance);  
        bool foundRunnableInstance = false;  
  
        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);  
        if (value != null && value.Value is XName)  
        {  
            ownerService = (XName)value.Value;  
        }  
  
        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)  
        {  
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)  
            {  
                continue;  
            }  
  
            if (ownerService != null)  
            {  
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);  
                if (value == null || ((XName)value.Value) != ownerService)  
                {  
                    continue;  
                }  
            }  
  
            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);  
            if (value != null && value.Value != null && value.Value is string)  
            {  
                continue;  
            }  
  
            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);  
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")  
            {  
                runnableInstance = instance.Value;  
                foundRunnableInstance = true;  
            }  
  
            if (!foundRunnableInstance)  
            {  
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);  
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)  
                {                          
                    runnableInstance = instance.Value;  
                    foundRunnableInstance = true;  
                }  
            }  
  
            if (foundRunnableInstance)  
            {  
                runnableInstance.LockVersion++;  
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;  
                MemoryStore.instances[instance.Key] = runnableInstance;  
                context.BindInstance(instance.Key);  
                context.BindAcquiredLock(runnableInstance.LockVersion);  
  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)  
                {  
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)  
                {  
                    if (keyEntry.Value.Completed)  
                    {  
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                    else  
                    {  
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                }  
            }  
  
            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);  
            break;  
        }  
    }  
    ```  
  
     <span data-ttu-id="c63d4-133">Nel frammento di codice precedente, un archivio di istanze esegue una ricerca delle istanze eseguibili.</span><span class="sxs-lookup"><span data-stu-id="c63d4-133">In the above code snippet, the instance store searches for runnable instances.</span></span> <span data-ttu-id="c63d4-134">Se viene trovata un'istanza eseguibile, viene associata al contesto di esecuzione e viene caricata.</span><span class="sxs-lookup"><span data-stu-id="c63d4-134">If an instance is found, it is bound to the execution context and loaded.</span></span>  
  
## <a name="using-a-custom-instance-store"></a><span data-ttu-id="c63d4-135">Uso di un archivio di istanze personalizzato</span><span class="sxs-lookup"><span data-stu-id="c63d4-135">Using a custom instance store</span></span>  
 <span data-ttu-id="c63d4-136">Per implementare un archivio di istanze personalizzato, assegnare un'istanza dell'archivio di istanze a <xref:System.Activities.WorkflowApplication.InstanceStore%2A>e implementare il metodo <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="c63d4-136">To implement a custom instance store, assign an instance of the instance store to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, and implement the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> method.</span></span>  <span data-ttu-id="c63d4-137">Vedere il [procedura: creare ed eseguire un flusso di lavoro in esecuzione lungo](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) esercitazione per informazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="c63d4-137">See the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) tutorial for specifics.</span></span>  
  
## <a name="a-sample-instance-store"></a><span data-ttu-id="c63d4-138">Esempio di archivio di istanze</span><span class="sxs-lookup"><span data-stu-id="c63d4-138">A sample instance store</span></span>  
 <span data-ttu-id="c63d4-139">Esempio di codice seguente è un'implementazione di archivio di istanza completa, ricavata il [processo di acquisto aziendale](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="c63d4-139">The following code sample is a complete instance store implementation, taken from the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span> <span data-ttu-id="c63d4-140">Questo archivio di istanze rende persistenti i dati del flusso di lavoro a un file mediante XML.</span><span class="sxs-lookup"><span data-stu-id="c63d4-140">This instance store persists workflow data to a file using XML.</span></span>  
  
```  
using System;  
using System.Activities.DurableInstancing;  
using System.Collections.Generic;  
using System.IO;  
using System.Runtime.DurableInstancing;  
using System.Runtime.Serialization;  
using System.ServiceModel.Persistence;  
using System.Xml;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.WF.PurchaseProcess  
{  
  
    public class XmlWorkflowInstanceStore : InstanceStore  
    {  
        Guid ownerInstanceID;  
  
        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())  
        {  
  
        }  
  
        public XmlWorkflowInstanceStore(Guid id)  
        {  
            ownerInstanceID = id;  
        }  
  
        //Synchronous version of the Begin/EndTryCommand functions  
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)  
        {  
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));  
        }  
  
        //The persistence engine will send a variety of commands to the configured InstanceStore,  
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.  
        //This method is where we will handle those commands  
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)  
        {  
            IDictionary<XName, InstanceValue> data = null;  
  
            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle  
            if (command is CreateWorkflowOwnerCommand)  
            {  
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());  
            }  
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key  
            else if (command is SaveWorkflowCommand)  
            {  
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;  
                data = saveCommand.InstanceData;  
  
                Save(data);  
            }  
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle  
            else if (command is LoadWorkflowCommand)  
            {  
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
  
                try  
                {  
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))  
                    {  
                        data = LoadInstanceDataFromFile(inputStream);  
                        //load the data into the persistence Context  
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);  
                    }  
                }  
                catch (Exception exception)  
                {  
                    throw new PersistenceException(exception.Message);  
                }  
            }  
  
            return new CompletedAsyncResult<bool>(true, callback, state);  
        }  
  
        protected override bool EndTryCommand(IAsyncResult result)  
        {  
            return CompletedAsyncResult<bool>.End(result);  
        }  
  
        //Reads data from xml file and creates a dictionary based off of that.  
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)  
        {  
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();  
  
            NetDataContractSerializer s = new NetDataContractSerializer();  
  
            XmlReader rdr = XmlReader.Create(inputStream);  
            XmlDocument doc = new XmlDocument();  
            doc.Load(rdr);  
  
            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");  
            foreach (XmlElement instanceElement in instances)  
            {  
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");  
                XName key = (XName)DeserializeObject(s, keyElement);  
  
                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");  
                object value = DeserializeObject(s, valueElement);  
                InstanceValue instVal = new InstanceValue(value);  
  
                data.Add(key, instVal);  
            }  
  
            return data;  
        }  
  
        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)  
        {  
            object deserializedObject = null;  
  
            MemoryStream stm = new MemoryStream();  
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);  
            element.WriteContentTo(wtr);  
            wtr.Flush();  
            stm.Position = 0;  
  
            deserializedObject = serializer.Deserialize(stm);  
  
            return deserializedObject;  
        }  
  
        //Saves the persistence data to an xml file.  
        void Save(IDictionary<XName, InstanceValue> instanceData)  
        {  
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
            XmlDocument doc = new XmlDocument();  
            doc.LoadXml("<InstanceValues/>");  
  
            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)  
            {  
                XmlElement newInstance = doc.CreateElement("InstanceValue");  
  
                XmlElement newKey = SerializeObject("key", valPair.Key, doc);  
                newInstance.AppendChild(newKey);  
  
                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);  
                newInstance.AppendChild(newValue);  
  
                doc.DocumentElement.AppendChild(newInstance);  
            }  
            doc.Save(fileName);  
       }  
  
        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)  
        {  
            NetDataContractSerializer s = new NetDataContractSerializer();  
            XmlElement newElement = doc.CreateElement(elementName);  
            MemoryStream stm = new MemoryStream();  
  
            s.Serialize(stm, o);  
            stm.Position = 0;  
            StreamReader rdr = new StreamReader(stm);  
            newElement.InnerXml = rdr.ReadToEnd();  
  
            return newElement;  
        }  
    }  
}  
```
