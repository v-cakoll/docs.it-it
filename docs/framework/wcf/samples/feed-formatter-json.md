---
title: Formattatore di feed (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: c3e3378cd2465e26e4b6ff7b4c12a55050301095
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329505"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="0c550-102">Formattatore di feed (JSON)</span><span class="sxs-lookup"><span data-stu-id="0c550-102">Feed Formatter (JSON)</span></span>
<span data-ttu-id="0c550-103">In questo esempio viene illustrato come serializzare un'istanza di una classe <xref:System.ServiceModel.Syndication.SyndicationFeed> in JSON (JavaScript Object Notation) usando un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizzato e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0c550-103">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="0c550-104">Architettura dell'esempio</span><span class="sxs-lookup"><span data-stu-id="0c550-104">Architecture of the Sample</span></span>  
 <span data-ttu-id="0c550-105">Nell'esempio viene implementata una classe denominata `JsonFeedFormatter` che eredita da <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="0c550-105">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="0c550-106">La classe `JsonFeedFormatter` si basa sul <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per leggere e scrivere e i dati in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="0c550-106">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="0c550-107">Internamente, il formattatore usa un set personalizzato di tipi di contratto dati denominati `JsonSyndicationFeed` e `JsonSyndicationItem` per controllare il formato dei dati JSON prodotti dal serializzatore.</span><span class="sxs-lookup"><span data-stu-id="0c550-107">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="0c550-108">Questi dettagli di implementazione sono nascosti dall'utente finale, consentendo l'esecuzione di chiamate rispetto alle classi <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> standard.</span><span class="sxs-lookup"><span data-stu-id="0c550-108">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="0c550-109">Scrittura di feed JSON</span><span class="sxs-lookup"><span data-stu-id="0c550-109">Writing JSON feeds</span></span>  
 <span data-ttu-id="0c550-110">La scrittura di un feed JSON può essere ottenuta usando il `JsonFeedFormatter` (implementato in questo esempio) con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0c550-110">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
```  
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
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="0c550-111">Lettura di un feed JSON</span><span class="sxs-lookup"><span data-stu-id="0c550-111">Reading a JSON feed</span></span>  
 <span data-ttu-id="0c550-112">L'ottenimento di un <xref:System.ServiceModel.Syndication.SyndicationFeed> da un flusso di dati formattati JSON può essere eseguito tramite `JsonFeedFormatter` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0c550-112">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0c550-113">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0c550-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0c550-114">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c550-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0c550-115">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c550-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0c550-116">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c550-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c550-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0c550-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0c550-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0c550-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0c550-119">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0c550-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0c550-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0c550-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
