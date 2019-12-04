---
title: Durata personalizzata
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 8625877d9b4d05d5cf06af2c9f8ef10f701e98db
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715473"
---
# <a name="custom-lifetime"></a><span data-ttu-id="5ed17-102">Durata personalizzata</span><span class="sxs-lookup"><span data-stu-id="5ed17-102">Custom lifetime</span></span>

<span data-ttu-id="5ed17-103">In questo esempio viene illustrato come scrivere un'estensione Windows Communication Foundation (WCF) per fornire servizi di durata personalizzati per le istanze del servizio WCF condivise.</span><span class="sxs-lookup"><span data-stu-id="5ed17-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed17-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="5ed17-105">Istanze condivise</span><span class="sxs-lookup"><span data-stu-id="5ed17-105">Shared instancing</span></span>

<span data-ttu-id="5ed17-106">WCF offre diverse modalità di istanza per le istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ed17-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="5ed17-107">La modalità di istanza condivisa descritta in questo articolo consente di condividere un'istanza del servizio tra più canali.</span><span class="sxs-lookup"><span data-stu-id="5ed17-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="5ed17-108">I client possono contattare un metodo factory nel servizio e creare un nuovo canale per avviare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="5ed17-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="5ed17-109">Il frammento di codice seguente mostra in che modo un'applicazione client crea un nuovo canale per un'istanza del servizio esistente:</span><span class="sxs-lookup"><span data-stu-id="5ed17-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="5ed17-110">A differenza di altre modalità di istanza, la modalità istanze condivise dispone di un modo univoco di rilascio di istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ed17-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="5ed17-111">Per impostazione predefinita, quando tutti i canali vengono chiusi per un <xref:System.ServiceModel.InstanceContext>, il runtime del servizio WCF verifica se il <xref:System.ServiceModel.InstanceContextMode> del servizio è configurato per <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession>e, in caso affermativo, rilascia l'istanza e dichiara le risorse.</span><span class="sxs-lookup"><span data-stu-id="5ed17-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="5ed17-112">Se viene utilizzato un <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> personalizzato, WCF richiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> dell'implementazione del provider prima di rilasciare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="5ed17-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="5ed17-113">Se <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> restituisce `true` l'istanza viene rilasciata, in caso contrario l'implementazione di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è responsabile della notifica del `Dispatcher` dello stato inattivo tramite un metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="5ed17-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="5ed17-114">Questa operazione viene eseguita chiamando il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> del provider.</span><span class="sxs-lookup"><span data-stu-id="5ed17-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="5ed17-115">Questo esempio illustra come è possibile ritardare il rilascio del <xref:System.ServiceModel.InstanceContext> con un timeout di inattività di 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="5ed17-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="5ed17-116">Estensione di InstanceContext</span><span class="sxs-lookup"><span data-stu-id="5ed17-116">Extending the InstanceContext</span></span>

<span data-ttu-id="5ed17-117">In WCF <xref:System.ServiceModel.InstanceContext> è il collegamento tra l'istanza del servizio e la `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="5ed17-118">WCF consente di estendere questo componente di runtime aggiungendo un nuovo stato o comportamento mediante il modello di oggetti estensibili.</span><span class="sxs-lookup"><span data-stu-id="5ed17-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="5ed17-119">Il modello a oggetti estendibile viene usato in WCF per estendere le classi di runtime esistenti con nuove funzionalità o per aggiungere nuove funzionalità di stato a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5ed17-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="5ed17-120">Nel modello di oggetti estensibili sono disponibili tre interfacce: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> e <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="5ed17-121">L'interfaccia <xref:System.ServiceModel.IExtensibleObject%601> viene implementata dagli oggetti per consentire le estensioni che ne personalizzano la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5ed17-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="5ed17-122">L'interfaccia <xref:System.ServiceModel.IExtension%601> viene implementata da oggetti che possono essere estensioni di classi di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="5ed17-123">Infine, l'interfaccia <xref:System.ServiceModel.IExtensionCollection%601> è una raccolta di implementazioni di <xref:System.ServiceModel.IExtension%601> che consente di recuperare un'implementazione di <xref:System.ServiceModel.IExtension%601> in base al relativo tipo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="5ed17-124">Pertanto, per estendere il <xref:System.ServiceModel.InstanceContext>, è necessario implementare l'interfaccia <xref:System.ServiceModel.IExtension%601>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="5ed17-125">In questo progetto di esempio, la classe `CustomLeaseExtension` contiene questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="5ed17-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="5ed17-126">L'interfaccia <xref:System.ServiceModel.IExtension%601> dispone di due metodi: <xref:System.ServiceModel.IExtension%601.Attach%2A> e <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="5ed17-127">Come implicano i nomi, questi due metodi vengono chiamati quando il runtime connette e disconnette l'estensione a un'istanza della classe <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="5ed17-128">In questo esempio, il metodo `Attach` viene utilizzato per tenere traccia dell'oggetto <xref:System.ServiceModel.InstanceContext> appartenente all'istanza corrente dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="5ed17-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="5ed17-129">Inoltre, è necessario aggiungere l'implementazione necessaria all'estensione per fornire il supporto di durata estesa.</span><span class="sxs-lookup"><span data-stu-id="5ed17-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="5ed17-130">Pertanto, l'interfaccia `ICustomLease` viene dichiarata con i metodi desiderati ed è implementata nella classe `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="5ed17-131">Quando WCF richiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> nell'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, questa chiamata viene indirizzata al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> della `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="5ed17-132">Quindi, il `CustomLeaseExtension` controlla lo stato privato per verificare se il <xref:System.ServiceModel.InstanceContext> è inattivo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="5ed17-133">Se è inattivo, restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="5ed17-134">In caso contrario, viene avviato un timer per un tempo specificato della durata estesa.</span><span class="sxs-lookup"><span data-stu-id="5ed17-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

<span data-ttu-id="5ed17-135">Nell'evento `Elapsed` del timer, la funzione di callback nel Dispatcher viene chiamata per avviare un altro ciclo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="5ed17-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="5ed17-136">Non è possibile rinnovare il timer in esecuzione quando arriva un nuovo messaggio per l'istanza spostata allo stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="5ed17-137">L'esempio implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> per intercettare le chiamate al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> e indirizzarle a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="5ed17-138">L'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è inclusa nella classe `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="5ed17-139">Il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> viene richiamato quando WCF sta per rilasciare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ed17-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="5ed17-140">Tuttavia, esiste solo un'istanza di una specifica implementazione `ISharedSessionInstance` nella raccolta <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> di ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="5ed17-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="5ed17-141">Ciò significa che non esiste alcun modo per sapere se il <xref:System.ServiceModel.InstanceContext> viene chiuso al momento in cui WCF controlla il metodo di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="5ed17-142">Pertanto, in questo esempio viene utilizzato il blocco dei thread per serializzare le richieste al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ed17-143">L'utilizzo di blocchi di thread non è un approccio consigliato perché la serializzazione può influenzare negativamente le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ed17-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="5ed17-144">Un campo membro privato viene usato nella classe `CustomLifetimeLease` per tenere traccia dello stato di inattività e viene restituito dal metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="5ed17-145">Ogni volta che viene chiamato il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>, viene restituito il campo `isIdle` e viene reimpostato il `false`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="5ed17-146">È essenziale impostare questo valore su `false` per assicurarsi che il dispatcher chiami il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="5ed17-147">Se il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> restituisce `false`, il dispatcher registra una funzione di callback utilizzando il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="5ed17-148">Tale metodo riceve un riferimento al <xref:System.ServiceModel.InstanceContext> rilasciato.</span><span class="sxs-lookup"><span data-stu-id="5ed17-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="5ed17-149">Pertanto, il codice di esempio può eseguire una query sull'estensione del tipo di `ICustomLease` e controllare la proprietà `ICustomLease.IsIdle` nello stato esteso.</span><span class="sxs-lookup"><span data-stu-id="5ed17-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

<span data-ttu-id="5ed17-150">Prima di controllare la proprietà `ICustomLease.IsIdle`, è necessario impostare la proprietà di callback perché è essenziale per `CustomLeaseExtension` inviare una notifica al dispatcher quando diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="5ed17-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="5ed17-151">Se `ICustomLease.IsIdle` restituisce `true`, il membro privato `isIdle` viene semplicemente impostato in `CustomLifetimeLease` su `true` e chiama il metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="5ed17-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="5ed17-152">Poiché il codice include un blocco, gli altri thread non possono modificare il valore di questo membro privato.</span><span class="sxs-lookup"><span data-stu-id="5ed17-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="5ed17-153">Il dispatcher successivo chiama il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, restituisce `true` e consente al dispatcher di rilasciare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="5ed17-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="5ed17-154">Una volta completato il lavoro di base per l'estensione personalizzata, quest'ultima deve essere associata al modello del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ed17-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="5ed17-155">Per associare l'implementazione di `CustomLeaseExtension` al <xref:System.ServiceModel.InstanceContext>, WCF fornisce l'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> per eseguire il bootstrap dei <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="5ed17-156">Nell'esempio, la classe `CustomLeaseInitializer` implementa tale interfaccia e aggiunge un'istanza di `CustomLeaseExtension` alla raccolta <xref:System.ServiceModel.InstanceContext.Extensions%2A> dalla sola inizializzazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="5ed17-157">Questo metodo viene chiamato dal dispatcher durante l'inizializzazione di <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="5ed17-158">Infine, l'implementazione del <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> viene associata al modello del servizio usando l'implementazione di <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5ed17-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="5ed17-159">Tale implementazione viene posizionata nella classe `CustomLeaseTimeAttribute` e deriva dalla classe di base <xref:System.Attribute> per esporre questo comportamento come attributo.</span><span class="sxs-lookup"><span data-stu-id="5ed17-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="5ed17-160">Questo comportamento può essere aggiunto a una classe del servizio di esempio mediante annotazione con l'attributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="5ed17-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="5ed17-161">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="5ed17-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="5ed17-162">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="5ed17-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5ed17-163">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="5ed17-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5ed17-164">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ed17-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="5ed17-165">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ed17-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="5ed17-166">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5ed17-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ed17-167">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5ed17-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5ed17-168">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5ed17-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5ed17-169">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="5ed17-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5ed17-170">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5ed17-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
