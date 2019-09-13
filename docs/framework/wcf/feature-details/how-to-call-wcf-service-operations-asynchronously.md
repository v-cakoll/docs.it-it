---
title: 'Procedura: Chiamare le operazioni del servizio WCF in modo asincrono'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2c0a6f1477ceec5471c22fa3e46d85f5856b298e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895071"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="0daea-102">Procedura: Chiamare le operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="0daea-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="0daea-103">In questo argomento viene illustrato come un client può accedere a un'operazione del servizio in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="0daea-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="0daea-104">Il servizio in questo argomento implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="0daea-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="0daea-105">Il client può chiamare le operazioni in questa interfaccia in modo asincrono utilizzando il modello di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="0daea-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="0daea-106">Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [programmazione multithreading con il modello asincrono basato su eventi](https://go.microsoft.com/fwlink/?LinkId=248184).</span><span class="sxs-lookup"><span data-stu-id="0daea-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="0daea-107">Per un esempio in cui viene illustrato come implementare un'operazione in modo asincrono in un servizio [, vedere Procedura: Implementare un'operazione](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)del servizio asincrona.</span><span class="sxs-lookup"><span data-stu-id="0daea-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="0daea-108">Per altre informazioni sulle operazioni sincrone e asincrone, vedere [operazioni sincrone e asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0daea-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0daea-109">Il modello di chiamata asincrono basato su eventi non è supportato quando si utilizza una classe <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="0daea-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="0daea-110">Per informazioni sull'esecuzione di chiamate asincrone mediante <xref:System.ServiceModel.ChannelFactory%601>, vedere [procedura: Chiamare le operazioni in modo asincrono utilizzando una](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)Channel factory.</span><span class="sxs-lookup"><span data-stu-id="0daea-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="0daea-111">Routine</span><span class="sxs-lookup"><span data-stu-id="0daea-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="0daea-112">Per chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="0daea-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="0daea-113">Eseguire lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con le `/async` opzioni e del `/tcv:Version35` comando insieme, come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="0daea-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="0daea-114">Questo genera, oltre alle operazioni asincrone basate su delegati sincroni e standard, una classe client WCF che contiene:</span><span class="sxs-lookup"><span data-stu-id="0daea-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="0daea-115">Due <`operationName` > operazionidautilizzareconl'approcciodichiamataasincrono`Async` basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="0daea-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0daea-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0daea-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="0daea-117">Gli eventi completati dell'operazione nel`operationName` form <> `Completed` per l'uso con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="0daea-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0daea-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0daea-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="0daea-119"><xref:System.EventArgs?displayProperty=nameWithType>tipi per ogni operazione (nel formato <`operationName`>`CompletedEventArgs`) da utilizzare con l'approccio di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="0daea-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0daea-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0daea-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="0daea-121">Nell'applicazione chiamante creare un metodo di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0daea-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="0daea-122">Prima di chiamare l'operazione, usare un nuovo oggetto <xref:System.EventHandler%601?displayProperty=nameWithType> generico di tipo`operationName` <`Completed` > `EventArgs` per aggiungere il metodo del gestore (creato nel passaggio precedente) all'evento`operationName` <> .</span><span class="sxs-lookup"><span data-stu-id="0daea-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="0daea-123">Chiamare quindi il metodo`operationName` <> `Async` .</span><span class="sxs-lookup"><span data-stu-id="0daea-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="0daea-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0daea-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="0daea-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="0daea-125">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0daea-126">Le linee guida di progettazione per il modello asincrono basato su eventi indicano che, se vengono restituiti più valori, un valore viene restituito come proprietà `Result` e i restanti valori sono restituiti come proprietà nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0daea-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0daea-127">Di conseguenza, è possibile che, se un client importa metadati utilizzando le opzioni di comando asincrone basate su eventi e l'operazione restituisce più valori, l'oggetto predefinito <xref:System.EventArgs> restituisce un valore come proprietà `Result` e i restanti valori come proprietà dell’oggetto <xref:System.EventArgs>. Se si desidera ricevere l’oggetto del messaggio come proprietà `Result` e i valori restituiti come proprietà in quell’oggetto, utilizzare l’opzione di comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="0daea-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="0daea-128">Questa operazione genera una firma che restituisce il messaggio di risposta come proprietà `Result` nell’oggetto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0daea-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0daea-129">Pertanto, tutti i valori restituiti interni sono proprietà dell’oggetto del messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="0daea-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0daea-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0daea-130">See also</span></span>

- [<span data-ttu-id="0daea-131">Procedura: Implementare un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="0daea-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
