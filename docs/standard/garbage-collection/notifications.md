---
title: Notifiche di Garbage Collection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: 389e851782edb82578c216951be440070b92723c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286002"
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="fbea7-102">Notifiche di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="fbea7-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="fbea7-103">In alcune situazioni un'operazione completa di Garbage Collection (cioè di generazione 2) eseguita da Common Language Runtime può influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fbea7-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="fbea7-104">Questo può costituire un problema in particolare con i server che elaborano volumi elevati di richieste. in questo caso, un Garbage Collection lungo può causare un timeout della richiesta. Per evitare che si verifichi una raccolta completa durante un periodo critico, è possibile ricevere una notifica del raggiungimento di un Garbage Collection completo e quindi eseguire un'azione per reindirizzare il carico di lavoro a un'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="fbea7-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="fbea7-105">È anche possibile indurre manualmente una raccolta, a condizione che l'istanza del server corrente non sia necessaria per elaborare le richieste.</span><span class="sxs-lookup"><span data-stu-id="fbea7-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="fbea7-106">Il metodo <xref:System.GC.RegisterForFullGCNotification%2A> registra la generazione di una notifica quando il runtime rileva che sta per essere eseguita una Garbage Collection completa.</span><span class="sxs-lookup"><span data-stu-id="fbea7-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="fbea7-107">Esistono due parti per questa notifica: quando sta per essere eseguita la Garbage Collection completa e quando la Garbage Collection completa è terminata.</span><span class="sxs-lookup"><span data-stu-id="fbea7-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="fbea7-108">Le notifiche vengono generate solo in caso di blocco delle operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fbea7-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="fbea7-109">Quando l' [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento di configurazione è abilitato, le operazioni di Garbage Collection in background non generano notifiche.</span><span class="sxs-lookup"><span data-stu-id="fbea7-109">When the [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="fbea7-110">Per determinare quando è stata generata una notifica, usare i metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbea7-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="fbea7-111">Questi metodi vengono in genere usati in un ciclo `while` per ottenere continuamente un'enumerazione <xref:System.GCNotificationStatus> che indica lo stato della notifica.</span><span class="sxs-lookup"><span data-stu-id="fbea7-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="fbea7-112">Se tale valore è <xref:System.GCNotificationStatus.Succeeded>, è possibile procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fbea7-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
- <span data-ttu-id="fbea7-113">In risposta a una notifica ottenuta con il metodo <xref:System.GC.WaitForFullGCApproach%2A>, è possibile reindirizzare il carico di lavoro e probabilmente indurre manualmente una raccolta.</span><span class="sxs-lookup"><span data-stu-id="fbea7-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
- <span data-ttu-id="fbea7-114">In risposta a una notifica ottenuta con il metodo <xref:System.GC.WaitForFullGCComplete%2A>, è possibile rendere l'istanza corrente del server disponibile per elaborare di nuovo le richieste.</span><span class="sxs-lookup"><span data-stu-id="fbea7-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="fbea7-115">È anche possibile raccogliere informazioni.</span><span class="sxs-lookup"><span data-stu-id="fbea7-115">You can also gather information.</span></span> <span data-ttu-id="fbea7-116">È ad esempio è possibile usare il metodo <xref:System.GC.CollectionCount%2A> per registrare il numero di raccolte.</span><span class="sxs-lookup"><span data-stu-id="fbea7-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="fbea7-117">I metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> sono progettati per interagire.</span><span class="sxs-lookup"><span data-stu-id="fbea7-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="fbea7-118">L'uso di uno senza l'altro può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="fbea7-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="fbea7-119">Garbage Collection completa</span><span class="sxs-lookup"><span data-stu-id="fbea7-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="fbea7-120">Il runtime genera una Garbage Collection completa quando si verifica uno degli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbea7-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
- <span data-ttu-id="fbea7-121">È stata promossa memoria sufficiente alla generazione 2 per generare la raccolta di generazione 2 successiva.</span><span class="sxs-lookup"><span data-stu-id="fbea7-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="fbea7-122">È stata promossa memoria sufficiente all'heap degli oggetti grandi per generare la raccolta di generazione 2 successiva.</span><span class="sxs-lookup"><span data-stu-id="fbea7-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="fbea7-123">Viene eseguita l'escalation di una raccolta di generazione 1 a una raccolta di generazione 2 a causa di altri fattori.</span><span class="sxs-lookup"><span data-stu-id="fbea7-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="fbea7-124">Le soglie specificate nel metodo <xref:System.GC.RegisterForFullGCNotification%2A> si applicano ai primi due scenari.</span><span class="sxs-lookup"><span data-stu-id="fbea7-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="fbea7-125">Nel primo scenario, tuttavia, non si riceverà sempre la notifica nel periodo di tempo proporzionale ai valori della soglia specificati, per due motivi:</span><span class="sxs-lookup"><span data-stu-id="fbea7-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
- <span data-ttu-id="fbea7-126">Il runtime non controlla ogni allocazione di oggetti piccoli (per motivi di prestazioni).</span><span class="sxs-lookup"><span data-stu-id="fbea7-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
- <span data-ttu-id="fbea7-127">Sole le raccolte di generazione 1 promuovono la memoria alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="fbea7-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="fbea7-128">Nel terzo scenario è incerto anche quando si riceverà la notifica.</span><span class="sxs-lookup"><span data-stu-id="fbea7-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="fbea7-129">Anche se non è una garanzia, è un modo utile per ridurre gli effetti di una Garbage Collection completa non opportuna reindirizzando le richieste durante questo intervallo di tempo o inducendo manualmente la raccolta quando può essere gestita meglio.</span><span class="sxs-lookup"><span data-stu-id="fbea7-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="fbea7-130">Parametri delle soglie di notifica</span><span class="sxs-lookup"><span data-stu-id="fbea7-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="fbea7-131">Il metodo <xref:System.GC.RegisterForFullGCNotification%2A> presenta due parametri per specificare i valori di soglia degli oggetti di generazione 2 e dell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="fbea7-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="fbea7-132">Quando tali valori sono soddisfatti, verrà generata una notifica di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fbea7-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="fbea7-133">Nella tabella seguente vengono descritti i parametri.</span><span class="sxs-lookup"><span data-stu-id="fbea7-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="fbea7-134">Parametro</span><span class="sxs-lookup"><span data-stu-id="fbea7-134">Parameter</span></span>|<span data-ttu-id="fbea7-135">Description</span><span class="sxs-lookup"><span data-stu-id="fbea7-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="fbea7-136">Numero compreso tra 1 e 99 che specifica se la notifica deve essere generata in base agli oggetti promossi alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="fbea7-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="fbea7-137">Numero compreso tra 1 e 99 che specifica quando generare la notifica in base agli oggetti allocati nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="fbea7-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="fbea7-138">Se si specifica un valore troppo elevato, è molto probabile che si riceverà una notifica, ma il tempo di attesa prima che il runtime causi una raccolta potrebbe essere troppo lungo.</span><span class="sxs-lookup"><span data-stu-id="fbea7-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="fbea7-139">Se si induce manualmente una raccolta, potrebbero essere recuperati più oggetti di quanti ne verrebbero recuperati se fosse il runtime a causare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="fbea7-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="fbea7-140">Se si specifica un valore troppo basso, il runtime potrebbe causare la raccolta prima di aver avuto tempo sufficiente per ricevere la notifica.</span><span class="sxs-lookup"><span data-stu-id="fbea7-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbea7-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbea7-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fbea7-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbea7-142">Description</span></span>  
 <span data-ttu-id="fbea7-143">Nell'esempio seguente un gruppo di server gestisce le richieste Web in ingresso.</span><span class="sxs-lookup"><span data-stu-id="fbea7-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="fbea7-144">Per simulare il carico di lavoro dell'elaborazione delle richieste, vengono aggiunte matrici di byte a una raccolta <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="fbea7-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="fbea7-145">Ogni server registra una notifica di Garbage Collection e quindi avvia un thread nel metodo utente `WaitForFullGCProc` per monitorare costantemente l'enumerazione <xref:System.GCNotificationStatus> restituita dai metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbea7-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="fbea7-146">I metodi <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> chiamano i rispettivi metodi utente di gestione eventi quando viene generata una notifica:</span><span class="sxs-lookup"><span data-stu-id="fbea7-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
- `OnFullGCApproachNotify`  
  
     <span data-ttu-id="fbea7-147">Questo metodo chiama il metodo utente `RedirectRequests`, che indica al server di accodamento delle richieste di sospendere l'invio di richieste al server.</span><span class="sxs-lookup"><span data-stu-id="fbea7-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="fbea7-148">Questa azione viene simulata impostando la variabile a livello di classe `bAllocate` su `false` in modo che non vengano allocati altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="fbea7-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="fbea7-149">Viene quindi chiamato il metodo utente `FinishExistingRequests` per completare l'elaborazione delle richieste al server in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fbea7-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="fbea7-150">Questa azione viene simulata cancellando la raccolta <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="fbea7-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="fbea7-151">Viene infine indotta una Garbage Collection perché il carico di lavoro è leggero.</span><span class="sxs-lookup"><span data-stu-id="fbea7-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
- `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="fbea7-152">Questo metodo chiama il metodo utente `AcceptRequests` per riprendere l'accettazione delle richieste perché il server non è più soggetto a una Garbage Collection completa.</span><span class="sxs-lookup"><span data-stu-id="fbea7-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="fbea7-153">Questa azione viene simulata impostando la variabile `bAllocate` su `true` in modo che sia possibile riprendere l'aggiunta degli oggetti alla raccolta <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="fbea7-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="fbea7-154">Il codice seguente contiene il metodo `Main` dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="fbea7-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="fbea7-155">Il codice seguente contiene il metodo utente `WaitForFullGCProc`, che include un ciclo while continuo per cercare le notifiche di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fbea7-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="fbea7-156">Il codice seguente contiene il metodo `OnFullGCApproachNotify` chiamato dal</span><span class="sxs-lookup"><span data-stu-id="fbea7-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="fbea7-157">Metodo`WaitForFullGCProc` .</span><span class="sxs-lookup"><span data-stu-id="fbea7-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="fbea7-158">Il codice seguente contiene il metodo `OnFullGCApproachComplete` chiamato dal</span><span class="sxs-lookup"><span data-stu-id="fbea7-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="fbea7-159">Metodo`WaitForFullGCProc` .</span><span class="sxs-lookup"><span data-stu-id="fbea7-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="fbea7-160">Il codice seguente contiene i metodi utente chiamati dai metodi `OnFullGCApproachNotify` e `OnFullGCCompleteNotify`.</span><span class="sxs-lookup"><span data-stu-id="fbea7-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="fbea7-161">I metodi utente reindirizzano le richieste, completano le richieste esistenti e quindi riprendono le richieste dopo che è stata eseguita una Garbage Collection completa.</span><span class="sxs-lookup"><span data-stu-id="fbea7-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="fbea7-162">L'esempio di codice completo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="fbea7-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbea7-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbea7-163">See also</span></span>

- [<span data-ttu-id="fbea7-164">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="fbea7-164">Garbage Collection</span></span>](index.md)
