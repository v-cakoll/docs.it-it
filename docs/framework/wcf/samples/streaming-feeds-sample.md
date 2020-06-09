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
# <a name="streaming-feeds-sample"></a>Esempio trasmissione feed
Questo esempio illustra come gestire feed che contengono numerosi elementi. Nel server, l'esempio illustra come rimandare la creazione di oggetti <xref:System.ServiceModel.Syndication.SyndicationItem> singoli all'interno del feed fino a immediatamente prima della scrittura dell'elemento nel flusso della rete.  
  
 Sul client, l'esempio illustra come un formattatore del feed di distribuzione personalizzato possa essere utilizzato per leggere elementi singoli dal flusso della rete così che il feed letto non sia mai pienamente memorizzato nel buffer.  
  
 Per dimostrare al meglio la funzionalità del flusso di diffusione API, questo esempio utilizza uno scenario piuttosto improbabile nel quale il server espone un feed che contiene un numero infinito di elementi. In questo caso, il server continua a generare nuovi elementi nel feed fino a determinare che il client ha letto un numero specificato di elementi dal feed (10, per impostazione predefinita). Per semplicità, sia il client che il server vengono implementati nello stesso processo e utilizzano un oggetto `ItemCounter` condiviso per tenere traccia del numero di elementi prodotti dal client. Il tipo `ItemCounter` esiste solo allo scopo di consentire allo scenario di esempio di terminare in modo pulito e non è un elemento principale dello schema illustrato.  
  
 La dimostrazione usa gli iteratori di Visual C# (usando il `yield return` costrutto di parola chiave). Per ulteriori informazioni sugli iteratori, vedere l'argomento relativo all'utilizzo degli iteratori su MSDN.  
  
## <a name="service"></a>Service  
 Il servizio implementa un contratto <xref:System.ServiceModel.Web.WebGetAttribute> di base che è costituito da un'operazione, come mostra il codice seguente.  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 Il servizio implementa il contratto utilizzando una classe `ItemGenerator` per creare un flusso potenzialmente infinito di istanze <xref:System.ServiceModel.Syndication.SyndicationItem> utilizzando un iteratore, come mostra il codice seguente.  
  
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
  
 Quando l'implementazione del servizio crea il feed, viene utilizzato l'output di `ItemGenerator.GenerateItems()` invece di una raccolta di elementi memorizzato nel buffer.  
  
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
  
 Di conseguenza, il flusso dell'elemento non viene mai memorizzato pienamente nel buffer. È possibile osservare questo comportamento impostando un punto di interruzione sull' `yield return` istruzione all'interno del `ItemGenerator.GenerateItems()` metodo e notando che il punto di interruzione viene rilevato per la prima volta dopo che il servizio ha restituito il risultato del `StreamedFeed()` metodo.  
  
## <a name="client"></a>Client  
 Il client in questo esempio utilizza un'implementazione personalizzata della classe <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> che rimanda la materializzazione di elementi singoli nel feed invece di memorizzarli nel buffer. Di seguito viene illustrata l'istanza personalizzata di `StreamedAtom10FeedFormatter`:  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 Normalmente, una chiamata al metodo <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> non restituisce alcun risultato fino a che il contenuto intero del feed non sia stato letto dalla rete e memorizzato nel buffer. Tuttavia, l'oggetto `StreamedAtom10FeedFormatter` ignora il metodo <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> per restituire un iteratore invece di una raccolta memorizzata nel buffer, come mostra il codice seguente.  
  
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
  
 Di conseguenza, ogni elemento non viene letto dalla rete fino a che l'applicazione client che attraversa i risultati di `ReadItems()` non è pronta a utilizzarli. È possibile osservare questo comportamento impostando un punto di interruzione sull' `yield return` istruzione all'interno di `StreamedAtom10FeedFormatter.DelayReadItems()` e notando che il punto di interruzione viene rilevato per la prima volta dopo il completamento della chiamata a `ReadFrom()` .  
  
 Nelle istruzioni seguenti viene illustrato come compilare ed eseguire l'esempio. Notare che anche se il server smette di generare elementi dopo che il client ha letto 10 elementi, l'output mostra che il client ne legge molti più di 10. Ciò avviene perché l'associazione di rete utilizzata dall'esempio trasmette dati in segmenti di quattro kilobyte (KB). Di conseguenza, il client riceve 4 KB di dati dell'elemento prima che abbia la possibilità di leggere il primo elemento. Si tratta di un comportamento normale (trasmettere dati HTTP in segmenti di dimensioni ragionevolmente grandi aumenta le prestazioni).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a>Vedere anche

- [Feed di diagnostica autonomo](stand-alone-diagnostics-feed-sample.md)
