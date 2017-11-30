---
title: Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="983d3-102">Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="983d3-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="983d3-103">Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona, devono restare bloccati fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="983d3-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="983d3-104">Bloccare il thread principale dell'applicazione durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="983d3-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="983d3-105">Chiamare le operazioni asincrone **fine** *OperationName* metodo.</span><span class="sxs-lookup"><span data-stu-id="983d3-105">Call the asynchronous operations **End** *OperationName* method.</span></span> <span data-ttu-id="983d3-106">Questo approccio viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="983d3-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="983d3-107">Utilizzare il <xref:System.IAsyncResult.AsyncWaitHandle%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo.</span><span class="sxs-lookup"><span data-stu-id="983d3-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="983d3-108">Per un esempio che illustra questo approccio, vedere [il blocco di esecuzione dell'applicazione tramite AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="983d3-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="983d3-109">Le applicazioni che utilizzano il **fine** *OperationName* verrà in genere chiamata al metodo di blocco fino al completamento di un'operazione asincrona di **iniziare**  *OperationName* (metodo), eseguire le operazioni che possono essere eseguita senza i risultati dell'operazione e quindi chiamano **fine** *OperationName*.</span><span class="sxs-lookup"><span data-stu-id="983d3-109">Applications that use the **End** *OperationName* method to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then call **End** *OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="983d3-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="983d3-110">Example</span></span>  
 <span data-ttu-id="983d3-111">Esempio di codice seguente viene illustrato come utilizzare metodi asincroni nel <xref:System.Net.Dns> classe per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="983d3-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="983d3-112">Si noti che `null` (`Nothing` in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` e `stateObject` parametri poiché questi argomenti non sono necessari quando si utilizza questo approccio.</span><span class="sxs-lookup"><span data-stu-id="983d3-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="983d3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983d3-113">See Also</span></span>  
 <span data-ttu-id="983d3-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="983d3-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 [<span data-ttu-id="983d3-115">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="983d3-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
