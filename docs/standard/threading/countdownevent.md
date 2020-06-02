---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: 8ed1414ad377015400d9e126d924bf426fbc753d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277856"
---
# <a name="countdownevent"></a><span data-ttu-id="b1bd5-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="b1bd5-102">CountdownEvent</span></span>
<span data-ttu-id="b1bd5-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> è una primitiva di sincronizzazione che sblocca i thread in attesa dopo che è stata segnalata un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="b1bd5-104"><xref:System.Threading.CountdownEvent> è progettato per gli scenari in cui altrimenti sarebbe necessario usare <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> e diminuire manualmente una variabile prima di segnalare l'evento.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="b1bd5-105">In uno scenario di fork/join, ad esempio, è sufficiente creare una classe <xref:System.Threading.CountdownEvent> con un conteggio di segnali pari a 5 e quindi avviare cinque elementi di lavoro nel pool di thread e fare in modo che ogni elemento di lavoro chiami <xref:System.Threading.CountdownEvent.Signal%2A> quando viene completato.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="b1bd5-106">Ogni chiamata a <xref:System.Threading.CountdownEvent.Signal%2A> riduce il conteggio di segnali di 1.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="b1bd5-107">Nel thread principale la chiamata a <xref:System.Threading.CountdownEvent.Wait%2A> verrà bloccata finché il conteggio dei segnali sarà pari a zero.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1bd5-108">Per il codice che non deve interagire con le API di sincronizzazione di .NET Framework legacy, considerare la possibilità di usare oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o il metodo <xref:System.Threading.Tasks.Parallel.Invoke%2A> per un approccio ancora più semplice per esprimere il parallelismo fork/join.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="b1bd5-109"><xref:System.Threading.CountdownEvent> ha queste funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="b1bd5-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
- <span data-ttu-id="b1bd5-110">L'operazione di attesa può essere annullata tramite i token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
- <span data-ttu-id="b1bd5-111">Il conteggio dei segnali può essere incrementato dopo la creazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-111">Its signal count can be incremented after the instance is created.</span></span>  
  
- <span data-ttu-id="b1bd5-112">Le istanze possono essere riutilizzate dopo che <xref:System.Threading.CountdownEvent.Wait%2A> è stato restituito chiamando il metodo <xref:System.Threading.CountdownEvent.Reset%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
- <span data-ttu-id="b1bd5-113">Le istanze espongono una classe <xref:System.Threading.WaitHandle> per l'integrazione con altre API di sincronizzazione di .NET Framework, ad esempio <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="b1bd5-114">Utilizzo di base</span><span class="sxs-lookup"><span data-stu-id="b1bd5-114">Basic Usage</span></span>  
 <span data-ttu-id="b1bd5-115">L'esempio seguente illustra come usare una classe <xref:System.Threading.CountdownEvent> con gli elementi di lavoro <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="b1bd5-116">CountdownEvent con annullamento</span><span class="sxs-lookup"><span data-stu-id="b1bd5-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="b1bd5-117">L'esempio seguente illustrato come annullare l'operazione di attesa in <xref:System.Threading.CountdownEvent> usando un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="b1bd5-118">Lo schema di base segue il modello per l'annullamento unificato, introdotto in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-118">The basic pattern follows the model for unified cancellation, which is introduced in .NET Framework 4.</span></span> <span data-ttu-id="b1bd5-119">Per altre informazioni, vedere [annullamento in thread gestiti](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="b1bd5-119">For more information, see [Cancellation in Managed Threads](cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="b1bd5-120">Si noti che l'operazione di attesa non annulla i thread che la segnalano.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="b1bd5-121">L'annullamento viene in genere applicato a un'operazione logica, inclusa l'attesa dell'evento, ma anche di tutti gli elementi di lavoro che l'attesa sta sincronizzando.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="b1bd5-122">In questo esempio a ogni elemento di lavoro viene passata una copia dello stesso token di annullamento in modo che possa rispondere alla richiesta di annullamento.</span><span class="sxs-lookup"><span data-stu-id="b1bd5-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1bd5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1bd5-123">See also</span></span>

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
