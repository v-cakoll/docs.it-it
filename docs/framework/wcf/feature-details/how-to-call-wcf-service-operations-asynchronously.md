---
title: 'Procedura: Chiamare operazioni del servizio WCF in modo asincrono'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 9a7bd1d67d9730c75e3f3f3b1eeb59f5d2d3c49a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204835"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="083eb-102">Procedura: Chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="083eb-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="083eb-103">In questo argomento viene illustrato come un client può accedere a un'operazione del servizio in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="083eb-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="083eb-104">Il servizio in questo argomento implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="083eb-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="083eb-105">Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="083eb-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="083eb-106">(Per altre informazioni sul modello di chiamata asincrono basato su eventi, vedere [programmazione multithreading con il modello asincrono basato su eventi](https://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="083eb-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="083eb-107">Per un esempio che illustra come implementare un'operazione in modo asincrono in un servizio, vedere [come: Implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="083eb-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="083eb-108">Per altre informazioni sulle operazioni sincrone e asincrone, vedere [sincrono e alle operazioni asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="083eb-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="083eb-109">Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="083eb-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="083eb-110">Per informazioni sulle chiamate asincrone utilizzando il <xref:System.ServiceModel.ChannelFactory%601>, vedere [come: Chiamare le operazioni in modo asincrono usando una Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="083eb-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="083eb-111">Routine</span><span class="sxs-lookup"><span data-stu-id="083eb-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="083eb-112">Per chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="083eb-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="083eb-113">Eseguire la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento sia con i `/async` e il `/tcv:Version35` opzioni di comando come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="083eb-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="083eb-114">Questa operazione genera, oltre alle operazioni sincrone e standard basate su delegati asincroni, una classe client WCF che contiene:</span><span class="sxs-lookup"><span data-stu-id="083eb-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    -   <span data-ttu-id="083eb-115">Due <`operationName` > `Async` operazioni per l'uso con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="083eb-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="083eb-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="083eb-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="083eb-117">Eventi completati dall'operazione del form <`operationName` > `Completed` per l'uso con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="083eb-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="083eb-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="083eb-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType> <span data-ttu-id="083eb-119">i tipi per ogni operazione (nel formato <`operationName`>`CompletedEventArgs`) per l'uso con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="083eb-119">types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="083eb-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="083eb-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  <span data-ttu-id="083eb-121">Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="083eb-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  <span data-ttu-id="083eb-122">Prima di chiamare l'operazione, usare un nuovo oggetto generico <xref:System.EventHandler%601?displayProperty=nameWithType> di tipo <`operationName` > `EventArgs` per aggiungere il metodo del gestore (creato nel passaggio precedente) per la <`operationName` > `Completed` evento.</span><span class="sxs-lookup"><span data-stu-id="083eb-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="083eb-123">Chiamare quindi il <`operationName` > `Async` (metodo).</span><span class="sxs-lookup"><span data-stu-id="083eb-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="083eb-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="083eb-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="083eb-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="083eb-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="083eb-126">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="083eb-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="083eb-127">Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="083eb-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="083eb-128">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="083eb-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="083eb-129">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="083eb-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="083eb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="083eb-130">See also</span></span>

- [<span data-ttu-id="083eb-131">Procedura: Implementare un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="083eb-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
