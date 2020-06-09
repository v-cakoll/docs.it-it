---
title: Esempio trasmissione feed
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 551a97f3cc54915a831fc28eca6ae0ff23101e0b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589786"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="0c908-102">Esempio trasmissione feed</span><span class="sxs-lookup"><span data-stu-id="0c908-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="0c908-103">Questo esempio illustra come gestire feed che contengono numerosi elementi.</span><span class="sxs-lookup"><span data-stu-id="0c908-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="0c908-104">Nel server, l'esempio illustra come rimandare la creazione di oggetti <xref:System.ServiceModel.Syndication.SyndicationItem> singoli all'interno del feed fino a immediatamente prima della scrittura dell'elemento nel flusso della rete.</span><span class="sxs-lookup"><span data-stu-id="0c908-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="0c908-105">Sul client, l'esempio illustra come un formattatore del feed di distribuzione personalizzato possa essere utilizzato per leggere elementi singoli dal flusso della rete così che il feed letto non sia mai pienamente memorizzato nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0c908-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="0c908-106">Per dimostrare al meglio la funzionalità del flusso di diffusione API, questo esempio utilizza uno scenario piuttosto improbabile nel quale il server espone un feed che contiene un numero infinito di elementi.</span><span class="sxs-lookup"><span data-stu-id="0c908-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="0c908-107">In questo caso, il server continua a generare nuovi elementi nel feed fino a determinare che il client ha letto un numero specificato di elementi dal feed (10, per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="0c908-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="0c908-108">Per semplicità, sia il client che il server vengono implementati nello stesso processo e utilizzano un oggetto `ItemCounter` condiviso per tenere traccia del numero di elementi prodotti dal client.</span><span class="sxs-lookup"><span data-stu-id="0c908-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="0c908-109">Il tipo `ItemCounter` esiste solo allo scopo di consentire allo scenario di esempio di terminare in modo pulito e non è un elemento principale dello schema illustrato.</span><span class="sxs-lookup"><span data-stu-id="0c908-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="0c908-110">La dimostrazione usa gli iteratori di Visual C# (usando il `yield return` costrutto di parola chiave).</span><span class="sxs-lookup"><span data-stu-id="0c908-110">The demonstration makes use of Visual C# iterators (using the `yield return` keyword construct).</span></span> <span data-ttu-id="0c908-111">Per ulteriori informazioni sugli iteratori, vedere l'argomento relativo all'utilizzo degli iteratori su MSDN.</span><span class="sxs-lookup"><span data-stu-id="0c908-111">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="0c908-112">Service</span><span class="sxs-lookup"><span data-stu-id="0c908-112">Service</span></span>  
 <span data-ttu-id="0c908-113">Il servizio implementa un contratto <xref:System.ServiceModel.Web.WebGetAttribute> di base che è costituito da un'operazione, come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0c908-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="0c908-114">Il servizio implementa il contratto utilizzando una classe `ItemGenerator` per creare un flusso potenzialmente infinito di istanze <xref:System.ServiceModel.Syndication.SyndicationItem> utilizzando un iteratore, come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0c908-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```csharp
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="0c908-115">Quando l'implementazione del servizio crea il feed, viene utilizzato l'output di `ItemGenerator.GenerateItems()` invece di una raccolta di elementi memorizzato nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0c908-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```csharp
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="0c908-116">Di conseguenza, il flusso dell'elemento non viene mai memorizzato pienamente nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0c908-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="0c908-117">È possibile osservare questo comportamento impostando un punto di interruzione sull' `yield return` istruzione all'interno del `ItemGenerator.GenerateItems()` metodo e notando che il punto di interruzione viene rilevato per la prima volta dopo che il servizio ha restituito il risultato del `StreamedFeed()` metodo.</span><span class="sxs-lookup"><span data-stu-id="0c908-117">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="0c908-118">Client</span><span class="sxs-lookup"><span data-stu-id="0c908-118">Client</span></span>  
 <span data-ttu-id="0c908-119">Il client in questo esempio utilizza un'implementazione personalizzata della classe <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> che rimanda la materializzazione di elementi singoli nel feed invece di memorizzarli nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0c908-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="0c908-120">Di seguito viene illustrata l'istanza personalizzata di `StreamedAtom10FeedFormatter`:</span><span class="sxs-lookup"><span data-stu-id="0c908-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="0c908-121">Normalmente, una chiamata al metodo <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> non restituisce alcun risultato fino a che il contenuto intero del feed non sia stato letto dalla rete e memorizzato nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0c908-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="0c908-122">Tuttavia, l'oggetto `StreamedAtom10FeedFormatter` ignora il metodo <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> per restituire un iteratore invece di una raccolta memorizzata nel buffer, come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0c908-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```csharp  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="0c908-123">Di conseguenza, ogni elemento non viene letto dalla rete fino a che l'applicazione client che attraversa i risultati di `ReadItems()` non è pronta a utilizzarli.</span><span class="sxs-lookup"><span data-stu-id="0c908-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="0c908-124">È possibile osservare questo comportamento impostando un punto di interruzione sull' `yield return` istruzione all'interno di `StreamedAtom10FeedFormatter.DelayReadItems()` e notando che il punto di interruzione viene rilevato per la prima volta dopo il completamento della chiamata a `ReadFrom()` .</span><span class="sxs-lookup"><span data-stu-id="0c908-124">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="0c908-125">Nelle istruzioni seguenti viene illustrato come compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="0c908-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="0c908-126">Notare che anche se il server smette di generare elementi dopo che il client ha letto 10 elementi, l'output mostra che il client ne legge molti più di 10.</span><span class="sxs-lookup"><span data-stu-id="0c908-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="0c908-127">Ciò avviene perché l'associazione di rete utilizzata dall'esempio trasmette dati in segmenti di quattro kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="0c908-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="0c908-128">Di conseguenza, il client riceve 4 KB di dati dell'elemento prima che abbia la possibilità di leggere il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="0c908-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="0c908-129">Si tratta di un comportamento normale (trasmettere dati HTTP in segmenti di dimensioni ragionevolmente grandi aumenta le prestazioni).</span><span class="sxs-lookup"><span data-stu-id="0c908-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0c908-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0c908-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0c908-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c908-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0c908-132">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c908-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0c908-133">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c908-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0c908-134">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0c908-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0c908-135">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0c908-135">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0c908-136">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0c908-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0c908-137">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0c908-137">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="0c908-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c908-138">See also</span></span>

- [<span data-ttu-id="0c908-139">Feed di diagnostica autonomo</span><span class="sxs-lookup"><span data-stu-id="0c908-139">Stand-Alone Diagnostics Feed</span></span>](stand-alone-diagnostics-feed-sample.md)
