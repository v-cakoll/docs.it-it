---
title: Formattatore di feed (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: 350e07ad37b09f39fc709e20d8f73a41f9d01f30
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183646"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="adb6c-102">Formattatore di feed (JSON)</span><span class="sxs-lookup"><span data-stu-id="adb6c-102">Feed Formatter (JSON)</span></span>
<span data-ttu-id="adb6c-103">In questo esempio viene illustrato come serializzare un'istanza di una classe <xref:System.ServiceModel.Syndication.SyndicationFeed> in JSON (JavaScript Object Notation) usando un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizzato e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="adb6c-103">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="adb6c-104">Architettura dell'esempio</span><span class="sxs-lookup"><span data-stu-id="adb6c-104">Architecture of the Sample</span></span>  
 <span data-ttu-id="adb6c-105">Nell'esempio viene implementata una classe denominata `JsonFeedFormatter` che eredita da <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="adb6c-105">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="adb6c-106">La classe `JsonFeedFormatter` si basa sul <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per leggere e scrivere e i dati in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="adb6c-106">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="adb6c-107">Internamente, il formattatore usa un set personalizzato di tipi di contratto dati denominati `JsonSyndicationFeed` e `JsonSyndicationItem` per controllare il formato dei dati JSON prodotti dal serializzatore.</span><span class="sxs-lookup"><span data-stu-id="adb6c-107">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="adb6c-108">Questi dettagli di implementazione sono nascosti dall'utente finale, consentendo l'esecuzione di chiamate rispetto alle classi <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> standard.</span><span class="sxs-lookup"><span data-stu-id="adb6c-108">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="adb6c-109">Scrittura di feed JSON</span><span class="sxs-lookup"><span data-stu-id="adb6c-109">Writing JSON feeds</span></span>  
 <span data-ttu-id="adb6c-110">La scrittura di un feed JSON può essere ottenuta usando il `JsonFeedFormatter` (implementato in questo esempio) con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="adb6c-110">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
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
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="adb6c-111">Lettura di un feed JSON</span><span class="sxs-lookup"><span data-stu-id="adb6c-111">Reading a JSON feed</span></span>  
 <span data-ttu-id="adb6c-112">L'ottenimento di un <xref:System.ServiceModel.Syndication.SyndicationFeed> da un flusso di dati formattati JSON può essere eseguito tramite `JsonFeedFormatter` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="adb6c-112">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="adb6c-113">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="adb6c-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="adb6c-114">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adb6c-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="adb6c-115">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adb6c-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="adb6c-116">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="adb6c-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adb6c-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="adb6c-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="adb6c-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="adb6c-118">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="adb6c-119">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="adb6c-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="adb6c-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="adb6c-120">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
