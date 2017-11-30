---
title: Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="5dfc6-102">Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="5dfc6-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="5dfc6-103">Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona, devono restare bloccati fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="5dfc6-104">Bloccare il thread principale dell'applicazione durante l'attesa di completamento di un'operazione asincrona, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5dfc6-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="5dfc6-105">Utilizzare il <xref:System.IAsyncResult.AsyncWaitHandle%2A> proprietà del <xref:System.IAsyncResult> restituito tramite l'operazione asincrona **iniziare** *OperationName* metodo.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="5dfc6-106">Questo approccio viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="5dfc6-107">Chiamare l'operazione asincrona **fine** *OperationName* metodo.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="5dfc6-108">Per un esempio che illustra questo approccio, vedere [il blocco di esecuzione dell'applicazione terminando un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="5dfc6-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="5dfc6-109">Le applicazioni che utilizzano uno o più <xref:System.Threading.WaitHandle> verranno chiamato in genere gli oggetti di blocco fino al completamento di un'operazione asincrona di **iniziare** *OperationName* (metodo), eseguire le operazioni che possono essere eseguite senza i risultati dell'operazione e blocco finché l'operazione di operazioni asincrone completa.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="5dfc6-110">Un'applicazione può essere bloccata in una singola operazione chiamando uno del <xref:System.Threading.WaitHandle.WaitOne%2A> metodi usando il <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="5dfc6-111">Per il blocco durante l'attesa di un set di operazioni asincrone per completare, archiviare associato <xref:System.IAsyncResult.AsyncWaitHandle%2A> oggetti in una matrice e chiamare uno del <xref:System.Threading.WaitHandle.WaitAll%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="5dfc6-112">Per il blocco durante l'attesa per uno qualsiasi di un set di operazioni asincrone per completare, archiviare associato <xref:System.IAsyncResult.AsyncWaitHandle%2A> oggetti in una matrice e chiamare uno del <xref:System.Threading.WaitHandle.WaitAny%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dfc6-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="5dfc6-113">Example</span></span>  
 <span data-ttu-id="5dfc6-114">Esempio di codice seguente viene illustrato l'utilizzo di metodi asincroni nella classe DNS per recuperare le informazioni di sistema di nome di dominio per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="5dfc6-115">Nell'esempio viene illustrato il blocco utilizzando la <xref:System.Threading.WaitHandle> associato all'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="5dfc6-116">Si noti che `null` (`Nothing` in Visual Basic) viene passato il <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` e `stateObject` parametri perché non sono necessarie quando si utilizza questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5dfc6-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5dfc6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dfc6-117">See Also</span></span>  
 <span data-ttu-id="5dfc6-118">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi)</span><span class="sxs-lookup"><span data-stu-id="5dfc6-118">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>  
 [<span data-ttu-id="5dfc6-119">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5dfc6-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
