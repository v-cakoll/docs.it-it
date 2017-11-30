---
title: 'Procedura: mettersi in ascolto di richieste di annullamento tramite polling'
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="ce4ed-102">Procedura: mettersi in ascolto di richieste di annullamento tramite polling</span><span class="sxs-lookup"><span data-stu-id="ce4ed-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="ce4ed-103">Nell'esempio seguente viene illustrato un modo che il codice utente può eseguire il polling di un token di annullamento a intervalli regolari per vedere se è stato richiesto l'annullamento dal thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="ce4ed-104">Questo esempio viene utilizzato il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo, ma lo stesso modello si applica alle operazioni asincrone create direttamente mediante il <xref:System.Threading.ThreadPool?displayProperty=nameWithType> tipo o <xref:System.Threading.Thread?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce4ed-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce4ed-105">Example</span></span>  
 <span data-ttu-id="ce4ed-106">Polling richiede un tipo di codice di ciclo o ricorsivo in grado di leggere periodicamente il valore della proprietà booleana <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="ce4ed-107">Se si utilizza il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo ed è in attesa per l'attività da completare sul thread chiamante, è possibile utilizzare il <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> per controllare la proprietà e generare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="ce4ed-108">Tramite questo metodo, assicurarsi che l'eccezione corretta è generata in risposta a una richiesta.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="ce4ed-109">Se si utilizza un <xref:System.Threading.Tasks.Task>, quindi chiamare questo metodo è migliore generazione manuale di un <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="ce4ed-110">Se non si dispone generare l'eccezione, quindi è solo possibile controllare la proprietà e restituito dal metodo, se la proprietà è `true`.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="ce4ed-111">La chiamata <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> è estremamente veloce e non comporta un sovraccarico significativo nei cicli.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="ce4ed-112">Se si chiama <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, è necessario verificare in modo esplicito il <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà se si dispone di altre attività da eseguire in risposta all'annullamento oltre alla generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="ce4ed-113">In questo esempio, si noterà che il codice effettivamente accede alla proprietà due volte: una volta tramite accesso esplicito e nuovamente il <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="ce4ed-114">Tuttavia, poiché l'operazione di lettura di <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà include solo un'istruzione per l'accesso di lettura volatile, il doppio accesso non è significativo dal punto di vista delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="ce4ed-115">È preferibile chiamare il metodo anziché generare manualmente il <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="ce4ed-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4ed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce4ed-116">See Also</span></span>  
 [<span data-ttu-id="ce4ed-117">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="ce4ed-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
