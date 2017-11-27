---
title: 'Procedura: chiamare le operazioni in modo asincrono tramite una channel factory'
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
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c907ed4c5c8cc76899d4f785ef1abf5a2821274f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a><span data-ttu-id="cd0cb-102">Procedura: chiamare le operazioni in modo asincrono tramite una channel factory</span><span class="sxs-lookup"><span data-stu-id="cd0cb-102">How to: Call Operations Asynchronously Using a Channel Factory</span></span>
<span data-ttu-id="cd0cb-103">In questo argomento viene illustrato in che modo un client può accedere a un'operazione del servizio in modalità asincrona quando si usa un'applicazione client basata su <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-103">This topic covers how a client can access a service operation asynchronously when using a <xref:System.ServiceModel.ChannelFactory%601>-based client application.</span></span> <span data-ttu-id="cd0cb-104">Quando si usa un oggetto <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> per richiamare un servizio, è possibile usare il modello di chiamata asincrono basato su eventi.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-104">(When using a <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> object to invoke a service you can use the event-driven asynchronous calling model.</span></span> <span data-ttu-id="cd0cb-105">Per ulteriori informazioni, vedere [procedura: chiamare servizio operazioni in modo asincrono](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="cd0cb-105">For more information, see [How to: Call Service Operations Asynchronously](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="cd0cb-106">Per ulteriori informazioni sul modello di chiamata asincrono basato su eventi, vedere [la programmazione multithreading con il modello asincrono basato su eventi](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).)</span><span class="sxs-lookup"><span data-stu-id="cd0cb-106">For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).)</span></span>  
  
 <span data-ttu-id="cd0cb-107">Il servizio in questo argomento implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-107">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="cd0cb-108">Il client può chiamare in modo asincrono le operazioni su tale interfaccia, il che significa che le operazioni come `Add` vengono suddivise in due metodi, `BeginAdd` ed `EndAdd`, il primo dei quali avvia la chiamata e il secondo recupera il risultato al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-108">The client can call the operations on this interface asynchronously, which means that operations like `Add` are split into two methods, `BeginAdd` and `EndAdd`, the former of which initiates the call and the latter of which retrieves the result when the operation completes.</span></span> <span data-ttu-id="cd0cb-109">Per un esempio che illustra come implementare un'operazione in modo asincrono in un servizio, vedere [procedura: implementare un'operazione del servizio asincrona](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="cd0cb-109">For an example showing how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="cd0cb-110">Per informazioni dettagliate sulle operazioni sincrone e asincrone, vedere [sincrono e alle operazioni asincrone](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cd0cb-110">For details about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="cd0cb-111">Routine</span><span class="sxs-lookup"><span data-stu-id="cd0cb-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="cd0cb-112">Per chiamare operazioni del servizio WCF in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="cd0cb-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="cd0cb-113">Eseguire il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento con il `/async` opzione come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with the `/async` option as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     <span data-ttu-id="cd0cb-114">Questo genera una versione client asincrona del contratto di servizio per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-114">This generates an asynchronous client version of the service contract for the operation.</span></span>  
  
2.  <span data-ttu-id="cd0cb-115">Creare una funzione di callback da chiamare al temine dell'operazione asincrona, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-115">Create a callback function to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  <span data-ttu-id="cd0cb-116">Per accedere in modo asincrono a un'operazione del servizio, creare il client, chiamare `Begin[Operation]` (ad esempio, `BeginAdd`) e specificare una funzione di callback, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-116">To access a service operation asynchronously, create the client and call the `Begin[Operation]` (for example, `BeginAdd`) and specify a callback function, as shown in the following sample code.</span></span>  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     <span data-ttu-id="cd0cb-117">Quando la funzione di callback viene eseguita, il client chiama `End<operation>``EndAdd` (ad esempio, ) per recuperare il risultato.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-117">When the callback function executes, the client calls `End<operation>` (for example, `EndAdd`) to retrieve the result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd0cb-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd0cb-118">Example</span></span>  
 <span data-ttu-id="cd0cb-119">Il servizio usato con il codice client della procedura precedente implementa l'interfaccia `ICalculator` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-119">The service that is used with the client code that is used in the preceding procedure implements the `ICalculator` interface as shown in the following code.</span></span> <span data-ttu-id="cd0cb-120">Sul lato del servizio, le operazioni `Add` e `Subtract` del contratto vengono richiamate in modo sincrono dal runtime [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], anche se i passaggi client precedenti vengono richiamati in modo asincrono sul client.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-120">On the service side, the `Add` and `Subtract` operations of the contract are invoked synchronously by the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] run time, even though the preceding client steps are invoked asynchronously on the client.</span></span> <span data-ttu-id="cd0cb-121">Le operazioni `Multiply` e `Divide` vengono usate per richiamare il servizio in modo asincrono sul lato del servizio, anche se il client le richiama in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-121">The `Multiply` and `Divide` operations are used to invoke the service asynchronously on the service side, even if the client invokes them synchronously.</span></span> <span data-ttu-id="cd0cb-122">In questo esempio la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> viene impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-122">This example sets the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property to `true`.</span></span> <span data-ttu-id="cd0cb-123">Tale impostazione della proprietà, in combinazione con l'implementazione del modello asincrono di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consente al runtime di richiamare in modo asincrono l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cd0cb-123">This property setting, in combination with the implementation of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] asynchronous pattern, tells the run time to invoke the operation asynchronously.</span></span>  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cd0cb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd0cb-124">See Also</span></span>  
 [<span data-ttu-id="cd0cb-125">: Contratto di servizio esempio asincrono</span><span class="sxs-lookup"><span data-stu-id="cd0cb-125">Service Contract: Asynchronous Sample</span></span>](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7)
