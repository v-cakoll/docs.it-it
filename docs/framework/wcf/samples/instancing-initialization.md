---
title: Inizializzazione della creazione di istanze
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: 897bb62df0a23073827aeed18b54bf77e8c6d4bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183603"
---
# <a name="instancing-initialization"></a><span data-ttu-id="0a7f1-102">Inizializzazione della creazione di istanze</span><span class="sxs-lookup"><span data-stu-id="0a7f1-102">Instancing Initialization</span></span>
<span data-ttu-id="0a7f1-103">In questo esempio si estende l'esempio [di pooling](../../../../docs/framework/wcf/samples/pooling.md) mediante la definizione di un'interfaccia , `IObjectControl`che consente di personalizzare l'inizializzazione di un oggetto attivandolo e disattivandolo.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-103">This sample extends the [Pooling](../../../../docs/framework/wcf/samples/pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="0a7f1-104">Il client richiama metodi che restituiscono l'oggetto al pool e che non restituiscono l'oggetto al pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-104">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a7f1-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="0a7f1-106">Punti di estensibilità</span><span class="sxs-lookup"><span data-stu-id="0a7f1-106">Extensibility Points</span></span>  
 <span data-ttu-id="0a7f1-107">Il primo passaggio nella creazione di un'estensione di Windows Communication Foundation (WCF) consiste nel decidere il punto di estendibilità da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-107">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="0a7f1-108">In WCF, il termine *EndpointDispatcher* si riferisce a un componente di runtime responsabile della conversione dei messaggi in arrivo in chiamate al metodo nel servizio dell'utente e della conversione dei valori restituiti da tale metodo in un messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-108">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="0a7f1-109">Un servizio WCF crea un EndpointDispatcher per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-109">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="0a7f1-110">L'EndpointDispatcher offre l'estensibilità dell'ambito dell'endpoint (per tutti i messaggi ricevuti o inviati dal servizio) utilizzando la classe <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-110">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="0a7f1-111">Questa classe consente di personalizzare le varie proprietà che controllano il comportamento dell'EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-111">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="0a7f1-112">Questo esempio si concentra sulla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> che punta all'oggetto che fornisce le istanze della classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-112">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="0a7f1-113">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="0a7f1-113">IInstanceProvider</span></span>  
 <span data-ttu-id="0a7f1-114">In WCF, il EndpointDispatcher crea istanze di una classe <xref:System.ServiceModel.Dispatcher.IInstanceProvider> di servizio utilizzando un provider di istanze che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-114">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="0a7f1-115">Questa interfaccia dispone solo di due metodi:</span><span class="sxs-lookup"><span data-stu-id="0a7f1-115">This interface has only two methods:</span></span>  
  
- <span data-ttu-id="0a7f1-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: quando un messaggio arriva, il dispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> per creare un'istanza della classe di servizio al fine di elaborare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="0a7f1-117">La frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-117">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="0a7f1-118">Ad esempio, se la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> è impostata su <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType> viene creata una nuova istanza della classe di servizio per elaborare ogni messaggio che arriva, pertanto il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> viene chiamato ogni qualvolta arriva un messaggio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-118">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="0a7f1-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: quando l'istanza del servizio finisce l'elaborazione del messaggio, l'EndpointDispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="0a7f1-120">Come per il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, la frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-120">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="0a7f1-121">Pool di oggetti</span><span class="sxs-lookup"><span data-stu-id="0a7f1-121">The Object Pool</span></span>  
 <span data-ttu-id="0a7f1-122">La classe `ObjectPoolInstanceProvider` contiene l'implementazione per il pool di oggetti.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-122">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="0a7f1-123">Questa classe implementa l'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceProvider> per interagire con il livello del modello di servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-123">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="0a7f1-124">Quando l'EndpointDispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, anziché creare una nuova istanza, l'implementazione personalizzata cerca un oggetto esistente in un pool in memoria.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-124">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="0a7f1-125">che viene restituito se disponibile.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-125">If one is available, it is returned.</span></span> <span data-ttu-id="0a7f1-126">In caso contrario, `ObjectPoolInstanceProvider` controlla se la proprietà `ActiveObjectsCount` (numero di oggetti restituito dal pool) ha raggiunto la dimensione massima del pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-126">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="0a7f1-127">In caso contrario, una nuova istanza viene creata e restituita al chiamante, quindi `ActiveObjectsCount` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-127">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="0a7f1-128">Diversamente, una richiesta di creazione di un oggetto viene accodata per un periodo di tempo configurato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-128">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="0a7f1-129">Nell'esempio di codice seguente viene illustrata l'implementazione di `GetObjectFromThePool`.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-129">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```csharp
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="0a7f1-130">L'implementazione personalizzata di `ReleaseInstance` aggiunge l'istanza rilasciata nuovamente al pool e decrementa il valore di `ActiveObjectsCount`.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-130">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="0a7f1-131">L'EndpointDispatcher può chiamare questi metodi da thread diversi e pertanto è necessario l'accesso sincronizzato ai membri del livello della classe nella classe `ObjectPoolInstanceProvider`.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-131">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```csharp
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="0a7f1-132">Il `ReleaseInstance` metodo fornisce una funzionalità di *inizializzazione di pulizia.*</span><span class="sxs-lookup"><span data-stu-id="0a7f1-132">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="0a7f1-133">Normalmente il pool gestisce un numero minimo di oggetti per la durata del pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-133">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="0a7f1-134">Ci possono essere, tuttavia, periodi di utilizzo eccessivo che richiedono la creazione di oggetti aggiuntivi nel pool per raggiungere il limite massimo specificato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-134">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="0a7f1-135">Successivamente, quando il pool diviene meno attivo, gli oggetti in eccesso possono divenire un sovraccarico aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-135">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="0a7f1-136">Pertanto, quando il conteggio `activeObjectsCount` si azzera, viene avviato un timer, precedentemente inattivo, che inizia ed esegue un ciclo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-136">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();
}  
```  
  
 <span data-ttu-id="0a7f1-137">Le estensioni del livello ServiceModel vengono collegate utilizzando i comportamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a7f1-137">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="0a7f1-138">Comportamenti del servizio: consentono la personalizzazione del runtime dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-138">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="0a7f1-139">Comportamenti dell'endpoint: consentono la personalizzazione di un particolare endpoint del servizio, incluso EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-139">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
- <span data-ttu-id="0a7f1-140">Comportamenti del contratto: consentono la personalizzazione delle classi <xref:System.ServiceModel.Dispatcher.ClientRuntime> o <xref:System.ServiceModel.Dispatcher.DispatchRuntime> rispettivamente sul client o sul servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-140">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
- <span data-ttu-id="0a7f1-141">Comportamenti dell'operazione: consentono la personalizzazione delle classi <xref:System.ServiceModel.Dispatcher.ClientOperation> o <xref:System.ServiceModel.Dispatcher.DispatchOperation> rispettivamente sul client o sul servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-141">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="0a7f1-142">Allo scopo di estendere il pool di oggetti, è possibile creare un comportamento dell'endpoint o del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-142">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="0a7f1-143">In questo esempio viene utilizzato un comportamento del servizio che applica la possibilità di creare pool di oggetti a ogni endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-143">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="0a7f1-144">I comportamenti del servizio vengono creati implementando l'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-144">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="0a7f1-145">Ci sono molti modi per indicare a ServiceModel i comportamenti personalizzati:</span><span class="sxs-lookup"><span data-stu-id="0a7f1-145">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="0a7f1-146">Utilizzo di un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-146">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="0a7f1-147">Aggiunto imperativamente alla raccolta di comportamenti della descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-147">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="0a7f1-148">Estensione dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0a7f1-148">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="0a7f1-149">Questo esempio utilizza un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-149">This sample uses a custom attribute.</span></span> <span data-ttu-id="0a7f1-150">Quando la classe <xref:System.ServiceModel.ServiceHost> viene costruita, essa esamina gli attributi utilizzati nella definizione del tipo del servizio e aggiunge i comportamenti disponibili alla raccolta di comportamenti della descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-150">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="0a7f1-151"><xref:System.ServiceModel.Description.IServiceBehavior> L'interfaccia dispone <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` di <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>tre metodi: e .</span><span class="sxs-lookup"><span data-stu-id="0a7f1-151">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="0a7f1-152">Questi metodi vengono chiamati <xref:System.ServiceModel.ServiceHost> da WCF quando il viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-152">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="0a7f1-153">Viene chiamato prima <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>, che consente di controllare la presenza di eventuali incoerenze nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="0a7f1-154">Successivamente viene chiamato <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>, che è necessario solo in scenari molto avanzati.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="0a7f1-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> viene chiamato per ultimo ed è responsabile per la configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="0a7f1-156">I parametri seguenti vengono passati in <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="0a7f1-156">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
- <span data-ttu-id="0a7f1-157">`Description`: questo parametro fornisce la descrizione del servizio per l'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-157">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="0a7f1-158">Può essere utilizzato per controllare dati della descrizione sugli endpoint del servizio, contratti, associazioni e altri dati associati al servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-158">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
- <span data-ttu-id="0a7f1-159">`ServiceHostBase`: questo parametro fornisce la classe <xref:System.ServiceModel.ServiceHostBase> che si sta attualmente inizializzando.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-159">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="0a7f1-160">Nell'implementazione personalizzata <xref:System.ServiceModel.Description.IServiceBehavior> viene creata una nuova istanza di `ObjectPoolInstanceProvider` e viene assegnata alla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> in ogni <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> associato a <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-160">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```csharp
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}
```  
  
 <span data-ttu-id="0a7f1-161">Oltre a un'implementazione della classe <xref:System.ServiceModel.Description.IServiceBehavior>, la classe `ObjectPoolingAttribute` ha molti membri per personalizzare il pool di oggetti utilizzando gli argomenti dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-161">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="0a7f1-162">Questi membri includono `MaxSize`, `MinSize`, `Enabled` e `CreationTimeout`, per corrispondere al set di funzionalità del pool di oggetti fornito da .NET Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-162">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="0a7f1-163">Il comportamento di pooling di oggetti può ora essere aggiunto a un servizio `ObjectPooling` WCF annotando l'implementazione del servizio con l'attributo personalizzato appena creato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-163">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="0a7f1-164">Attivazione e disattivazione del collegamento</span><span class="sxs-lookup"><span data-stu-id="0a7f1-164">Hooking Activation and Deactivation</span></span>  
 <span data-ttu-id="0a7f1-165">L'obiettivo principale del pool di oggetti è ottimizzare gli oggetti di breve durata con operazioni di creazione e inizializzazione relativamente dispendiose.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-165">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="0a7f1-166">Se utilizzato correttamente, può pertanto migliorare notevolmente le prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-166">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="0a7f1-167">Poiché l'oggetto viene restituito dal pool, il costruttore viene chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-167">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="0a7f1-168">Tuttavia, alcune applicazioni richiedono un certo livello di controllo in modo da poter inizializzare e pulire le risorse utilizzate durante un solo contesto.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-168">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="0a7f1-169">Ad esempio, un oggetto utilizzato per una serie di calcoli può reimpostare i relativi campi privati prima di elaborare il calcolo successivo.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-169">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="0a7f1-170">Enterprise Services abilita questo tipo di inizializzazione specifica del contesto consentendo allo sviluppatore degli oggetti di eseguire l'override dei metodi `Activate` e `Deactivate` dalla classe di base <xref:System.EnterpriseServices.ServicedComponent>.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-170">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="0a7f1-171">Il pool di oggetti chiama il metodo `Activate` poco prima di restituire l'oggetto dal pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-171">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="0a7f1-172">`Deactivate` viene chiamato quando l'oggetto viene restituito di nuovo al pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-172">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="0a7f1-173">La classe di base <xref:System.EnterpriseServices.ServicedComponent> dispone anche di una proprietà `boolean` denominata `CanBePooled`, che può essere utilizzata per notificare al pool se l'oggetto può essere ulteriormente inserito nel pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-173">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="0a7f1-174">Per riprodurre questa funzionalità, nell'esempio viene dichiarata un'interfaccia pubblica (`IObjectControl`) che dispone dei membri menzionati.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-174">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="0a7f1-175">Questa interfaccia viene quindi implementata dalle classi del servizio destinate a fornire l'inizializzazione specifica del contesto.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-175">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="0a7f1-176">L'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceProvider> deve essere modificata per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-176">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="0a7f1-177">A questo punto, ogni volta `GetInstance` che si ottiene un oggetto `IObjectControl.` chiamando il metodo , `Activate` è necessario verificare se l'oggetto implementa Se lo fa, è necessario chiamare il metodo in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-177">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="0a7f1-178">Quando si restituisce un oggetto al pool, è necessario controllare la proprietà `CanBePooled` prima di aggiungere di nuovo l'oggetto al pool.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-178">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```csharp  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="0a7f1-179">Poiché lo sviluppatore del servizio può decidere se un oggetto può essere inserito in un pool, il conteggio degli oggetti nel pool in un determinato momento può essere inferiore alla dimensione minima.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-179">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="0a7f1-180">È pertanto necessario controllare se il conteggio degli oggetti è inferiore al livello minimo ed eseguire l'inizializzazione necessaria nella procedura di pulizia.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-180">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```csharp  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="0a7f1-181">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-181">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="0a7f1-182">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-182">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0a7f1-183">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0a7f1-183">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0a7f1-184">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0a7f1-184">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0a7f1-185">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0a7f1-185">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0a7f1-186">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0a7f1-186">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0a7f1-187">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0a7f1-188">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-188">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0a7f1-189">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0a7f1-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0a7f1-190">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0a7f1-190">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
