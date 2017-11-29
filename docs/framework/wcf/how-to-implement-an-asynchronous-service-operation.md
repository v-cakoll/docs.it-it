---
title: 'Procedura: implementare un''operazione del servizio asincrona'
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
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 65cd45a2510aa43c3f0c58a7cbf78c13e47d821e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="d68b2-102">Procedura: implementare un'operazione del servizio asincrona</span><span class="sxs-lookup"><span data-stu-id="d68b2-102">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="d68b2-103">Nelle applicazioni [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], un'operazione del servizio può essere implementata in modo sincrono o asincrono senza imporre al client la modalità di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d68b2-103">In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="d68b2-104">È possibile, ad esempio, che operazioni del servizio asincrone vengano chiamate in modo sincrono e che operazioni del servizio sincrone vengano chiamate in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="d68b2-104">For example, asynchronous service operations can be calling synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="d68b2-105">Per un esempio che illustra come chiamare un'operazione in modo asincrono in un'applicazione client, vedere [procedura: chiamare servizio operazioni in modo asincrono](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="d68b2-105">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d68b2-106">operazioni sincrone e asincrone, vedere [progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md) e [sincrono e alle operazioni asincrone](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d68b2-106"> synchronous and asynchronous operations, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md) and [Synchronous and Asynchronous Operations](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="d68b2-107">In questo argomento viene descritta la struttura di base di un'operazione del servizio asincrona (il codice non è completo).</span><span class="sxs-lookup"><span data-stu-id="d68b2-107">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="d68b2-108">Per un esempio completo di lati client e servizio vedere [asincrono](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).</span><span class="sxs-lookup"><span data-stu-id="d68b2-108">For a complete example of both the service and client sides see [Asynchronous](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="d68b2-109">Implementazione di un'operazione del servizio in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="d68b2-109">Implement a service operation asynchronously</span></span>  
  
1.  <span data-ttu-id="d68b2-110">Nel contratto di servizio, dichiarare una coppia di metodi asincroni in base alle linee guida di progettazione asincrona .NET.</span><span class="sxs-lookup"><span data-stu-id="d68b2-110">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="d68b2-111">Il metodo `Begin` prende un parametro, un oggetto callback e un oggetto di stato e restituisce un <xref:System.IAsyncResult?displayProperty=nameWithType> e un metodo `End` corrispondente che prende un <xref:System.IAsyncResult?displayProperty=nameWithType> e restituisce il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="d68b2-111">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="d68b2-112">Per ulteriori informazioni sulle chiamate asincrone, vedere [Asynchronous Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).</span><span class="sxs-lookup"><span data-stu-id="d68b2-112">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).</span></span>  
  
2.  <span data-ttu-id="d68b2-113">Contrassegnare il metodo `Begin` della coppia di metodi asincroni con l'attributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> e impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="d68b2-113">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="d68b2-114">Nel codice seguente, ad esempio, vengono eseguiti i passaggi 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="d68b2-114">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  <span data-ttu-id="d68b2-115">Implementare la coppia di metodi `Begin/End` nella classe del servizio in base alle linee guida di progettazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="d68b2-115">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="d68b2-116">Nell'esempio di codice seguente viene illustrata un'implementazione nella quale una stringa viene scritta nella console sia nella parte `Begin` che nella parte `End` dell'operazione del servizio asincrona e viene restituito al client il valore restituito dell'operazione `End`.</span><span class="sxs-lookup"><span data-stu-id="d68b2-116">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="d68b2-117">Per un esempio completo di codice, vedere la sezione degli esempi.</span><span class="sxs-lookup"><span data-stu-id="d68b2-117">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d68b2-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d68b2-118">Example</span></span>  
 <span data-ttu-id="d68b2-119">Negli esempi di codice seguenti viene illustrato:</span><span class="sxs-lookup"><span data-stu-id="d68b2-119">The following code examples show:</span></span>  
  
1.  <span data-ttu-id="d68b2-120">Un'interfaccia del contratto di servizio con:</span><span class="sxs-lookup"><span data-stu-id="d68b2-120">A service contract interface with:</span></span>  
  
    1.  <span data-ttu-id="d68b2-121">Un'operazione `SampleMethod` sincrona.</span><span class="sxs-lookup"><span data-stu-id="d68b2-121">A synchronous `SampleMethod` operation.</span></span>  
  
    2.  <span data-ttu-id="d68b2-122">Un'operazione `BeginSampleMethod` asincrona.</span><span class="sxs-lookup"><span data-stu-id="d68b2-122">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3.  <span data-ttu-id="d68b2-123">Asincrono `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` coppia di operazioni.</span><span class="sxs-lookup"><span data-stu-id="d68b2-123">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2.  <span data-ttu-id="d68b2-124">Un'implementazione del servizio tramite un oggetto <xref:System.IAsyncResult?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d68b2-124">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d68b2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d68b2-125">See Also</span></span>  
 [<span data-ttu-id="d68b2-126">Progettazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="d68b2-126">Designing Service Contracts</span></span>](../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="d68b2-127">Operazioni sincrone e asincrone</span><span class="sxs-lookup"><span data-stu-id="d68b2-127">Synchronous and Asynchronous Operations</span></span>](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
