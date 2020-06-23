---
title: 'Procedura: chiamare operazioni del servizio WCF in modo asincrono'
description: Informazioni su come creare un client WCF in grado di accedere a un'operazione del servizio in modo asincrono usando il modello di chiamata asincrono basato su eventi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: aa31f64473111800f4cd01907a0446c94f368456
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247234"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="3fdc5-103">Procedura: chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="3fdc5-103">How to: Call WCF Service Operations Asynchronously</span></span>

<span data-ttu-id="3fdc5-104">Questo articolo illustra in che modo un client può accedere a un'operazione del servizio in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-104">This article covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="3fdc5-105">Il servizio in questo articolo implementa l' `ICalculator` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-105">The service in this article implements the `ICalculator` interface.</span></span> <span data-ttu-id="3fdc5-106">Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-106">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="3fdc5-107">Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [programmazione multithreading con il modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="3fdc5-107">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span></span> <span data-ttu-id="3fdc5-108">Per un esempio in cui viene illustrato come implementare un'operazione in modo asincrono in un servizio, vedere [procedura: implementare un'operazione del servizio asincrona](../how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="3fdc5-108">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="3fdc5-109">Per altre informazioni sulle operazioni sincrone e asincrone, vedere [operazioni sincrone e asincrone](../synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3fdc5-109">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fdc5-110">Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-110">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="3fdc5-111">Per informazioni sull'esecuzione di chiamate asincrone mediante <xref:System.ServiceModel.ChannelFactory%601> , vedere [procedura: chiamare operazioni in modo asincrono utilizzando una channel factory](how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="3fdc5-111">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="3fdc5-112">Procedura</span><span class="sxs-lookup"><span data-stu-id="3fdc5-112">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="3fdc5-113">Per chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="3fdc5-113">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="3fdc5-114">Eseguire lo strumento [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con entrambe le `/async` Opzioni e il `/tcv:Version35` comando insieme, come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-114">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="3fdc5-115">Questo genera, oltre alle operazioni asincrone basate su delegati sincroni e standard, una classe client WCF che contiene:</span><span class="sxs-lookup"><span data-stu-id="3fdc5-115">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="3fdc5-116">Due <`operationName` > `Async` operazioni da utilizzare con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-116">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="3fdc5-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdc5-117">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="3fdc5-118">Gli eventi completati dell'operazione nel form <`operationName` > `Completed` per l'uso con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-118">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="3fdc5-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdc5-119">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="3fdc5-120"><xref:System.EventArgs?displayProperty=nameWithType>tipi per ogni operazione (nel formato <`operationName` > `CompletedEventArgs` ) da utilizzare con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-120"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="3fdc5-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdc5-121">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="3fdc5-122">Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-122">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="3fdc5-123">Prima di chiamare l'operazione, usare un nuovo oggetto generico <xref:System.EventHandler%601?displayProperty=nameWithType> di tipo <`operationName` > `EventArgs` per aggiungere il metodo del gestore (creato nel passaggio precedente) all' `operationName` > `Completed` evento <.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-123">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="3fdc5-124">Chiamare quindi il `operationName` > `Async` Metodo <.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-124">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="3fdc5-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdc5-125">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="3fdc5-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fdc5-126">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fdc5-127">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-127">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="3fdc5-128">Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-128">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="3fdc5-129">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-129">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="3fdc5-130">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="3fdc5-130">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3fdc5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fdc5-131">See also</span></span>

- [<span data-ttu-id="3fdc5-132">Procedura: Implementare un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="3fdc5-132">How to: Implement an Asynchronous Service Operation</span></span>](../how-to-implement-an-asynchronous-service-operation.md)
