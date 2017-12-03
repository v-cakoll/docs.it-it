---
title: Durata personalizzata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2538a9c483b949dfef1c60bd2225f5daf4e01117
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="custom-lifetime"></a><span data-ttu-id="1815b-102">Durata personalizzata</span><span class="sxs-lookup"><span data-stu-id="1815b-102">Custom Lifetime</span></span>
<span data-ttu-id="1815b-103">In questo esempio viene descritto come scrivere un'estensione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per fornire servizi di durata personalizzata per le istanze del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] condivise.</span><span class="sxs-lookup"><span data-stu-id="1815b-103">This sample demonstrates how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extension to provide custom lifetime services for shared [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1815b-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1815b-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="1815b-105">Istanze condivise</span><span class="sxs-lookup"><span data-stu-id="1815b-105">Shared Instancing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1815b-106"> offre diverse modalità di istanza per le istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="1815b-106"> offers several instancing modes for your service instances.</span></span> <span data-ttu-id="1815b-107">La modalità istanze condivise analizzata in questo argomento offre un modo per condividere un'istanza del servizio tra più canali.</span><span class="sxs-lookup"><span data-stu-id="1815b-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="1815b-108">I client possono risolvere l'indirizzo dell'endpoint dell'istanza a livello locale o possono contattare un metodo factory nel servizio per ottenere l'indirizzo dell'endpoint di un'istanza in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1815b-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="1815b-109">Una volta ottenuto l'indirizzo dell'endpoint, possono creare un nuovo canale e avviare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="1815b-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="1815b-110">Il frammento di codice seguente mostra la creazione di un nuovo canale in un'istanza del servizio esistente da parte di un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="1815b-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="1815b-111">A differenza di altre modalità di istanza, la modalità istanze condivise dispone di un modo univoco di rilascio di istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="1815b-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="1815b-112">Quando tutti i canali sono chiusi per un'istanza, il runtime del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] avvia un timer.</span><span class="sxs-lookup"><span data-stu-id="1815b-112">When all the channels are closed for an instance, the service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime starts a timer.</span></span> <span data-ttu-id="1815b-113">Se nessuna connessione viene effettuata prima della scadenza del timeout, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene rilasciata l'istanza e viene effettuata la richiesta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="1815b-113">If nobody makes a connection before the timeout expires, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] releases the instance and claims the resources.</span></span> <span data-ttu-id="1815b-114">Come parte della routine di chiusura, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene richiamato il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> di tutte le implementazioni di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> prima di rilasciare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="1815b-114">As a part of the teardown procedure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="1815b-115">Se tutte le implementazioni restituiscono `true`, l'istanza viene rilasciata.</span><span class="sxs-lookup"><span data-stu-id="1815b-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="1815b-116">In caso contrario, l'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è responsabile della notifica al `Dispatcher` dello stato inattivo tramite un metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="1815b-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="1815b-117">Per impostazione predefinita, il valore di timeout inattivo di <xref:System.ServiceModel.InstanceContext> è un minuto.</span><span class="sxs-lookup"><span data-stu-id="1815b-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="1815b-118">In questo esempio viene tuttavia illustrato come estendere tale valore mediante un'estensione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1815b-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="1815b-119">Estensione di InstanceContext</span><span class="sxs-lookup"><span data-stu-id="1815b-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="1815b-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] l'oggetto <xref:System.ServiceModel.InstanceContext> è il collegamento tra l'istanza del servizio e `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="1815b-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1815b-121"> consente di estendere tale componente di runtime aggiungendo un nuovo stato o comportamento mediante il modello di oggetti estensibili.</span><span class="sxs-lookup"><span data-stu-id="1815b-121"> allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="1815b-122">Questo modello viene utilizzato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per estendere le classi del runtime esistenti con nuove funzionalità oppure per aggiungere nuove funzionalità di stato a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1815b-122">The extensible object pattern is used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="1815b-123">Nel modello di oggetti estensibili sono disponibili tre interfacce: `IExtensibleObject<T>`, `IExtension<T>` e `IExtensionCollection<T>`.</span><span class="sxs-lookup"><span data-stu-id="1815b-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="1815b-124">L'interfaccia `IExtensibleObject<T>` viene implementata da oggetti che consentono alle estensioni di personalizzare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1815b-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="1815b-125">L'interfaccia `IExtension<T>` viene implementata da oggetti che possono essere estensioni di classi di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="1815b-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="1815b-126">Infine, l'interfaccia `IExtensionCollection<T>` è una raccolta di `IExtensions` che consente di recuperare `IExtensions` in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="1815b-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="1815b-127">Per estendere <xref:System.ServiceModel.InstanceContext>, è pertanto necessario implementare l'interfaccia `IExtension`.</span><span class="sxs-lookup"><span data-stu-id="1815b-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="1815b-128">In questo progetto di esempio la classe `CustomLeaseExtension` include tale implementazione.</span><span class="sxs-lookup"><span data-stu-id="1815b-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="1815b-129">L'interfaccia `IExtension` dispone di due metodi: `Attach` e `Detach`.</span><span class="sxs-lookup"><span data-stu-id="1815b-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="1815b-130">Come implicano i nomi, questi due metodi vengono chiamati quando il runtime connette e disconnette l'estensione a un'istanza della classe <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="1815b-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="1815b-131">In questo esempio, il metodo `Attach` viene utilizzato per tenere traccia dell'oggetto <xref:System.ServiceModel.InstanceContext> appartenente all'istanza corrente dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="1815b-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="1815b-132">Inoltre, è necessario aggiungere l'implementazione necessaria all'estensione per fornire il supporto di durata estesa.</span><span class="sxs-lookup"><span data-stu-id="1815b-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="1815b-133">L'interfaccia `ICustomLease` viene pertanto dichiarata con i metodi desiderati e viene implementata nella classe `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="1815b-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="1815b-134">Quando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> nell'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, tale chiamata viene indirizzata al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> dell'estensione `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="1815b-134">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="1815b-135">`CustomLeaseExtension` controlla quindi lo stato privato per verificare se <xref:System.ServiceModel.InstanceContext> è inattivo.</span><span class="sxs-lookup"><span data-stu-id="1815b-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="1815b-136">Se è inattivo, viene restituito `true`.</span><span class="sxs-lookup"><span data-stu-id="1815b-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="1815b-137">In caso contrario, viene avviato un timer per un tempo specificato della durata estesa.</span><span class="sxs-lookup"><span data-stu-id="1815b-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
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
  
 <span data-ttu-id="1815b-138">Nell'evento `Elapsed` del timer la funzione di callback nel dispatcher viene chiamata per avviare un altro ciclo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="1815b-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="1815b-139">Non è possibile rinnovare in alcun modo il timer in esecuzione all'arrivo di un nuovo messaggio relativo al passaggio dell'istanza nello stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="1815b-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="1815b-140">L'esempio implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> per intercettare le chiamate al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> e indirizzarle a `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="1815b-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="1815b-141">L'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è inclusa nella classe `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="1815b-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="1815b-142">Il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> viene richiamato quando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sta per rilasciare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="1815b-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is about to release the service instance.</span></span> <span data-ttu-id="1815b-143">Tuttavia, esiste solo un'istanza di una specifica implementazione `ISharedSessionInstance` nella raccolta <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> di ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="1815b-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="1815b-144">Ciò significa che non è possibile sapere che <xref:System.ServiceModel.InstanceContext> viene chiuso quando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controlla il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="1815b-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="1815b-145">Questo esempio utilizza pertanto blocchi di thread per serializzare le richieste al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="1815b-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1815b-146">L'utilizzo di blocchi di thread non è un approccio consigliato perché la serializzazione può influenzare negativamente le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1815b-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="1815b-147">Una variabile membro privato viene utilizzata nella classe `CustomLeaseExtension` per rilevare il valore `IsIdle`.</span><span class="sxs-lookup"><span data-stu-id="1815b-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="1815b-148">Ogni volta che viene recuperato il valore di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, il membro privato `IsIdle` viene restituito e reimpostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="1815b-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="1815b-149">È essenziale impostare questo valore su `false` per assicurarsi che il dispatcher chiami il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="1815b-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="1815b-150">Se la proprietà `ISharedSessionLifetime.IsIdle` restituisce `false`, il dispatcher registra una funzione di callback tramite il metodo `NotifyIdle`.</span><span class="sxs-lookup"><span data-stu-id="1815b-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="1815b-151">Tale metodo riceve un riferimento al <xref:System.ServiceModel.InstanceContext> rilasciato.</span><span class="sxs-lookup"><span data-stu-id="1815b-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="1815b-152">Pertanto il codice di esempio può eseguire una query dell'estensione di tipo `ICustomLease` e archiviare la proprietà `ICustomLease.IsIdle` nello stato esteso.</span><span class="sxs-lookup"><span data-stu-id="1815b-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
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
  
 <span data-ttu-id="1815b-153">Prima che la proprietà `ICustomLease.IsIdle` venga verificata, è necessario impostare la proprietà di callback, poiché ciò è essenziale affinché `CustomLeaseExtension` notifichi al dispatcher quando diventa inattiva.</span><span class="sxs-lookup"><span data-stu-id="1815b-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="1815b-154">Se `ICustomLease.IsIdle` restituisce `true`, il membro privato `isIdle` viene semplicemente impostato in `CustomLifetimeLease` su `true` e chiama il metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="1815b-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="1815b-155">Poiché il codice contiene un blocco, gli altri thread non possono modificare il valore del membro privato.</span><span class="sxs-lookup"><span data-stu-id="1815b-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="1815b-156">La volta successiva che il dispatcher controlla `ISharedSessionLifetime.IsIdle`, restituisce `true` e consente al dispatcher di rilasciare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="1815b-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="1815b-157">Una volta completato il lavoro di base per l'estensione personalizzata, quest'ultima deve essere associata al modello del servizio.</span><span class="sxs-lookup"><span data-stu-id="1815b-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="1815b-158">Per collegare l'implementazione `CustomLeaseExtension` a <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce l'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> per eseguire l'avvio di <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="1815b-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="1815b-159">Nell'esempio, la classe `CustomLeaseInitializer` implementa tale interfaccia e aggiunge un'istanza di `CustomLeaseExtension` alla raccolta <xref:System.ServiceModel.InstanceContext.Extensions%2A> dalla sola inizializzazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="1815b-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="1815b-160">Questo metodo viene chiamato dal dispatcher durante l'inizializzazione di <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="1815b-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="1815b-161">Infine il `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` e <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementazioni sono associati a un massimo del modello di servizio utilizzando il <xref:System.ServiceModel.Description.IServiceBehavior> implementazione.</span><span class="sxs-lookup"><span data-stu-id="1815b-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="1815b-162">Tale implementazione viene posizionata nella classe `CustomLeaseTimeAttribute` e deriva dalla classe di base `Attribute` per esporre questo comportamento come attributo.</span><span class="sxs-lookup"><span data-stu-id="1815b-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="1815b-163">Nel metodo `IServiceBehavior.ApplyBehavior`, le istanze delle implementazioni di <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> e `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` vengono aggiunte rispettivamente alle raccolte `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` e <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> di <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime>.</span><span class="sxs-lookup"><span data-stu-id="1815b-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="1815b-164">Questo comportamento può essere aggiunto a una classe del servizio di esempio mediante annotazione con l'attributo `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="1815b-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="1815b-165">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="1815b-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="1815b-166">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="1815b-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1815b-167">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1815b-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1815b-168">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1815b-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1815b-169">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1815b-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="1815b-170">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1815b-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1815b-171">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1815b-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1815b-172">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1815b-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1815b-173">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1815b-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1815b-174">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1815b-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="1815b-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1815b-175">See Also</span></span>
