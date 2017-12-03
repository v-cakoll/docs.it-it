---
title: 'Procedura: chiamare operazioni del servizio WCF in modo asincrono'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 549510d4d2b2ae0ee031b1c5426e7e28ab902bcd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="ebe1f-102">Procedura: chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="ebe1f-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="ebe1f-103">In questo argomento viene illustrato come un client può accedere a un'operazione del servizio in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="ebe1f-104">Il servizio in questo argomento implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="ebe1f-105">Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="ebe1f-106">(Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [la programmazione multithreading con il modello asincrono basato su eventi](http://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="ebe1f-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="ebe1f-107">Per un esempio che illustra come implementare un'operazione in modo asincrono in un servizio, vedere [procedura: implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="ebe1f-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="ebe1f-108">Per ulteriori informazioni sulle operazioni sincrone e asincrone, vedere [sincrono e alle operazioni asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ebe1f-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe1f-109">Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="ebe1f-110">Per informazioni sull'esecuzione di chiamate asincrone mediante il <xref:System.ServiceModel.ChannelFactory%601>, vedere [procedura: chiamare operazioni utilizzando in modo asincrono una Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="ebe1f-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="ebe1f-111">Procedura</span><span class="sxs-lookup"><span data-stu-id="ebe1f-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="ebe1f-112">Per chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="ebe1f-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="ebe1f-113">Eseguire il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento con entrambi i `/async` e `/tcv:Version35` le opzioni del comando insieme come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="ebe1f-114">Questa operazione genera, oltre alle operazioni sincrone e a quelle asincrone standard basate su delega, una classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]contenente:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class that contains:</span></span>  
  
    -   <span data-ttu-id="ebe1f-115">Due <`operationName` > `Async` operazioni per l'utilizzo con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="ebe1f-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="ebe1f-117">Gli eventi di operazione è stata completata nel formato <`operationName` > `Completed` per l'utilizzo con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="ebe1f-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <span data-ttu-id="ebe1f-119"><xref:System.EventArgs?displayProperty=nameWithType>tipi per ogni operazione (nel formato <`operationName`>`CompletedEventArgs`) per l'utilizzo con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="ebe1f-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  <span data-ttu-id="ebe1f-121">Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  <span data-ttu-id="ebe1f-122">Prima di chiamare l'operazione, utilizzare un nuovo oggetto generico <xref:System.EventHandler%601?displayProperty=nameWithType> di tipo <`operationName` > `EventArgs` per aggiungere il metodo di gestore (creato nel passaggio precedente) per il <`operationName` > `Completed` evento.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="ebe1f-123">Chiamare quindi il <`operationName` > `Async` metodo.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="ebe1f-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ebe1f-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebe1f-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe1f-126">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ebe1f-127">Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="ebe1f-128">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ebe1f-129">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ebe1f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebe1f-130">See Also</span></span>  
 [<span data-ttu-id="ebe1f-131">Procedura: Implementare un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="ebe1f-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
