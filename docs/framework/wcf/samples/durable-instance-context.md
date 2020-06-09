---
title: Contesto dell'istanza durevole
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: 567ca62d48e80993328548b11f8b59c4fcd355fe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600594"
---
# <a name="durable-instance-context"></a><span data-ttu-id="6a583-102">Contesto dell'istanza durevole</span><span class="sxs-lookup"><span data-stu-id="6a583-102">Durable Instance Context</span></span>

<span data-ttu-id="6a583-103">In questo esempio viene illustrato come personalizzare il runtime di Windows Communication Foundation (WCF) per abilitare contesti dell'istanza durevoli.</span><span class="sxs-lookup"><span data-stu-id="6a583-103">This sample demonstrates how to customize the Windows Communication Foundation (WCF) runtime to enable durable instance contexts.</span></span> <span data-ttu-id="6a583-104">SQL Server 2005 viene utilizzato come archivio di backup (in questo caso SQL Server 2005 Express).</span><span class="sxs-lookup"><span data-stu-id="6a583-104">It uses SQL Server 2005 as its backing store (SQL Server 2005 Express in this case).</span></span> <span data-ttu-id="6a583-105">Tuttavia, viene fornito anche un modo di accedere ai meccanismi di archiviazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6a583-105">However, it also provides a way to access custom storage mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="6a583-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6a583-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="6a583-107">Questo esempio prevede l'estensione del livello del canale e del livello del modello di servizio di WCF.</span><span class="sxs-lookup"><span data-stu-id="6a583-107">This sample involves extending both the channel layer and the service model layer of the WCF.</span></span> <span data-ttu-id="6a583-108">È pertanto necessario comprendere i concetti sottostanti prima di entrare nei dettagli dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-108">Therefore it is necessary to understand the underlying concepts before going into the implementation details.</span></span>

<span data-ttu-id="6a583-109">I contesti dell'istanza durevoli si trovano spesso in situazioni del mondo reale.</span><span class="sxs-lookup"><span data-stu-id="6a583-109">Durable instance contexts can be found in the real world scenarios quite often.</span></span> <span data-ttu-id="6a583-110">Un'applicazione del carrello acquisti, ad esempio, ha la possibilità di sospendere la spesa a metà e di continuare in un altro giorno.</span><span class="sxs-lookup"><span data-stu-id="6a583-110">A shopping cart application, for example, has the ability to pause shopping halfway through and continue it on another day.</span></span> <span data-ttu-id="6a583-111">Quando si visita il carrello degli acquisti il giorno successivo, il contesto originale viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="6a583-111">So that when we visit the shopping cart the next day, our original context is restored.</span></span> <span data-ttu-id="6a583-112">È importante notare che l'applicazione di carrello degli acquisti (sul server) non mantiene l'istanza del carrello degli acquisti mentre si è disconnessi.</span><span class="sxs-lookup"><span data-stu-id="6a583-112">It is important to note that the shopping cart application (on the server) does not maintain the shopping cart instance while we are disconnected.</span></span> <span data-ttu-id="6a583-113">Invece, lo stato viene salvato in un archivio durevole e viene utilizzato per generare una nuova istanza del contesto ripristinato.</span><span class="sxs-lookup"><span data-stu-id="6a583-113">Instead, it persists its state into a durable storage media and uses it when constructing a new instance for the restored context.</span></span> <span data-ttu-id="6a583-114">Pertanto l'istanza del servizio che può essere utile allo stesso contesto non corrisponde all'istanza precedente (ovvero, non ha lo stesso indirizzo di memoria).</span><span class="sxs-lookup"><span data-stu-id="6a583-114">Therefore the service instance that may service for the same context is not the same as the previous instance (that is, it does not have the same memory address).</span></span>

<span data-ttu-id="6a583-115">Il contesto dell'istanza durevole è reso possibile da un piccolo protocollo che consente al client e al servizio di scambiare un ID del contesto.</span><span class="sxs-lookup"><span data-stu-id="6a583-115">Durable instance context is made possible by a small protocol that exchanges a context ID between the client and service.</span></span> <span data-ttu-id="6a583-116">Questo ID del contesto viene creato sul client e trasmesso al servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-116">This context ID is created on the client and transmitted to the service.</span></span> <span data-ttu-id="6a583-117">Quando viene creata l'istanza del servizio, il runtime del servizio tenta di caricare lo stato salvato che corrisponde a questo ID del contesto da un'archiviazione permanente (per impostazione predefinita corrisponde a un database SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="6a583-117">When the service instance is created, the service runtime tries to load the persisted state that corresponds to this context ID from a persistent storage (by default it is a SQL Server 2005 database).</span></span> <span data-ttu-id="6a583-118">Se non è disponibile alcuno stato, la nuova istanza avrà lo stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="6a583-118">If no state is available, the new instance has its default state.</span></span> <span data-ttu-id="6a583-119">L'implementazione del servizio utilizza un attributo personalizzato per contrassegnare le operazioni che modificano il runtime del servizio, in modo che la fase di esecuzione possa salvare l'istanza del servizio dopo averle richiamate.</span><span class="sxs-lookup"><span data-stu-id="6a583-119">The service implementation uses a custom attribute to mark operations that change the state of the service implementation so that the runtime can save the service instance after invoking them.</span></span>

<span data-ttu-id="6a583-120">Dalla descrizione precedente è possibile individuare i due passaggi necessari per raggiungere l'obiettivo:</span><span class="sxs-lookup"><span data-stu-id="6a583-120">By the previous description, two steps can easily be distinguished to achieve the goal:</span></span>

1. <span data-ttu-id="6a583-121">Modificare il messaggio che va in transito per portare l'ID del contesto.</span><span class="sxs-lookup"><span data-stu-id="6a583-121">Change the message that goes on the wire to carry the context ID.</span></span>

2. <span data-ttu-id="6a583-122">Modificare il comportamento locale del servizio per implementare la logica dell'istanza personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6a583-122">Change the service local behavior to implement custom instancing logic.</span></span>

<span data-ttu-id="6a583-123">Poiché la prima nell'elenco influiscono sui messaggi in transito, è necessario implementarla come canale personalizzato e associarla al livello del canale.</span><span class="sxs-lookup"><span data-stu-id="6a583-123">Because the first one in the list affects the messages on the wire, it should be implemented as a custom channel and be hooked up to the channel layer.</span></span> <span data-ttu-id="6a583-124">Il secondo passaggio influisce solo sul comportamento locale del servizio e pertanto può essere implementato estendendo vari punti di estensibilità del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-124">The latter only affects the service local behavior and therefore can be implemented by extending several service extensibility points.</span></span> <span data-ttu-id="6a583-125">Nelle prossime sezioni verranno illustrate tutte queste estensioni.</span><span class="sxs-lookup"><span data-stu-id="6a583-125">In the next few sections, each of these extensions are discussed.</span></span>

## <a name="durable-instancecontext-channel"></a><span data-ttu-id="6a583-126">Canale InstanceContext durevole</span><span class="sxs-lookup"><span data-stu-id="6a583-126">Durable InstanceContext Channel</span></span>

<span data-ttu-id="6a583-127">La prima cosa da notare è l'estensione del livello del canale.</span><span class="sxs-lookup"><span data-stu-id="6a583-127">The first thing to look at is a channel layer extension.</span></span> <span data-ttu-id="6a583-128">Il primo passaggio per creare un canale personalizzato consiste nel decidere la struttura della comunicazione del canale.</span><span class="sxs-lookup"><span data-stu-id="6a583-128">The first step in writing a custom channel is to decide the communication structure of the channel.</span></span> <span data-ttu-id="6a583-129">Quando viene introdotto un nuovo protocollo wire, il canale dovrebbe funzionare con quasi tutti gli altri canali nello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="6a583-129">As a new wire protocol is being introduced, the channel should work with almost any other channel in the channel stack.</span></span> <span data-ttu-id="6a583-130">È pertanto necessario che supporti tutti i modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a583-130">Therefore it should support all the message exchange patterns.</span></span> <span data-ttu-id="6a583-131">Tuttavia, la funzionalità principale del canale rimane la stessa, indipendentemente dalla struttura della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-131">However, the core functionality of the channel is the same regardless of its communication structure.</span></span> <span data-ttu-id="6a583-132">Più specificamente, deve scrivere l'ID del contesto ai messaggi dal client e leggere questo ID del contesto dai messaggi dal servizio, per poi passarlo ai livelli superiori.</span><span class="sxs-lookup"><span data-stu-id="6a583-132">More specifically, from the client it should write the context ID to the messages and from the service it should read this context ID from the messages and pass it to the upper levels.</span></span> <span data-ttu-id="6a583-133">Per questa ragione, viene creata una classe `DurableInstanceContextChannelBase` che rappresenta la classe di base astratta per tutte le implementazioni dei canali del contesto dell'istanza durevole.</span><span class="sxs-lookup"><span data-stu-id="6a583-133">Because of that, a `DurableInstanceContextChannelBase` class is created that acts as the abstract base class for all durable instance context channel implementations.</span></span> <span data-ttu-id="6a583-134">Questa classe contiene le funzioni comuni di gestione del computer di stato e due membri protetti per applicare e leggere le informazioni di contesto a e da i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a583-134">This class contains the common state machine management functions and two protected members to apply and read the context information to and from messages.</span></span>

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

<span data-ttu-id="6a583-135">Questi due metodi si avvalgono delle implementazioni `IContextManager` per scrivere e leggere l'ID del contesto a o da il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6a583-135">These two methods make use of `IContextManager` implementations to write and read the context ID to or from the message.</span></span> <span data-ttu-id="6a583-136">( `IContextManager` è un'interfaccia personalizzata utilizzata per definire il contratto per tutti i gestori del contesto). Il canale può includere l'ID del contesto in un'intestazione SOAP personalizzata o in un'intestazione HTTP del cookie.</span><span class="sxs-lookup"><span data-stu-id="6a583-136">(`IContextManager` is a custom interface used to define the contract for all context managers.) The channel can either include the context ID in a custom SOAP header or in an HTTP cookie header.</span></span> <span data-ttu-id="6a583-137">Ogni implementazione dei gestori di contesto eredita dalla classe `ContextManagerBase` che contiene le funzionalità comuni per tutti i gestori del contesto.</span><span class="sxs-lookup"><span data-stu-id="6a583-137">Each context manager implementation inherits from the `ContextManagerBase` class that contains the common functionality for all context managers.</span></span> <span data-ttu-id="6a583-138">Il metodo `GetContextId` in questa classe viene utilizzato per originare l'ID del contesto dal client.</span><span class="sxs-lookup"><span data-stu-id="6a583-138">The `GetContextId` method in this class is used to originate the context ID from the client.</span></span> <span data-ttu-id="6a583-139">Quando un ID del contesto viene originato per la prima volta, questo metodo lo salva in un file di testo il cui nome è costituito dall'indirizzo endpoint remoto (i caratteri del nome file non validi degli URI tipici sono sostituiti con il carattere @).</span><span class="sxs-lookup"><span data-stu-id="6a583-139">When a context ID is originated for the first time, this method saves it into a text file whose name is constructed by the remote endpoint address (the invalid file name characters in the typical URIs are replaced with @ characters).</span></span>

<span data-ttu-id="6a583-140">In un secondo momento, quando l'ID del contesto è necessario allo stesso endpoint remoto, il metodo verifica se esiste un file appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a583-140">Later when the context ID is required for the same remote endpoint, it checks whether an appropriate file exists.</span></span> <span data-ttu-id="6a583-141">Se esiste, il metodo legge l'ID del contesto e termina.</span><span class="sxs-lookup"><span data-stu-id="6a583-141">If it does, it reads the context ID and returns.</span></span> <span data-ttu-id="6a583-142">In caso contrario, restituisce un ID del contesto appena generato e lo salva in un file.</span><span class="sxs-lookup"><span data-stu-id="6a583-142">Otherwise it returns a newly generated context ID and saves it to a file.</span></span> <span data-ttu-id="6a583-143">Con la configurazione predefinita, questi file vengono inseriti in una directory denominata ContextStore, che risiede nella directory temporanea dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6a583-143">With the default configuration, these files are placed in a directory called ContextStore, which resides in the current user's temp directory.</span></span> <span data-ttu-id="6a583-144">Questo percorso è tuttavia configurabile tramite l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-144">However this location is configurable using the binding element.</span></span>

<span data-ttu-id="6a583-145">Il meccanismo utilizzato per trasportare l'ID del contesto è configurabile.</span><span class="sxs-lookup"><span data-stu-id="6a583-145">The mechanism used to transport the context ID is configurable.</span></span> <span data-ttu-id="6a583-146">Può essere scritto nell'intestazione HTTP del cookie o in un'intestazione SOAP personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6a583-146">It could be either written to the HTTP cookie header or to a custom SOAP header.</span></span> <span data-ttu-id="6a583-147">Se si utilizza l'intestazione SOAP personalizzata, è possibile utilizzare questo protocollo con i protocolli non HTTP (ad esempio, TCP o Named pipe).</span><span class="sxs-lookup"><span data-stu-id="6a583-147">The custom SOAP header approach makes it possible to use this protocol with non-HTTP protocols (for example, TCP or Named Pipes).</span></span> <span data-ttu-id="6a583-148">Le due classi `MessageHeaderContextManager` e `HttpCookieContextManager` implementano queste due opzioni.</span><span class="sxs-lookup"><span data-stu-id="6a583-148">There are two classes, namely `MessageHeaderContextManager` and `HttpCookieContextManager`, which implement these two options.</span></span>

<span data-ttu-id="6a583-149">Entrambi scrivono l'ID del contesto nel messaggio in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a583-149">Both of them write the context ID to the message appropriately.</span></span> <span data-ttu-id="6a583-150">Ad esempio, la classe `MessageHeaderContextManager` lo scrive in un'intestazione SOAP del metodo `WriteContext`.</span><span class="sxs-lookup"><span data-stu-id="6a583-150">For example, the `MessageHeaderContextManager` class writes it to a SOAP header in the `WriteContext` method.</span></span>

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

<span data-ttu-id="6a583-151">I metodi `ApplyContext` e `ReadContextId` della classe  `DurableInstanceContextChannelBase` richiamano rispettivamente `IContextManager.ReadContext` e `IContextManager.WriteContext`.</span><span class="sxs-lookup"><span data-stu-id="6a583-151">Both the `ApplyContext` and `ReadContextId` methods in the `DurableInstanceContextChannelBase` class invoke the `IContextManager.ReadContext` and `IContextManager.WriteContext`, respectively.</span></span> <span data-ttu-id="6a583-152">Questi gestori del contesto non vengono creati direttamente dalla classe `DurableInstanceContextChannelBase`.</span><span class="sxs-lookup"><span data-stu-id="6a583-152">However, these context managers are not directly created by the `DurableInstanceContextChannelBase` class.</span></span> <span data-ttu-id="6a583-153">Viene utilizzata la classe `ContextManagerFactory` per eseguire quel processo.</span><span class="sxs-lookup"><span data-stu-id="6a583-153">Instead it uses the `ContextManagerFactory` class to do that job.</span></span>

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

<span data-ttu-id="6a583-154">Il metodo `ApplyContext` viene richiamato dai canali di invio.</span><span class="sxs-lookup"><span data-stu-id="6a583-154">The `ApplyContext` method is invoked by the sending channels.</span></span> <span data-ttu-id="6a583-155">Inserisce l'ID del contesto nei messaggi in uscita.</span><span class="sxs-lookup"><span data-stu-id="6a583-155">It injects the context ID to the outgoing messages.</span></span> <span data-ttu-id="6a583-156">Il metodo `ReadContextId` viene richiamato dai canali di ricezione.</span><span class="sxs-lookup"><span data-stu-id="6a583-156">The `ReadContextId` method is invoked by the receiving channels.</span></span> <span data-ttu-id="6a583-157">Questo metodo assicura che l'ID del contesto sia disponibile nei messaggi in arrivo e lo aggiunge alla raccolta `Properties` della classe `Message`.</span><span class="sxs-lookup"><span data-stu-id="6a583-157">This method ensures that the context ID is available in the incoming messages and adds it to the `Properties` collection of the `Message` class.</span></span> <span data-ttu-id="6a583-158">Genera inoltre un'eccezione `CommunicationException` in caso di errore nella lettura dell'ID del contesto, facendo in modo che il canale venga interrotto.</span><span class="sxs-lookup"><span data-stu-id="6a583-158">It also throws a `CommunicationException` in case of a failure to read the context ID and thus causes the channel to be aborted.</span></span>

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

<span data-ttu-id="6a583-159">Prima di procedere, è importante comprendere l'utilizzo della raccolta `Properties` nella classe `Message`.</span><span class="sxs-lookup"><span data-stu-id="6a583-159">Before proceeding, it is important to understand the usage of the `Properties` collection in the `Message` class.</span></span> <span data-ttu-id="6a583-160">In genere, questa raccolta `Properties` viene utilizzata quando si passano dati dai livelli inferiore a quelli superiori dal livello del canale.</span><span class="sxs-lookup"><span data-stu-id="6a583-160">Typically, this `Properties` collection is used when passing data from lower to the upper levels from the channel layer.</span></span> <span data-ttu-id="6a583-161">In questo modo i dati desiderati possono essere forniti ai livelli superiori in modo coerente, indipendentemente dai dettagli del protocollo.</span><span class="sxs-lookup"><span data-stu-id="6a583-161">This way the desired data can be provided to the upper levels in a consistent manner regardless of the protocol details.</span></span> <span data-ttu-id="6a583-162">In altre parole, il livello del canale può inviare e ricevere l'ID del contesto come intestazione SOAP o intestazione HTTP del cookie.</span><span class="sxs-lookup"><span data-stu-id="6a583-162">In other words, the channel layer can send and receive the context ID either as a SOAP header or an HTTP cookie header.</span></span> <span data-ttu-id="6a583-163">Ma non è necessario che i livelli superiori conoscano questi dettagli, perché il livello del canale rende disponibili queste informazioni nella raccolta `Properties`.</span><span class="sxs-lookup"><span data-stu-id="6a583-163">But it is not necessary for the upper levels to know about these details because the channel layer makes this information available in the `Properties` collection.</span></span>

<span data-ttu-id="6a583-164">Una volta sistemata la classe `DurableInstanceContextChannelBase` tutte e dieci le interfacce necessarie (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) devono essere implementate.</span><span class="sxs-lookup"><span data-stu-id="6a583-164">Now with the `DurableInstanceContextChannelBase` class in place all ten of the necessary interfaces (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) must be implemented.</span></span> <span data-ttu-id="6a583-165">Sono simili a tutti i modelli di scambio dei messaggi disponibili (datagramma, simplex, duplex e varianti con sessione).</span><span class="sxs-lookup"><span data-stu-id="6a583-165">They resemble every available message exchange pattern (datagram, simplex, duplex, and their sessionful variants).</span></span> <span data-ttu-id="6a583-166">Ognuna di queste implementazioni eredita la classe di base descritta in precedenza e chiama `ApplyContext` e in `ReadContextId` modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a583-166">Each of these implementations inherits the base class previously described and calls `ApplyContext` and `ReadContextId` appropriately.</span></span> <span data-ttu-id="6a583-167">Ad esempio, `DurableInstanceContextOutputChannel`, il quale implementa l'interfaccia IOutputChannel, chiama il metodo `ApplyContext` da ogni metodo che invia i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a583-167">For example, `DurableInstanceContextOutputChannel` - which implements the IOutputChannel interface - calls the `ApplyContext` method from each method that sends the messages.</span></span>

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

<span data-ttu-id="6a583-168">D'altra parte, `DurableInstanceContextInputChannel` che implementa l'interfaccia, `IInputChannel` chiama il `ReadContextId` metodo in ogni metodo che riceve i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a583-168">On the other hand, `DurableInstanceContextInputChannel` - which implements the `IInputChannel` interface - calls the `ReadContextId` method in each method, which receives the messages.</span></span>

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

<span data-ttu-id="6a583-169">Tranne che in questi casi, queste implementazioni del canale delegano le chiamate al metodo al canale sottostante nello stack di canali.</span><span class="sxs-lookup"><span data-stu-id="6a583-169">Apart from this, these channel implementations delegate the method invocations to the channel below them in the channel stack.</span></span> <span data-ttu-id="6a583-170">Tuttavia, le varianti con sessione hanno una logica di base per assicurarsi che l'ID del contesto venga inviato e letto solo per il primo messaggio che crea la sessione.</span><span class="sxs-lookup"><span data-stu-id="6a583-170">However, sessionful variants have a basic logic to make sure that the context ID is sent and is read only for the first message that causes the session to be created.</span></span>

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

<span data-ttu-id="6a583-171">Queste implementazioni del canale vengono quindi aggiunte al runtime del canale WCF dalla `DurableInstanceContextBindingElement` classe e dalla `DurableInstanceContextBindingElementSection` classe in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a583-171">These channel implementations are then added to the WCF channel runtime by the `DurableInstanceContextBindingElement` class and `DurableInstanceContextBindingElementSection` class appropriately.</span></span> <span data-ttu-id="6a583-172">Per ulteriori informazioni sugli elementi di associazione e le sezioni degli elementi di associazione, vedere la documentazione di esempio sul canale [HttpCookieSession](httpcookiesession.md) .</span><span class="sxs-lookup"><span data-stu-id="6a583-172">See the [HttpCookieSession](httpcookiesession.md) channel sample documentation for more details about binding elements and binding element sections.</span></span>

## <a name="service-model-layer-extensions"></a><span data-ttu-id="6a583-173">Estensioni del livello del modello di servizio</span><span class="sxs-lookup"><span data-stu-id="6a583-173">Service Model Layer Extensions</span></span>

<span data-ttu-id="6a583-174">Ora che l'ID del contesto è stato trasferito utilizzando il livello del canale, il comportamento del servizio può essere implementato per personalizzare la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="6a583-174">Now that the context ID has traveled through the channel layer, the service behavior can be implemented to customize the instantiation.</span></span> <span data-ttu-id="6a583-175">In questo esempio, viene utilizzata una gestione archivi per caricare e salvare lo stato a o da l'archivio permanente.</span><span class="sxs-lookup"><span data-stu-id="6a583-175">In this sample, a storage manager is used to load and save state from or to the persistent store.</span></span> <span data-ttu-id="6a583-176">Come spiegato in precedenza, questo esempio fornisce una gestione archivi che utilizza SQL Server 2005 come archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="6a583-176">As explained previously, this sample provides a storage manager that uses SQL Server 2005 as its backing store.</span></span> <span data-ttu-id="6a583-177">È tuttavia possibile aggiungere meccanismi di archiviazione personalizzati a questa estensione.</span><span class="sxs-lookup"><span data-stu-id="6a583-177">However, it is also possible to add custom storage mechanisms to this extension.</span></span> <span data-ttu-id="6a583-178">Per fare ciò, viene dichiarata un'interfaccia pubblica che deve essere implementata da tutte le gestioni archivi.</span><span class="sxs-lookup"><span data-stu-id="6a583-178">To do that a public interface is declared, which must be implemented by all storage managers.</span></span>

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

<span data-ttu-id="6a583-179">La classe `SqlServerStorageManager` contiene l'implementazione `IStorageManager` predefinita.</span><span class="sxs-lookup"><span data-stu-id="6a583-179">The `SqlServerStorageManager` class contains the default `IStorageManager` implementation.</span></span> <span data-ttu-id="6a583-180">Nel `SaveInstance` metodo, l'oggetto specificato viene serializzato utilizzando XmlSerializer e viene salvato nel database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a583-180">In its `SaveInstance` method, the given object is serialized using the XmlSerializer and is saved to the SQL Server database.</span></span>

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

<span data-ttu-id="6a583-181">Nel `GetInstance` metodo, i dati serializzati vengono letti per un determinato ID di contesto e l'oggetto costruito da esso viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6a583-181">In the `GetInstance` method, the serialized data is read for a given context ID and the object constructed from it is returned to the caller.</span></span>

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

<span data-ttu-id="6a583-182">Non è necessario che gli utenti di queste gestioni archivi creino direttamente un'istanza.</span><span class="sxs-lookup"><span data-stu-id="6a583-182">Users of these storage managers are not supposed to instantiate them directly.</span></span> <span data-ttu-id="6a583-183">Possono utilizzare la classe `StorageManagerFactory` che astrae dai dettagli della creazione della gestione archivi.</span><span class="sxs-lookup"><span data-stu-id="6a583-183">They use the `StorageManagerFactory` class, which abstracts from the storage manager creation details.</span></span> <span data-ttu-id="6a583-184">Questa classe ha uno membro statico, `GetStorageManager`, che crea un'istanza di un tipo di gestione archivi specificato.</span><span class="sxs-lookup"><span data-stu-id="6a583-184">This class has one static member, `GetStorageManager`, which creates an instance of a given storage manager type.</span></span> <span data-ttu-id="6a583-185">Se il parametro di tipo è `null`, questo metodo crea un'istanza della classe `SqlServerStorageManager` predefinita e la restituisce.</span><span class="sxs-lookup"><span data-stu-id="6a583-185">If the type parameter is `null`, this method creates an instance of the default `SqlServerStorageManager` class and returns it.</span></span> <span data-ttu-id="6a583-186">Convalida inoltre il tipo specificato per assicurarsi che implementi l'interfaccia `IStorageManager`.</span><span class="sxs-lookup"><span data-stu-id="6a583-186">It also validates the given type to make sure that it implements the `IStorageManager` interface.</span></span>

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

<span data-ttu-id="6a583-187">L'infrastruttura necessaria per leggere e scrivere istanze dall'archiviazione permanente è implementata.</span><span class="sxs-lookup"><span data-stu-id="6a583-187">The necessary infrastructure to read and write instances from the persistent storage is implemented.</span></span> <span data-ttu-id="6a583-188">È ora necessario eseguire i passaggi necessari per modificare il comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-188">Now the necessary steps to change the service behavior have to be taken.</span></span>

<span data-ttu-id="6a583-189">Come primo passaggio di questo processo è necessario salvare l'ID del contesto che è stato trasferito sul InstanceContext attuale utilizzando il livello del canale.</span><span class="sxs-lookup"><span data-stu-id="6a583-189">As the first step of this process we have to save the context ID, which came through the channel layer to the current InstanceContext.</span></span> <span data-ttu-id="6a583-190">InstanceContext è un componente di runtime che funge da collegamento tra il Dispatcher WCF e l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-190">InstanceContext is a runtime component that acts as the link between the WCF dispatcher and the service instance.</span></span> <span data-ttu-id="6a583-191">Può essere utilizzato per fornire stati e comportamenti aggiuntivi all'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-191">It can be used to provide additional state and behavior to the service instance.</span></span> <span data-ttu-id="6a583-192">È essenziale, perché nella comunicazione con sessione l'ID del contesto viene inviato solo con il primo messaggio.</span><span class="sxs-lookup"><span data-stu-id="6a583-192">This is essential because in sessionful communication the context ID is sent only with the first message.</span></span>

<span data-ttu-id="6a583-193">WCF consente di estendere il componente runtime di InstanceContext aggiungendo un nuovo stato e un nuovo comportamento usando il modello di oggetto estensibile.</span><span class="sxs-lookup"><span data-stu-id="6a583-193">WCF allows extending its InstanceContext runtime component by adding a new state and behavior using its extensible object pattern.</span></span> <span data-ttu-id="6a583-194">Il modello a oggetti estendibile viene usato in WCF per estendere le classi di runtime esistenti con nuove funzionalità o per aggiungere nuove funzionalità di stato a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="6a583-194">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="6a583-195">Nel modello di oggetto estensibile sono disponibili tre interfacce \<T> , IExtensibleObject, IExtension \<T> e IExtensionCollection \<T> :</span><span class="sxs-lookup"><span data-stu-id="6a583-195">There are three interfaces in the extensible object pattern - IExtensibleObject\<T>, IExtension\<T>, and IExtensionCollection\<T>:</span></span>

- <span data-ttu-id="6a583-196">L' \<T> interfaccia IExtensibleObject viene implementata da oggetti che consentono le estensioni che ne personalizzano le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6a583-196">The IExtensibleObject\<T> interface is implemented by objects that allow extensions that customize their functionality.</span></span>

- <span data-ttu-id="6a583-197">L' \<T> interfaccia IExtension è implementata da oggetti che sono estensioni di classi di tipo T.</span><span class="sxs-lookup"><span data-stu-id="6a583-197">The IExtension\<T> interface is implemented by objects that are extensions of classes of type T.</span></span>

- <span data-ttu-id="6a583-198">L' \<T> interfaccia IExtensionCollection è una raccolta di IExtensions che consente di recuperare IExtensions in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="6a583-198">The IExtensionCollection\<T> interface is a collection of IExtensions that allows for retrieving IExtensions by their type.</span></span>

<span data-ttu-id="6a583-199">È pertanto necessario creare una classe InstanceContextExtension che implementi l'interfaccia IExtension e definisca lo stato necessario per salvare l'ID del contesto.</span><span class="sxs-lookup"><span data-stu-id="6a583-199">Therefore an InstanceContextExtension class should be created that implements the IExtension interface and defines the required state to save the context ID.</span></span> <span data-ttu-id="6a583-200">Questa classe fornisce inoltre lo stato per memorizzare la gestione archivi utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6a583-200">This class also provides the state to hold the storage manager being used.</span></span> <span data-ttu-id="6a583-201">Una volta salvato il nuovo stato, non sarà possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="6a583-201">Once the new state is saved, it should not be possible to modify it.</span></span> <span data-ttu-id="6a583-202">Lo stato viene pertanto fornito e salvato nell'istanza che viene generata in quel momento e vi si potrà accedere soltanto utilizzando le proprietà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6a583-202">Therefore the state is provided and saved to the instance at the time it is being constructed and then only accessible using read-only properties.</span></span>

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

<span data-ttu-id="6a583-203">La classe InstanceContextInitializer implementa l'interfaccia IInstanceContextInitializer e aggiunge l'estensione del contesto di istanza alla raccolta di estensioni dell'InstanceContext che viene generata.</span><span class="sxs-lookup"><span data-stu-id="6a583-203">The InstanceContextInitializer class implements the IInstanceContextInitializer interface and adds the instance context extension to the Extensions collection of the InstanceContext being constructed.</span></span>

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

<span data-ttu-id="6a583-204">Come descritto precedentemente, l'ID del contesto viene letto dalla raccolta `Properties` della classe `Message` e passato al costruttore della classe dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="6a583-204">As described earlier the context ID is read from the `Properties` collection of the `Message` class and passed to the constructor of the extension class.</span></span> <span data-ttu-id="6a583-205">Questo dimostra che le informazioni possono essere scambiate tra i livelli in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="6a583-205">This demonstrates how information can be exchanged between the layers in a consistent manner.</span></span>

<span data-ttu-id="6a583-206">Il successivo passaggio consiste nell'eseguire l'override del processo di creazione dell'istanza di servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-206">The next important step is overriding the service instance creation process.</span></span> <span data-ttu-id="6a583-207">WCF consente di implementare comportamenti di creazione di istanze personalizzati e di associarli al runtime utilizzando l'interfaccia IInstanceProvider.</span><span class="sxs-lookup"><span data-stu-id="6a583-207">WCF allows implementing custom instantiation behaviors and hooking them up to the runtime using the IInstanceProvider interface.</span></span> <span data-ttu-id="6a583-208">La nuova classe `InstanceProvider` viene implementata per eseguire quel processo.</span><span class="sxs-lookup"><span data-stu-id="6a583-208">The new `InstanceProvider` class is implemented to do that job.</span></span> <span data-ttu-id="6a583-209">Il tipo di servizio previsto dal provider di istanze è accettato nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="6a583-209">The service type expected from the instance provider is accepted in the constructor.</span></span> <span data-ttu-id="6a583-210">In un secondo momento viene utilizzato per creare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="6a583-210">Later this is used to create new instances.</span></span> <span data-ttu-id="6a583-211">Nell' `GetInstance` implementazione di viene creata un'istanza di un gestore di archiviazione che cerca un'istanza salvata in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="6a583-211">In the `GetInstance` implementation, an instance of a storage manager is created looking for a persisted instance.</span></span> <span data-ttu-id="6a583-212">Se restituisce `null` , viene creata un'istanza di una nuova istanza del tipo di servizio e viene restituita al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6a583-212">If it returns `null`, then a new instance of the service type is instantiated and returned to the caller.</span></span>

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

<span data-ttu-id="6a583-213">Il passaggio importante successivo consiste nell'installare le `InstanceContextExtension` `InstanceContextInitializer` classi, e `InstanceProvider` nel runtime del modello di servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-213">The next important step is to install the `InstanceContextExtension`, `InstanceContextInitializer`, and `InstanceProvider` classes into the service model runtime.</span></span> <span data-ttu-id="6a583-214">È possibile utilizzare un attributo personalizzato per contrassegnare le classi di implementazione del servizio perché installino il comportamento.</span><span class="sxs-lookup"><span data-stu-id="6a583-214">A custom attribute could be used to mark the service implementation classes to install the behavior.</span></span> <span data-ttu-id="6a583-215">`DurableInstanceContextAttribute` contiene l'implementazione per questo attributo e implementa l'interfaccia `IServiceBehavior` per estendere l'intero runtime del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-215">The `DurableInstanceContextAttribute` contains the implementation for this attribute and it implements the `IServiceBehavior` interface to extend the entire service runtime.</span></span>

<span data-ttu-id="6a583-216">Questa classe è dotata di una proprietà che accetta il tipo della gestione archivi da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6a583-216">This class has a property that accepts the type of the storage manager to be used.</span></span> <span data-ttu-id="6a583-217">In questo modo, l'implementazione consente agli utenti di specificare la propria `IStorageManager` implementazione come parametro di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="6a583-217">In this way, the implementation enables the users to specify their own `IStorageManager` implementation as parameter of this attribute.</span></span>

<span data-ttu-id="6a583-218">Nell' `ApplyDispatchBehavior` implementazione di, l'oggetto `InstanceContextMode` dell' `ServiceBehavior` attributo corrente viene verificato.</span><span class="sxs-lookup"><span data-stu-id="6a583-218">In the `ApplyDispatchBehavior` implementation, the `InstanceContextMode` of the current `ServiceBehavior` attribute is being verified.</span></span> <span data-ttu-id="6a583-219">Se questa proprietà è impostata su Singleton, non è possibile abilitare la creazione di istanze durevoli e viene generata un'eccezione `InvalidOperationException` per notificare l'host.</span><span class="sxs-lookup"><span data-stu-id="6a583-219">If this property is set to Singleton, enabling durable instancing is not possible and an `InvalidOperationException` is thrown to notify the host.</span></span>

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

<span data-ttu-id="6a583-220">Dopodiché le istanze della gestione archivi, dell'inizializzatore del contesto dell'istanza e del provider di istanze vengono  creati e installati nel `DispatchRuntime` creato per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a583-220">After this the instances of the storage manager, instance context initializer, and the instance provider are created and installed in the `DispatchRuntime` created for every endpoint.</span></span>

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

<span data-ttu-id="6a583-221">Per riassumere, questo esempio ha prodotto un canale che abilita il protocollo di rete personalizzato per lo scambio di ID del contesto personalizzati e sovrascrive il comportamento di istanza predefinito per caricare le istanze dall'archivio permanente.</span><span class="sxs-lookup"><span data-stu-id="6a583-221">In summary so far, this sample has produced a channel that enabled the custom wire protocol for custom context ID exchange and it also overwrites the default instancing behavior to load the instances from the persistent storage.</span></span>

<span data-ttu-id="6a583-222">Rimane da trovare un modo per salvare l'istanza del servizio nell'archivio permanente.</span><span class="sxs-lookup"><span data-stu-id="6a583-222">What is left is a way to save the service instance to the persistent storage.</span></span> <span data-ttu-id="6a583-223">Come illustrato precedentemente, esiste già la funzionalità necessaria per salvare lo stato in un'implementazione `IStorageManager`.</span><span class="sxs-lookup"><span data-stu-id="6a583-223">As discussed previously, there is already the required functionality to save the state in an `IStorageManager` implementation.</span></span> <span data-ttu-id="6a583-224">A questo punto è necessario integrare questa operazione con il runtime WCF.</span><span class="sxs-lookup"><span data-stu-id="6a583-224">We now must integrate this with the WCF runtime.</span></span> <span data-ttu-id="6a583-225">È necessario un altro attributo applicabile ai metodi della classe di implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-225">Another attribute is required that is applicable to the methods in the service implementation class.</span></span> <span data-ttu-id="6a583-226">Questo attributo va applicato ai metodi che modificano lo stato dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-226">This attribute is supposed to be applied to the methods that change the state of the service instance.</span></span>

<span data-ttu-id="6a583-227">La classe `SaveStateAttribute` implementa questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6a583-227">The `SaveStateAttribute` class implements this functionality.</span></span> <span data-ttu-id="6a583-228">Implementa inoltre `IOperationBehavior` la classe per modificare il runtime WCF per ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-228">It also implements `IOperationBehavior` class to modify the WCF runtime for each operation.</span></span> <span data-ttu-id="6a583-229">Quando un metodo è contrassegnato con questo attributo, il runtime WCF richiama il `ApplyBehavior` Metodo mentre viene costruito l'oggetto appropriato `DispatchOperation` .</span><span class="sxs-lookup"><span data-stu-id="6a583-229">When a method is marked with this attribute, the WCF runtime invokes the `ApplyBehavior` method while the appropriate `DispatchOperation` is being constructed.</span></span> <span data-ttu-id="6a583-230">In questa implementazione del metodo è presente una sola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="6a583-230">There is a single line of code in this method implementation:</span></span>

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

<span data-ttu-id="6a583-231">Questa istruzione crea un'istanza di tipo `OperationInvoker` e la assegna alla proprietà `Invoker` dell'elemento `DispatchOperation` che viene generato.</span><span class="sxs-lookup"><span data-stu-id="6a583-231">This instruction creates an instance of `OperationInvoker` type and assigns it to the `Invoker` property of the `DispatchOperation` being constructed.</span></span> <span data-ttu-id="6a583-232">La classe `OperationInvoker` è un wrapper per l'invoker dell'operazione predefinita creato per `DispatchOperation`.</span><span class="sxs-lookup"><span data-stu-id="6a583-232">The `OperationInvoker` class is a wrapper for the default operation invoker created for the `DispatchOperation`.</span></span> <span data-ttu-id="6a583-233">La classe implementa l'interfaccia `IOperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="6a583-233">This class implements the `IOperationInvoker` interface.</span></span> <span data-ttu-id="6a583-234">Nell' `Invoke` implementazione del metodo, la chiamata al metodo effettiva viene delegata all'invoker dell'operazione interna.</span><span class="sxs-lookup"><span data-stu-id="6a583-234">In the `Invoke` method implementation, the actual method invocation is delegated to the inner operation invoker.</span></span> <span data-ttu-id="6a583-235">Tuttavia, prima di restituire i risultati la gestione archivi in `InstanceContext` viene utilizzata per salvare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-235">However, before returning the results the storage manager in the `InstanceContext` is used to save the service instance.</span></span>

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a><span data-ttu-id="6a583-236">Utilizzo dell'estensione</span><span class="sxs-lookup"><span data-stu-id="6a583-236">Using the Extension</span></span>

<span data-ttu-id="6a583-237">Le estensioni del livello del canale e del livello del modello di servizio vengono eseguite e ora possono essere utilizzate nelle applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="6a583-237">Both the channel layer and service model layer extensions are done and they can now be used in WCF applications.</span></span> <span data-ttu-id="6a583-238">I servizi devono aggiungere il canale nello stack dei canali utilizzando un'associazione personalizzata e quindi contrassegnare le classi di implementazione del servizio con gli attributi appropriati.</span><span class="sxs-lookup"><span data-stu-id="6a583-238">Services must add the channel into the channel stack using a custom binding and then mark the service implementation classes with the appropriate attributes.</span></span>

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

<span data-ttu-id="6a583-239">È necessario che le applicazioni client aggiungano DurableInstanceContextChannel allo stack di canali utilizzando un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6a583-239">Client applications must add the DurableInstanceContextChannel into the channel stack using a custom binding.</span></span> <span data-ttu-id="6a583-240">Per configurare in modo dichiarativo il canale nel file di configurazione la sezione dell'elemento di associazione deve essere aggiunta alla raccolta delle estensioni degli elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-240">To configure the channel declaratively in the configuration file, the binding element section has to be added to the binding element extensions collection.</span></span>

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

<span data-ttu-id="6a583-241">È ora possibile utilizzare l'elemento di associazione con un'associazione personalizzata, proprio come gli altri elementi di associazione standard:</span><span class="sxs-lookup"><span data-stu-id="6a583-241">Now the binding element can be used with a custom binding just like other standard binding elements:</span></span>

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a><span data-ttu-id="6a583-242">Conclusione</span><span class="sxs-lookup"><span data-stu-id="6a583-242">Conclusion</span></span>

<span data-ttu-id="6a583-243">In questo esempio viene illustrato come creare un canale del protocollo personalizzato e come personalizzare il comportamento del servizio per abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="6a583-243">This sample showed how to create a custom protocol channel and how to customize the service behavior to enable it.</span></span>

<span data-ttu-id="6a583-244">L'estensione può essere ulteriormente migliorata consentendo agli utenti di specificare l'implementazione `IStorageManager` utilizzando una sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a583-244">The extension can be further improved by letting users specify the `IStorageManager` implementation using a configuration section.</span></span> <span data-ttu-id="6a583-245">In questo modo è possibile modificare l'archivio di backup senza ricompilare il codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-245">This makes it possible to modify the backing store without recompiling the service code.</span></span>

<span data-ttu-id="6a583-246">È inoltre possibile tentare di implementare una classe (ad esempio, `StateBag`) che incapsuli lo stato dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="6a583-246">Furthermore you could try to implement a class (for example, `StateBag`), which encapsulates the state of the instance.</span></span> <span data-ttu-id="6a583-247">Quella classe è responsabile di salvare in modo permanente lo stato quando viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6a583-247">That class is responsible for persisting the state whenever it changes.</span></span> <span data-ttu-id="6a583-248">In questo modo è possibile evitare di utilizzare l'attributo `SaveState` ed eseguire più accuratamente il lavoro di archiviazione permanente (ad esempio, è possibile salvare in modo permanente lo stato solo quando viene davvero modificato piuttosto che salvarlo ogni volta che viene chiamato un metodo con l'attributo `SaveState`).</span><span class="sxs-lookup"><span data-stu-id="6a583-248">This way you can avoid using the `SaveState` attribute and perform the persisting work more accurately (for example, you could persist the state when the state is actually changed rather than saving it each time when a method with the `SaveState` attribute is called).</span></span>

<span data-ttu-id="6a583-249">Quando si esegue l'esempio, viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="6a583-249">When you run the sample, the following output is displayed.</span></span> <span data-ttu-id="6a583-250">Il client aggiunge due elementi al carrello degli acquisti e ottiene l'elenco di elementi nel carrello degli acquisti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-250">The client adds two items to its shopping cart and then gets the list of items in its shopping cart from the service.</span></span> <span data-ttu-id="6a583-251">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="6a583-251">Press ENTER in each console window to shut down the service and client.</span></span>

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> <span data-ttu-id="6a583-252">La ricompilazione del servizio si sovrascrive il file di database.</span><span class="sxs-lookup"><span data-stu-id="6a583-252">Rebuilding the service overwrites the database file.</span></span> <span data-ttu-id="6a583-253">Per osservare lo stato salvato in modo permanente in più esecuzioni dell'esempio, assicurarsi di non ricompilare l'esempio tra esecuzioni.</span><span class="sxs-lookup"><span data-stu-id="6a583-253">To observe state preserved across multiple runs of the sample, be sure not to rebuild the sample between runs.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a583-254">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6a583-254">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="6a583-255">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a583-255">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="6a583-256">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a583-256">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="6a583-257">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a583-257">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a583-258">È necessario che SQL Server 2005 o SQL Express 2005 siano in esecuzione per eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6a583-258">You must be running SQL Server 2005 or SQL Express 2005 to run this sample.</span></span> <span data-ttu-id="6a583-259">Se è in esecuzione SQL Server 2005, è necessario modificare la configurazione della stringa di connessione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6a583-259">If you are running SQL Server 2005, you must modify the configuration of the service's connection string.</span></span> <span data-ttu-id="6a583-260">Quando si esegue tra più computer, SQL Server è necessario solo sul server.</span><span class="sxs-lookup"><span data-stu-id="6a583-260">When running cross-machine, SQL Server is only required on the server machine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a583-261">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6a583-261">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a583-262">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6a583-262">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6a583-263">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="6a583-263">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a583-264">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6a583-264">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
