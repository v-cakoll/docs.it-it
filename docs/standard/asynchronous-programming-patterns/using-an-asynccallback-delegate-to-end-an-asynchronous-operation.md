---
title: Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: c3cac2db57a24bf6a0f5640e4ad8101686e6c3e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130928"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="74738-102">Utilizzo di un delegato AsyncCallback per terminare un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="74738-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="74738-103">Le applicazioni che possono eseguire altre attività durante l'attesa dei risultati di un'operazione asincrona non devono bloccare lo stato di attesa fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="74738-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="74738-104">Usare una delle opzioni seguenti per continuare a eseguire le istruzioni durante l'attesa del completamento di un'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="74738-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="74738-105">Usare un delegato <xref:System.AsyncCallback> per elaborare i risultati dell'operazione asincrona in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="74738-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="74738-106">Questo metodo viene dimostrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="74738-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="74738-107">Usare la proprietà <xref:System.IAsyncResult.IsCompleted%2A> dell'oggetto <xref:System.IAsyncResult> restituito dal metodo **Begin**_NomeOperazione_ dell'operazione asincrona per determinare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="74738-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="74738-108">Per un esempio che illustri questo approccio, vedere [Esecuzione del polling dello stato di un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="74738-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74738-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="74738-109">Example</span></span>  
 <span data-ttu-id="74738-110">Nell'esempio di codice seguente viene illustrato come usare metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni sul DNS (Domain Name System) per i computer specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="74738-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="74738-111">Questo esempio crea un delegato <xref:System.AsyncCallback> che fa riferimento al metodo `ProcessDnsInformation`.</span><span class="sxs-lookup"><span data-stu-id="74738-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="74738-112">Questo metodo viene chiamato una volta per ogni richiesta asincrona per le informazioni DNS.</span><span class="sxs-lookup"><span data-stu-id="74738-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="74738-113">Si noti che l'host specificato dall'utente viene passato al parametro <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="74738-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="74738-114">Per un esempio che illustri la definizione e l'uso di un oggetto di stato più complesso, vedere [Uso di un oggetto di stato e di un delegato AsyncCallback](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="74738-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="74738-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74738-115">See also</span></span>

- <span data-ttu-id="74738-116">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="74738-116">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="74738-117">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="74738-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="74738-118">Chiamata di metodi asincroni tramite IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="74738-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)
- [<span data-ttu-id="74738-119">Uso di un oggetto di stato e di un delegato AsyncCallback</span><span class="sxs-lookup"><span data-stu-id="74738-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
