---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="8f9cb-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="8f9cb-102">CountdownEvent</span></span>
<span data-ttu-id="8f9cb-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>è una primitiva di sincronizzazione che sblocca i thread in attesa dopo che è stato segnalato un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="8f9cb-104"><xref:System.Threading.CountdownEvent>è progettato per scenari in cui in caso contrario è necessario utilizzare un <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> e diminuire manualmente una variabile prima di segnalare l'evento.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="8f9cb-105">In uno scenario di divisione e unione, ad esempio, è possibile creare solo un <xref:System.Threading.CountdownEvent> che presenta un numero di segnale di 5 e quindi avviare cinque elementi di lavoro sul thread del pool e ogni chiamata di elemento di lavoro <xref:System.Threading.CountdownEvent.Signal%2A> quando viene completato.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="8f9cb-106">Ogni chiamata a <xref:System.Threading.CountdownEvent.Signal%2A> decrementa il conteggio segnali 1.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="8f9cb-107">Nel thread principale, la chiamata a <xref:System.Threading.CountdownEvent.Wait%2A> verrà bloccata finché il segnale di conteggio è zero.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f9cb-108">Per il codice che non devono interagire con l'API di sincronizzazione di .NET Framework legacy, è consigliabile utilizzare <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> oggetti o <xref:System.Threading.Tasks.Parallel.Invoke%2A> metodo per un approccio ancora più semplice per esprimere il parallelismo fork-join.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="8f9cb-109"><xref:System.Threading.CountdownEvent>dispone di queste funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="8f9cb-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="8f9cb-110">L'operazione di attesa può essere annullata tramite i token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="8f9cb-111">Il numero di segnale può essere incrementato dopo la creazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="8f9cb-112">Istanze possono essere riutilizzate dopo <xref:System.Threading.CountdownEvent.Wait%2A> ha restituito chiamando il <xref:System.Threading.CountdownEvent.Reset%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="8f9cb-113">Le istanze espongono un <xref:System.Threading.WaitHandle> per l'integrazione con altre API di sincronizzazione di .NET Framework, ad esempio <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="8f9cb-114">Utilizzo di base</span><span class="sxs-lookup"><span data-stu-id="8f9cb-114">Basic Usage</span></span>  
 <span data-ttu-id="8f9cb-115">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.CountdownEvent> con <xref:System.Threading.ThreadPool> gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="8f9cb-116">CountdownEvent con annullamento</span><span class="sxs-lookup"><span data-stu-id="8f9cb-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="8f9cb-117">Nell'esempio seguente viene illustrato come annullare l'operazione di attesa in <xref:System.Threading.CountdownEvent> utilizzando un token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="8f9cb-118">Il modello di base segue il modello di annullamento unificato, che è stato introdotto in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9cb-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="8f9cb-119">Per ulteriori informazioni, vedere [annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="8f9cb-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="8f9cb-120">Si noti che l'operazione di attesa non annulla il thread di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="8f9cb-121">In genere, annullamento viene applicato a un'operazione logica e che può includere in attesa dell'evento, nonché tutti gli elementi di lavoro che sta sincronizzando il tempo di attesa.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="8f9cb-122">In questo esempio, ogni elemento di lavoro viene passato una copia del token di annullamento stesso in modo da poter rispondere alla richiesta di annullamento.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9cb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9cb-123">See Also</span></span>  
 [<span data-ttu-id="8f9cb-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="8f9cb-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
