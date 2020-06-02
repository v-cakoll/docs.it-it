---
title: Interoperabilità con altri tipi e modelli asincroni
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: fe5d8321a62b67a54dc09507e8fd86ee8d5cf74d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276556"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="f4c5e-102">Interoperabilità con altri tipi e modelli asincroni</span><span class="sxs-lookup"><span data-stu-id="f4c5e-102">Interop with Other Asynchronous Patterns and Types</span></span>
<span data-ttu-id="f4c5e-103">In .NET Framework 1.0 è stato introdotto il modello <xref:System.IAsyncResult> , altrimenti noto come [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)o modello `Begin/End` .</span><span class="sxs-lookup"><span data-stu-id="f4c5e-103">The .NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>  <span data-ttu-id="f4c5e-104">In .NET Framework 2.0 è stato aggiunto [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="f4c5e-104">The .NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  <span data-ttu-id="f4c5e-105">A partire da .NET Framework 4, [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) sostituisce sia APM che EAP, ma consente di compilare facilmente le routine di migrazione dai modelli precedenti.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-105">Starting with the .NET Framework 4, the [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) supersedes both APM and EAP, but provides the ability to easily build migration routines from the earlier patterns.</span></span>  
  
 <span data-ttu-id="f4c5e-106">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="f4c5e-106">In this topic:</span></span>  
  
- <span data-ttu-id="f4c5e-107">[Attività e APM](#APM) ([da APM a TAP](#ApmToTap) o [da TAP ad APM](#TapToApm))</span><span class="sxs-lookup"><span data-stu-id="f4c5e-107">[Tasks and APM](#APM) ([from APM to TAP](#ApmToTap) or [from TAP to APM](#TapToApm))</span></span>  
  
- [<span data-ttu-id="f4c5e-108">Attività e EAP</span><span class="sxs-lookup"><span data-stu-id="f4c5e-108">Tasks and EAP</span></span>](#EAP)  
  
- <span data-ttu-id="f4c5e-109">[Attività e handle di attesa](#WaitHandles) ([da handle di attesa a TAP](#WHToTap) o [da TAP a handle di attesa](#TapToWH))</span><span class="sxs-lookup"><span data-stu-id="f4c5e-109">[Tasks and wait handles](#WaitHandles) ([from wait handles to TAP](#WHToTap) or [from TAP to wait handles](#TapToWH))</span></span>  
  
<a name="APM"></a>
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="f4c5e-110">Attività e modelli di programmazione asincrona (APM)</span><span class="sxs-lookup"><span data-stu-id="f4c5e-110">Tasks and the Asynchronous Programming Model (APM)</span></span>  
  
<a name="ApmToTap"></a>
### <a name="from-apm-to-tap"></a><span data-ttu-id="f4c5e-111">da APM a TAP</span><span class="sxs-lookup"><span data-stu-id="f4c5e-111">From APM to TAP</span></span>  
 <span data-ttu-id="f4c5e-112">Poiché il modello [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) è molto strutturato, è piuttosto facile compilare un wrapper per esporre l'implementazione APM come implementazione di TAP.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-112">Because the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) pattern is very structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="f4c5e-113">.NET Framework, a partire da .NET Framework 4, include le routine di supporto sotto forma di overload del metodo <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> per offrire questa conversione.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-113">In fact, the .NET Framework, starting with .NET Framework 4, includes helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="f4c5e-114">Si consideri la classe <xref:System.IO.Stream> e i relativi metodi <xref:System.IO.Stream.BeginRead%2A> e <xref:System.IO.Stream.EndRead%2A> , che rappresentano l'equivalente di APM del metodo sincrono <xref:System.IO.Stream.Read%2A> :</span><span class="sxs-lookup"><span data-stu-id="f4c5e-114">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="f4c5e-115">È possibile usare il metodo <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> per implementare un wrapper di TAP per questa operazione come segue:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-115">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="f4c5e-116">Questa implementazione è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-116">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>
### <a name="from-tap-to-apm"></a><span data-ttu-id="f4c5e-117">da TAP ad APM</span><span class="sxs-lookup"><span data-stu-id="f4c5e-117">From TAP to APM</span></span>  
 <span data-ttu-id="f4c5e-118">Se l'infrastruttura esistente prevede il modello APM, sarà anche possibile creare un'implementazione di TAP e usarla dove è prevista un'implementazione APM.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-118">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="f4c5e-119">Poiché le attività possono essere composte e tramite la classe <xref:System.Threading.Tasks.Task> viene implementato l'oggetto <xref:System.IAsyncResult>, a tal fine è possibile utilizzare una semplice funzione di supporto.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-119">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="f4c5e-120">Il codice seguente usa un'estensione della classe <xref:System.Threading.Tasks.Task%601> , ma è possibile usare una funzione quasi identica per le attività non generiche.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-120">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="f4c5e-121">Ora, si consideri il caso in cui si dispone dell'implementazione di TAP:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-121">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="f4c5e-122">e si desidera fornire questa implementazione APM:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-122">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="f4c5e-123">Nell'esempio seguente viene illustrata una migrazione ad APM:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-123">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="f4c5e-124">Attività e modello asincrono basato su eventi (EAP)</span><span class="sxs-lookup"><span data-stu-id="f4c5e-124">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="f4c5e-125">Eseguire il wrapping di un'implementazione di [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) è un'operazione più complessa dell'esecuzione del wrapping di un modello APM, perché il modello EAP è più variabile e meno strutturato del modello APM.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-125">Wrapping an [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="f4c5e-126">A dimostrazione di quanto detto, il codice seguente esegue il wrapping del metodo `DownloadStringAsync` .</span><span class="sxs-lookup"><span data-stu-id="f4c5e-126">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="f4c5e-127">`DownloadStringAsync` accetta un URI, genera l'evento `DownloadProgressChanged` durante il download per comunicare diverse statistiche sullo stato di avanzamento e genera l'evento `DownloadStringCompleted` quando ha terminato.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-127">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="f4c5e-128">Il risultato finale è una stringa che contiene il contenuto della pagina all'URI specificato.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-128">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="f4c5e-129">Attività e handle di attesa</span><span class="sxs-lookup"><span data-stu-id="f4c5e-129">Tasks and Wait Handles</span></span>  
  
<a name="WHToTap"></a>
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="f4c5e-130">da handle di attesa a TAP</span><span class="sxs-lookup"><span data-stu-id="f4c5e-130">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="f4c5e-131">Sebbene gli handle di attesa non implementino un modello asincrono, gli sviluppatori avanzati possono usare la classe <xref:System.Threading.WaitHandle> e il metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> per le notifiche asincrone quando è impostato un handle di attesa.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-131">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="f4c5e-132">È possibile eseguire il wrapping del metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> per abilitare un'alternativa basata su attività a qualsiasi attesa sincrona su un handle di attesa:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-132">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="f4c5e-133">Con questo metodo, è possibile usare le implementazioni di <xref:System.Threading.WaitHandle> esistenti nei metodi asincroni.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-133">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="f4c5e-134">Se, ad esempio, si vuole limitare il numero di operazioni asincrone in esecuzione in un momento specifico, è possibile usare un semaforo (oggetto <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f4c5e-134">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="f4c5e-135">È possibile limitare a *N* il numero di operazioni eseguite contemporaneamente inizializzando il conteggio del semaforo a *N*, rimanendo in attesa del semaforo ogni volta che si desidera eseguire un'operazione e rilasciando il semaforo quando l'operazione è terminata:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-135">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore’s count to *N*, waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you’re done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="f4c5e-136">È anche possibile creare un semaforo asincrono che non si basa sugli handle di attesa ma interagisce completamente con le attività.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-136">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="f4c5e-137">A questo scopo, è possibile usare tecniche quali quelle descritte in [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) per basare le strutture dei dati su <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="f4c5e-137">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
<a name="TapToWH"></a>
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="f4c5e-138">da TAP a handle di attesa</span><span class="sxs-lookup"><span data-stu-id="f4c5e-138">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="f4c5e-139">Come accennato in precedenza, la classe <xref:System.Threading.Tasks.Task> implementa <xref:System.IAsyncResult>e tale implementazione espone una proprietà <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> che restituisce un handle di attesa che verrà impostato al completamento di <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="f4c5e-139">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="f4c5e-140">È possibile ottenere un <xref:System.Threading.WaitHandle> per <xref:System.Threading.Tasks.Task> come segue:</span><span class="sxs-lookup"><span data-stu-id="f4c5e-140">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="f4c5e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4c5e-141">See also</span></span>

- [<span data-ttu-id="f4c5e-142">Modello asincrono basato su attività (TAP)</span><span class="sxs-lookup"><span data-stu-id="f4c5e-142">Task-based Asynchronous Pattern (TAP)</span></span>](task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="f4c5e-143">Implementazione del modello asincrono basato su attività</span><span class="sxs-lookup"><span data-stu-id="f4c5e-143">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="f4c5e-144">Consuming the Task-based Asynchronous Pattern</span><span class="sxs-lookup"><span data-stu-id="f4c5e-144">Consuming the Task-based Asynchronous Pattern</span></span>](consuming-the-task-based-asynchronous-pattern.md)
