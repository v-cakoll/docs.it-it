---
title: Pooling
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: 82b81637deb0715d19109794348d2a2bcda7f0d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594621"
---
# <a name="pooling"></a><span data-ttu-id="1e703-102">Pooling</span><span class="sxs-lookup"><span data-stu-id="1e703-102">Pooling</span></span>
<span data-ttu-id="1e703-103">In questo esempio viene illustrato come estendere Windows Communication Foundation (WCF) per supportare il pool di oggetti.</span><span class="sxs-lookup"><span data-stu-id="1e703-103">This sample demonstrates how to extend Windows Communication Foundation (WCF) to support object pooling.</span></span> <span data-ttu-id="1e703-104">L'esempio illustra come creare un attributo sintatticamente e semanticamente simile alla funzionalità dell'attributo `ObjectPoolingAttribute` di Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="1e703-104">The sample demonstrates how to create an attribute that is syntactically and semantically similar to the `ObjectPoolingAttribute` attribute functionality of Enterprise Services.</span></span> <span data-ttu-id="1e703-105">Il pool degli oggetti può fornire una spinta notevole alle prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1e703-105">Object pooling can provide a dramatic boost to an application's performance.</span></span> <span data-ttu-id="1e703-106">Tuttavia, può avere l'effetto contrario se non utilizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1e703-106">However, it can have the opposite effect if it is not used properly.</span></span> <span data-ttu-id="1e703-107">Il pool degli oggetti consente di ridurre il sovraccarico dovuto alla creazione continua di oggetti frequentemente utilizzati che richiedono un'inizializzazione estesa.</span><span class="sxs-lookup"><span data-stu-id="1e703-107">Object pooling helps reduce the overhead of recreating frequently used objects that require extensive initialization.</span></span> <span data-ttu-id="1e703-108">Tuttavia, se una chiamata a un metodo su un oggetto del pool richiede una quantità considerevole di tempo, il pool degli oggetti mette in coda richieste aggiuntive appena viene raggiunta la dimensione del pool massima.</span><span class="sxs-lookup"><span data-stu-id="1e703-108">However, if a call to a method on a pooled object takes a considerable amount of time to complete, object pooling queues additional requests as soon as the maximum pool size is reached.</span></span> <span data-ttu-id="1e703-109">Pertanto può non riuscire a soddisfare richieste di creazione di oggetti generando un'eccezione di timeout.</span><span class="sxs-lookup"><span data-stu-id="1e703-109">Thus it may fail to serve some object creation requests by throwing a timeout exception.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e703-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1e703-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1e703-111">Il primo passaggio nella creazione di un'estensione WCF consiste nel decidere il punto di estensibilità da usare.</span><span class="sxs-lookup"><span data-stu-id="1e703-111">The first step in creating a WCF extension is to decide the extensibility point to use.</span></span>  
  
 <span data-ttu-id="1e703-112">In WCF il termine *Dispatcher* fa riferimento a un componente runtime responsabile della conversione dei messaggi in arrivo in chiamate al metodo sul servizio dell'utente e della conversione di valori restituiti da tale metodo in un messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="1e703-112">In WCF the term *dispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="1e703-113">Un servizio WCF crea un dispatcher per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e703-113">A WCF service creates a dispatcher for each endpoint.</span></span> <span data-ttu-id="1e703-114">Un client WCF deve usare un dispatcher se il contratto associato a tale client è un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="1e703-114">A WCF client must use a dispatcher if the contract associated with that client is a duplex contract.</span></span>  
  
 <span data-ttu-id="1e703-115">I dispatcher del canale e dell'endpoint offrono estensibilità sul canale e sul contratto esponendo le varie proprietà che controllano il comportamento del dispatcher.</span><span class="sxs-lookup"><span data-stu-id="1e703-115">The channel and endpoint dispatchers offer channel-and contract-wide extensibility by exposing various properties that control the behavior of the dispatcher.</span></span> <span data-ttu-id="1e703-116">La proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> consente inoltre di ispezionare, modificare e personalizzare la modalità di autenticazione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="1e703-116">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> property also enables you to inspect, modify, or customize the dispatching process.</span></span> <span data-ttu-id="1e703-117">Questo esempio si concentra sulla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> che punta all'oggetto che fornisce le istanze della classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-117">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="the-iinstanceprovider"></a><span data-ttu-id="1e703-118">Provider di istanze</span><span class="sxs-lookup"><span data-stu-id="1e703-118">The IInstanceProvider</span></span>  
 <span data-ttu-id="1e703-119">In WCF, il dispatcher crea istanze della classe del servizio usando un oggetto <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> che implementa l' <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1e703-119">In WCF, the dispatcher creates instances of the service class using a <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, which implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="1e703-120">Questa interfaccia ha tre metodi:</span><span class="sxs-lookup"><span data-stu-id="1e703-120">This interface has three methods:</span></span>  
  
- <span data-ttu-id="1e703-121"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: quando un messaggio arriva il dispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> per creare un'istanza della classe del servizio al fine di elaborare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1e703-121"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: When a message arrives the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="1e703-122">La frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e703-122">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="1e703-123">Ad esempio, se la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> è impostata su <xref:System.ServiceModel.InstanceContextMode.PerCall> viene creata una nuova istanza della classe del servizio per elaborare ogni messaggio che arriva, pertanto il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> viene chiamato ogni qualvolta arriva un messaggio.</span><span class="sxs-lookup"><span data-stu-id="1e703-123">For example, if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall> a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="1e703-124"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: questo metodo è identico a quello precedente, salvo che viene richiamato quando non c'è nessun argomento di messaggio.</span><span class="sxs-lookup"><span data-stu-id="1e703-124"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: This is identical to the previous method, except this is invoked when there is no Message argument.</span></span>  
  
- <span data-ttu-id="1e703-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: Quando la durata di un'istanza del servizio è scaduta, il dispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="1e703-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: When a service instance's lifetime has elapsed, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> method.</span></span> <span data-ttu-id="1e703-126">Solo per il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, la frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e703-126">Just like for the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="1e703-127">Pool di oggetti</span><span class="sxs-lookup"><span data-stu-id="1e703-127">The Object Pool</span></span>  
 <span data-ttu-id="1e703-128">Un'implementazione personalizzata della classe <xref:System.ServiceModel.Dispatcher.IInstanceProvider> fornisce la semantica del pool di oggetti necessaria per un servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-128">A custom <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation provides the required object pooling semantics for a service.</span></span> <span data-ttu-id="1e703-129">Pertanto, questo esempio ha un tipo `ObjectPoolingInstanceProvider` che fornisce un'implementazione personalizzata della classe <xref:System.ServiceModel.Dispatcher.IInstanceProvider> per il pool.</span><span class="sxs-lookup"><span data-stu-id="1e703-129">Therefore, this sample has an `ObjectPoolingInstanceProvider` type that provides custom implementation of <xref:System.ServiceModel.Dispatcher.IInstanceProvider> for pooling.</span></span> <span data-ttu-id="1e703-130">Quando `Dispatcher` chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, anziché creare una nuova istanza, l'implementazione personalizzata cerca un oggetto esistente in un pool in memoria</span><span class="sxs-lookup"><span data-stu-id="1e703-130">When the `Dispatcher` calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="1e703-131">che viene restituito se disponibile.</span><span class="sxs-lookup"><span data-stu-id="1e703-131">If one is available, it is returned.</span></span> <span data-ttu-id="1e703-132">In caso contrario, viene creato un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="1e703-132">Otherwise, a new object is created.</span></span> <span data-ttu-id="1e703-133">Nell'esempio di codice seguente viene illustrata l'implementazione di `GetInstance`.</span><span class="sxs-lookup"><span data-stu-id="1e703-133">The implementation for `GetInstance` is shown in the following sample code.</span></span>  
  
```csharp  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;
}  
```  
  
 <span data-ttu-id="1e703-134">L'implementazione personalizzata di `ReleaseInstance` aggiunge l'istanza rilasciata nuovamente al pool e decrementa il valore di `ActiveObjectsCount`.</span><span class="sxs-lookup"><span data-stu-id="1e703-134">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="1e703-135">Il `Dispatcher` può chiamare questi metodi da thread diversi e pertanto sincronizzare l'accesso ai membri del livello della classe, nella classe `ObjectPoolingInstanceProvider` obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1e703-135">The `Dispatcher` can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolingInstanceProvider` class is required.</span></span>  
  
```csharp  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();
    }  
}  
```  
  
 <span data-ttu-id="1e703-136">Il `ReleaseInstance` metodo fornisce una funzionalità di pulizia dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1e703-136">The `ReleaseInstance` method provides a "clean up initialization" feature.</span></span> <span data-ttu-id="1e703-137">Normalmente il pool gestisce un numero minimo di oggetti per la durata del pool.</span><span class="sxs-lookup"><span data-stu-id="1e703-137">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="1e703-138">Ci possono essere, tuttavia, periodi di utilizzo eccessivo che richiedono la creazione di oggetti aggiuntivi nel pool per raggiungere il limite massimo specificato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="1e703-138">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="1e703-139">Successivamente, quando il pool diviene meno attivo, quegli oggetti in surplus possono divenire un sovraccarico aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="1e703-139">Eventually, when the pool becomes less active, those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="1e703-140">Pertanto, quando il conteggio `activeObjectsCount` si azzera, viene avviato un timer, precedentemente inattivo, che inizia ed esegue un ciclo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="1e703-140">Therefore, when the `activeObjectsCount` reaches zero, an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
## <a name="adding-the-behavior"></a><span data-ttu-id="1e703-141">Aggiunta del comportamento.</span><span class="sxs-lookup"><span data-stu-id="1e703-141">Adding the Behavior</span></span>  
 <span data-ttu-id="1e703-142">Le estensioni del livello del dispatcher vengono collegate utilizzando i comportamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e703-142">Dispatcher-layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="1e703-143">Comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-143">Service Behaviors.</span></span> <span data-ttu-id="1e703-144">Essi consentono la personalizzazione del runtime dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-144">These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="1e703-145">Comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e703-145">Endpoint Behaviors.</span></span> <span data-ttu-id="1e703-146">Essi consentono la personalizzazione degli endpoint del servizio, in particolare un canale e un dispatcher dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e703-146">These allow for the customization of service endpoints, specifically a Channel and Endpoint Dispatcher.</span></span>  
  
- <span data-ttu-id="1e703-147">Comportamenti del contratto.</span><span class="sxs-lookup"><span data-stu-id="1e703-147">Contract Behaviors.</span></span> <span data-ttu-id="1e703-148">Essi consentono la personalizzazione di entrambe le classi <xref:System.ServiceModel.Dispatcher.ClientRuntime> e <xref:System.ServiceModel.Dispatcher.DispatchRuntime> rispettivamente sul client e sui servizi.</span><span class="sxs-lookup"><span data-stu-id="1e703-148">These allow for the customization of both <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client and the service respectively.</span></span>  
  
 <span data-ttu-id="1e703-149">Allo scopo di un'estensione del pool di oggetti deve essere creato un comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-149">For the purpose of an object pooling extension a service behavior must be created.</span></span> <span data-ttu-id="1e703-150">I comportamenti del servizio vengono creati implementando l'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1e703-150">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="1e703-151">Ci sono molti modi per rendere consapevole il modello dei servizi dei comportamenti personalizzati:</span><span class="sxs-lookup"><span data-stu-id="1e703-151">There are several ways to make the service model aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="1e703-152">Utilizzo di un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e703-152">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="1e703-153">Aggiunto imperativamente alla raccolta di comportamenti della descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-153">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="1e703-154">Estensione dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1e703-154">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="1e703-155">Questo esempio utilizza un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1e703-155">This sample uses a custom attribute.</span></span> <span data-ttu-id="1e703-156">Quando la classe <xref:System.ServiceModel.ServiceHost> viene costruita esamina gli attributi utilizzati nella definizione del tipo del servizio e aggiunge i comportamenti disponibili alla raccolta di comportamenti della descrizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-156">When the <xref:System.ServiceModel.ServiceHost> is constructed it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="1e703-157">L'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior> contiene tre metodi: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> e <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e703-157">The interface <xref:System.ServiceModel.Description.IServiceBehavior> has three methods in it -- <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>, and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="1e703-158">Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> viene utilizzato per assicurare che il comportamento possa essere applicato al servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-158">The <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> method is used to ensure that the behavior can be applied to the service.</span></span> <span data-ttu-id="1e703-159">In questo esempio, l'implementazione assicura che il servizio non sia configurato con <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="1e703-159">In this sample, the implementation ensures that the service is not configured with <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span> <span data-ttu-id="1e703-160">Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> viene utilizzato per configurare le associazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-160">The <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> method is used to configure the service's bindings.</span></span> <span data-ttu-id="1e703-161">Non è obbligatorio in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="1e703-161">It is not required in this scenario.</span></span> <span data-ttu-id="1e703-162">Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> viene utilizzato per configurare i dispatcher del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-162">The <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> is used to configure the service's dispatchers.</span></span> <span data-ttu-id="1e703-163">Questo metodo viene chiamato da WCF quando <xref:System.ServiceModel.ServiceHost> è in corso l'inizializzazione di.</span><span class="sxs-lookup"><span data-stu-id="1e703-163">This method is called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="1e703-164">I parametri seguenti vengono passati in questo metodo:</span><span class="sxs-lookup"><span data-stu-id="1e703-164">The following parameters are passed into this method:</span></span>  
  
- <span data-ttu-id="1e703-165">`Description`: questo argomento fornisce la descrizione del servizio per l'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="1e703-165">`Description`: This argument provides the service description for the entire service.</span></span> <span data-ttu-id="1e703-166">Può essere utilizzato per controllare dati della descrizione sugli endpoint del servizio, contratti, associazioni e altri dati.</span><span class="sxs-lookup"><span data-stu-id="1e703-166">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data.</span></span>  
  
- <span data-ttu-id="1e703-167">`ServiceHostBase`: questo argomento fornisce la classe <xref:System.ServiceModel.ServiceHostBase> attualmente in fase di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1e703-167">`ServiceHostBase`: This argument provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="1e703-168">Nell'implementazione personalizzata della classe <xref:System.ServiceModel.Description.IServiceBehavior> viene creata una nuova istanza di `ObjectPoolingInstanceProvider` e viene assegnata alla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> in ogni <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in ServiceHostBase.</span><span class="sxs-lookup"><span data-stu-id="1e703-168">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation a new instance of `ObjectPoolingInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in the ServiceHostBase.</span></span>  
  
```csharp  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior
    // (this.throttlingBehavior==null), it should have initialized
    // a single ServiceThrottle on all ChannelDispatchers.
    // As we loop through the ChannelDispatchers, we verify that
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all
            // endpoints. If there were others, we could not enforce
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                throttle ??= cd.ServiceThrottle;
                if (cd.ServiceThrottle == null)  
                {  
                    throw new
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 <span data-ttu-id="1e703-169">Oltre a un'implementazione della classe <xref:System.ServiceModel.Description.IServiceBehavior>, la classe <xref:System.EnterpriseServices.ObjectPoolingAttribute> ha molti membri per personalizzare il pool di oggetti utilizzando gli argomenti dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="1e703-169">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the <xref:System.EnterpriseServices.ObjectPoolingAttribute> class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="1e703-170">Questi membri includono <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> e <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, per corrispondere al set di funzionalità del pool di oggetti fornito da Enterprise Services .NET.</span><span class="sxs-lookup"><span data-stu-id="1e703-170">These members include <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A>, and <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="1e703-171">Il comportamento del pool di oggetti può ora essere aggiunto a un servizio WCF annotando l'implementazione del servizio con l'attributo personalizzato appena creato `ObjectPooling` .</span><span class="sxs-lookup"><span data-stu-id="1e703-171">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```csharp  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="1e703-172">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="1e703-172">Running the Sample</span></span>  
 <span data-ttu-id="1e703-173">L'esempio illustra i vantaggi a livello di prestazioni che possono essere raggiunti utilizzando i pool di oggetti in alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="1e703-173">The sample demonstrates the performance benefits that can be gained by using object pooling in certain scenarios.</span></span>  
  
 <span data-ttu-id="1e703-174">L'applicazione di servizio implementa due servizi: `WorkService` e `ObjectPooledWorkService`.</span><span class="sxs-lookup"><span data-stu-id="1e703-174">The service application implements two services -- `WorkService` and `ObjectPooledWorkService`.</span></span> <span data-ttu-id="1e703-175">Entrambi i servizi condividono la stessa implementazione. Richiedono entrambi una lunga inizializzazione e quindi espongono un metodo `DoWork()` che è relativamente conveniente.</span><span class="sxs-lookup"><span data-stu-id="1e703-175">Both services share the same implementation -- they both require expensive initialization and then expose a `DoWork()` method that is relatively cheap.</span></span> <span data-ttu-id="1e703-176">La sola differenza è che `ObjectPooledWorkService` ha un pool di oggetti configurato:</span><span class="sxs-lookup"><span data-stu-id="1e703-176">The only difference is that the `ObjectPooledWorkService` has object pooling configured:</span></span>  
  
```csharp  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }
}  
```  
  
 <span data-ttu-id="1e703-177">Quando si esegue il client, effettua la chiamata a `WorkService` 5 volte.</span><span class="sxs-lookup"><span data-stu-id="1e703-177">When you run the client, it times calling the `WorkService` 5 times.</span></span> <span data-ttu-id="1e703-178">Quindi effettua la chiamata a `ObjectPooledWorkService` 5 volte.</span><span class="sxs-lookup"><span data-stu-id="1e703-178">It then times calling the `ObjectPooledWorkService` 5 times.</span></span> <span data-ttu-id="1e703-179">Viene infine visualizzata la differenza:</span><span class="sxs-lookup"><span data-stu-id="1e703-179">The difference in time is then displayed:</span></span>  
  
```console
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
> <span data-ttu-id="1e703-180">La prima volta che il client viene eseguito, entrambi i servizi sembrano avere la stessa durata.</span><span class="sxs-lookup"><span data-stu-id="1e703-180">The first time the client is run both services appear to take about the same amount of time.</span></span> <span data-ttu-id="1e703-181">Se si esegue nuovamente l'esempio, è possibile vedere che `ObjectPooledWorkService` restituisce molto più rapidamente perché un'istanza di quell'oggetto già esiste nel pool.</span><span class="sxs-lookup"><span data-stu-id="1e703-181">If you re-run the sample, you can see that the `ObjectPooledWorkService` returns much quicker because an instance of that object already exists in the pool.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1e703-182">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1e703-182">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1e703-183">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1e703-183">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1e703-184">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1e703-184">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1e703-185">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1e703-185">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e703-186">Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.</span><span class="sxs-lookup"><span data-stu-id="1e703-186">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1e703-187">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1e703-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e703-188">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1e703-188">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1e703-189">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1e703-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e703-190">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1e703-190">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
