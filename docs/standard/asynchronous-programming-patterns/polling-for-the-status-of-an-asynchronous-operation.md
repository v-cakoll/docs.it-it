---
title: Esecuzione del polling dello stato di un'operazione asincrona
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: ff9cefc73adfe1ece1bf7545c75ccb6cc618e89f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123969"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="c28a5-102">Esecuzione del polling dello stato di un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="c28a5-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="c28a5-103">Le applicazioni che possono eseguire altre attività durante l'attesa dei risultati di un'operazione asincrona non devono bloccare lo stato di attesa fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c28a5-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="c28a5-104">Usare una delle opzioni seguenti per continuare a eseguire le istruzioni durante l'attesa del completamento di un'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="c28a5-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="c28a5-105">Utilizzare <xref:System.IAsyncResult.IsCompleted%2A> la proprietà <xref:System.IAsyncResult> dell'oggetto restituito dal metodo **Begin**_NomeOperazione_ dell'operazione asincrona per determinare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c28a5-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="c28a5-106">Questo approccio è noto come polling e viene illustrato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c28a5-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="c28a5-107">Usare un delegato <xref:System.AsyncCallback> per elaborare i risultati dell'operazione asincrona in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="c28a5-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="c28a5-108">Per un esempio relativo all'uso di questo approccio, vedere [Uso di un delegato AsyncCallback per terminare un'operazione asincrona](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="c28a5-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c28a5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c28a5-109">Example</span></span>  
 <span data-ttu-id="c28a5-110">L'esempio di codice seguente illustra l'uso dei metodi asincroni nella classe <xref:System.Net.Dns> per recuperare le informazioni di Domain Name System per un computer specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c28a5-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="c28a5-111">In questo esempio viene avviata l'operazione asincrona e vengono quindi stampati punti (".") nella console fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c28a5-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="c28a5-112">Si noti che per i parametri <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> e <xref:System.Object> viene passato **null** (**Nothing** in Visual Basic) poiché questi argomenti non sono obbligatori quando si usa questo approccio.</span><span class="sxs-lookup"><span data-stu-id="c28a5-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c28a5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c28a5-113">See also</span></span>

- <span data-ttu-id="c28a5-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)</span><span class="sxs-lookup"><span data-stu-id="c28a5-114">[Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)</span></span>
- [<span data-ttu-id="c28a5-115">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c28a5-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
