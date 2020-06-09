---
title: Formattatore di feed (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: 7b535a5090d3c7df59b7faada35fc324a77b5651
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594673"
---
# <a name="feed-formatter-json"></a>Formattatore di feed (JSON)
In questo esempio viene illustrato come serializzare un'istanza di una classe <xref:System.ServiceModel.Syndication.SyndicationFeed> in JSON (JavaScript Object Notation) usando un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizzato e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="architecture-of-the-sample"></a>Architettura dell'esempio  
 Nell'esempio viene implementata una classe denominata `JsonFeedFormatter` che eredita da <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. La classe `JsonFeedFormatter` si basa sul <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per leggere e scrivere e i dati in formato JSON. Internamente, il formattatore usa un set personalizzato di tipi di contratto dati denominati `JsonSyndicationFeed` e `JsonSyndicationItem` per controllare il formato dei dati JSON prodotti dal serializzatore. Questi dettagli di implementazione sono nascosti dall'utente finale, consentendo l'esecuzione di chiamate rispetto alle classi <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> standard.  
  
## <a name="writing-json-feeds"></a>Scrittura di feed JSON  
 La scrittura di un feed JSON può essere ottenuta usando il `JsonFeedFormatter` (implementato in questo esempio) con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> come illustrato nel codice di esempio seguente.  
  
```csharp  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
```  
  
## <a name="reading-a-json-feed"></a>Lettura di un feed JSON  
 L'ottenimento di un <xref:System.ServiceModel.Syndication.SyndicationFeed> da un flusso di dati formattati JSON può essere eseguito tramite `JsonFeedFormatter` come illustrato nel codice seguente.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
