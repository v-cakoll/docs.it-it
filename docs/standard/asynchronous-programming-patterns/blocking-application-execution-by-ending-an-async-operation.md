---
title: Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121320"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="5505c-102">Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="5505c-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="5505c-103">Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona devono restare bloccati fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5505c-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="5505c-104">Usare una delle opzioni seguenti per bloccare il thread principale dell'applicazione in attesa del completamento di un'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="5505c-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="5505c-105">Chiamare il metodo **End**_OperationName_ delle operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="5505c-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="5505c-106">Questo metodo viene dimostrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5505c-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="5505c-107">Usare la proprietà <xref:System.IAsyncResult.AsyncWaitHandle%2A> dell'interfaccia <xref:System.IAsyncResult> restituita dal metodo **Begin**_OperationName_ dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="5505c-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="5505c-108">Per un esempio relativo all'uso di questo approccio, vedere [Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="5505c-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="5505c-109">Le applicazioni che usano il metodo **End**_NomeOperazione_ per il blocco fino al completamento di un'operazione asincrona in genere chiamano il metodo **Begin**_NomeOperazione_, effettuano qualsiasi attività eseguibile senza i risultati dell'operazione e quindi chiamano **End**_NomeOperazione_.</span><span class="sxs-lookup"><span data-stu-id="5505c-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5505c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="5505c-110">Example</span></span>  
 <span data-ttu-id="5505c-111">L'esempio di codice seguente illustra l'uso dei metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni di Domain Name System per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5505c-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="5505c-112">Si noti che viene passato `null` (`Nothing` in Visual Basic) per i parametri `requestCallback` e `stateObject` di <xref:System.Net.Dns.BeginGetHostByName%2A> perché questi argomenti non sono necessari quando si usa questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5505c-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5505c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5505c-113">See also</span></span>

- <span data-ttu-id="5505c-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="5505c-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="5505c-115">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5505c-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
