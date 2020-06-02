---
title: Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 6184e52c3f6e39e452331af27b83520e498062aa
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289928"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="b84e2-102">Blocco dell'esecuzione dell'applicazione tramite AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="b84e2-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="b84e2-103">Le applicazioni che non possono continuare a eseguire altre attività in attesa dei risultati di un'operazione asincrona devono restare bloccati fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b84e2-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="b84e2-104">Usare una delle opzioni seguenti per bloccare il thread principale dell'applicazione in attesa del completamento di un'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="b84e2-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="b84e2-105">Usare la proprietà <xref:System.IAsyncResult.AsyncWaitHandle%2A> dell'interfaccia <xref:System.IAsyncResult> restituita dal metodo **Begin**_OperationName_ dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b84e2-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="b84e2-106">Questo metodo viene dimostrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b84e2-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="b84e2-107">Chiamare il metodo **End**_OperationName_ dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b84e2-107">Call the asynchronous operation's **End**_OperationName_ method.</span></span> <span data-ttu-id="b84e2-108">Per un esempio relativo all'uso di questo approccio, vedere [Blocco dell'esecuzione dell'applicazione terminando un'operazione asincrona](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="b84e2-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="b84e2-109">Le applicazioni che usano uno o più oggetti <xref:System.Threading.WaitHandle> per il blocco fino al completamento di un'operazione asincrona chiameranno in genere il metodo **Begin**_OperationName_, effettueranno qualsiasi attività eseguibile senza i risultati dell'operazione e quindi verranno bloccate fino al completamento delle operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="b84e2-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="b84e2-110">Un'applicazione può essere bloccata su una singola operazione chiamando uno dei metodi <xref:System.Threading.WaitHandle.WaitOne%2A> con la proprietà <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="b84e2-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="b84e2-111">Per applicare il blocco in attesa del completamento di un set di operazioni asincrone, archiviare gli oggetti <xref:System.IAsyncResult.AsyncWaitHandle%2A> associati in una matrice e chiamare uno dei metodi <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="b84e2-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="b84e2-112">Per applicare il blocco in attesa del completamento di un'operazione asincrona di un set, archiviare gli oggetti <xref:System.IAsyncResult.AsyncWaitHandle%2A> associati in una matrice e chiamare uno dei metodi <xref:System.Threading.WaitHandle.WaitAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="b84e2-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b84e2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b84e2-113">Example</span></span>  
 <span data-ttu-id="b84e2-114">L'esempio di codice seguente illustra l'uso dei metodi asincroni nella classe DNS per recuperare le informazioni di Domain Name System per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b84e2-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="b84e2-115">L'esempio illustra il blocco tramite la classe <xref:System.Threading.WaitHandle> associata all'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b84e2-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="b84e2-116">Si noti che viene passato `null` (`Nothing` in Visual Basic) per i parametri `requestCallback` e `stateObject` di <xref:System.Net.Dns.BeginGetHostByName%2A> perché non sono necessari quando si usa questo approccio.</span><span class="sxs-lookup"><span data-stu-id="b84e2-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b84e2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b84e2-117">See also</span></span>

- <span data-ttu-id="b84e2-118">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="b84e2-118">[Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="b84e2-119">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="b84e2-119">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
