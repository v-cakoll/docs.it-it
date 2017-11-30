---
title: Notifiche di Garbage Collection
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
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="bbe65-102">Notifiche di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="bbe65-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="bbe65-103">In alcune situazioni un'operazione completa di Garbage Collection (cioè di generazione 2) eseguita da Common Language Runtime può influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bbe65-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="bbe65-104">Può trattarsi di un problema particolarmente con server che elaborano grandi volumi di richieste. In questo caso, una lunga procedura di garbage collection può provocare un timeout della richiesta. Per evitare un insieme completo che si verifichino durante un periodo critico, si può ricevere notifiche di garbage collection completa sta per raggiungere e intraprendere azioni per reindirizzare il carico di lavoro a un'altra istanza del server.</span><span class="sxs-lookup"><span data-stu-id="bbe65-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="bbe65-105">È possibile anche forzare una raccolta, condizione che l'istanza del server corrente non è necessario elaborare le richieste.</span><span class="sxs-lookup"><span data-stu-id="bbe65-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="bbe65-106">Il <xref:System.GC.RegisterForFullGCNotification%2A> metodo registra la notifica quando il runtime rileva che sta per una garbage collection completa.</span><span class="sxs-lookup"><span data-stu-id="bbe65-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="bbe65-107">Esistono due parti per questa notifica: quando sta per raggiungere la garbage collection completa e quando è stata completata la garbage collection completa.</span><span class="sxs-lookup"><span data-stu-id="bbe65-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bbe65-108">Le notifiche vengono generate solo in caso di blocco delle operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bbe65-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="bbe65-109">Quando il [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento di configurazione è abilitata, le Garbage Collection in background non saranno generate notifiche.</span><span class="sxs-lookup"><span data-stu-id="bbe65-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="bbe65-110">Per determinare quando è stata generata una notifica, utilizzare il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="bbe65-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="bbe65-111">In genere, usare questi metodi in un `while` ciclo per ottenere continuamente una <xref:System.GCNotificationStatus> enumerazione che indica lo stato della notifica.</span><span class="sxs-lookup"><span data-stu-id="bbe65-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="bbe65-112">Se il valore è <xref:System.GCNotificationStatus.Succeeded>, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbe65-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="bbe65-113">In risposta a una notifica ottenuta con la <xref:System.GC.WaitForFullGCApproach%2A> (metodo), è possibile reindirizzare il carico di lavoro e possibilmente forzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="bbe65-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="bbe65-114">In risposta a una notifica ottenuta con la <xref:System.GC.WaitForFullGCComplete%2A> (metodo), è possibile rendere l'istanza corrente di server disponibile per elaborare le richieste nuovamente.</span><span class="sxs-lookup"><span data-stu-id="bbe65-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="bbe65-115">È anche possibile raccogliere informazioni.</span><span class="sxs-lookup"><span data-stu-id="bbe65-115">You can also gather information.</span></span> <span data-ttu-id="bbe65-116">Ad esempio, è possibile utilizzare il <xref:System.GC.CollectionCount%2A> metodo per registrare il numero di raccolte.</span><span class="sxs-lookup"><span data-stu-id="bbe65-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="bbe65-117">Il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi sono progettati per funzionare insieme.</span><span class="sxs-lookup"><span data-stu-id="bbe65-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="bbe65-118">Utilizzo di uno senza l'altro può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="bbe65-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="bbe65-119">Garbage Collection completa</span><span class="sxs-lookup"><span data-stu-id="bbe65-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="bbe65-120">Il runtime genera un'operazione completa di garbage collection quando uno degli scenari seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="bbe65-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="bbe65-121">Memoria insufficiente sia stato promosso alla generazione 2 per generare la raccolta di generazione 2 successiva.</span><span class="sxs-lookup"><span data-stu-id="bbe65-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="bbe65-122">Memoria insufficiente è stato promosso nell'heap oggetti grandi per generare la raccolta di generazione 2 successiva.</span><span class="sxs-lookup"><span data-stu-id="bbe65-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="bbe65-123">Una raccolta di generazione 1 viene riassegnata a una raccolta di generazione 2 a causa di altri fattori.</span><span class="sxs-lookup"><span data-stu-id="bbe65-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="bbe65-124">Le soglie specificate nel <xref:System.GC.RegisterForFullGCNotification%2A> metodo riguardano i primi due scenari.</span><span class="sxs-lookup"><span data-stu-id="bbe65-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="bbe65-125">Tuttavia, nel primo scenario è non sempre riceveranno la notifica al momento proporzionale per i valori di soglia specificati per due motivi:</span><span class="sxs-lookup"><span data-stu-id="bbe65-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="bbe65-126">Il runtime non controlla ogni allocazione di oggetti piccoli (per motivi di prestazioni).</span><span class="sxs-lookup"><span data-stu-id="bbe65-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="bbe65-127">Generazione 1 raccolte innalzare di livello solo memoria alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="bbe65-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="bbe65-128">Il terzo scenario contribuisce inoltre all'incertezza di quando si riceveranno la notifica.</span><span class="sxs-lookup"><span data-stu-id="bbe65-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="bbe65-129">Anche se non si tratta di una garanzia, esso si riveli utile per ridurre gli effetti di un inopportuna completa di garbage collection da reindirizzare le richieste durante questo periodo o forzando la raccolta quando possono essere gestita meglio.</span><span class="sxs-lookup"><span data-stu-id="bbe65-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="bbe65-130">Parametri della soglia di notifica</span><span class="sxs-lookup"><span data-stu-id="bbe65-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="bbe65-131">Il <xref:System.GC.RegisterForFullGCNotification%2A> metodo presenta due parametri per specificare i valori soglia degli oggetti di generazione 2 e l'heap oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="bbe65-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="bbe65-132">Quando vengono soddisfatti questi valori, dovrebbe essere generata una notifica di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="bbe65-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="bbe65-133">Nella tabella seguente vengono descritti questi parametri.</span><span class="sxs-lookup"><span data-stu-id="bbe65-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="bbe65-134">Parametro</span><span class="sxs-lookup"><span data-stu-id="bbe65-134">Parameter</span></span>|<span data-ttu-id="bbe65-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbe65-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="bbe65-136">Un numero compreso tra 1 e 99 che specifica se la notifica deve essere generata basato sugli oggetti alzate di livello nella generazione 2.</span><span class="sxs-lookup"><span data-stu-id="bbe65-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="bbe65-137">Un numero compreso tra 1 e 99 che specifica se la notifica deve essere generata basato sugli oggetti allocati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="bbe65-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="bbe65-138">Se si specifica un valore troppo elevato, è presente un elevato livello di probabilità che si riceverà una notifica, ma potrebbe essere troppo lungo un periodo di attesa prima che il runtime determina un insieme.</span><span class="sxs-lookup"><span data-stu-id="bbe65-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="bbe65-139">Se si forzare una raccolta, si potrebbero richiedere più oggetti verrebbero recuperati se il runtime determina la raccolta.</span><span class="sxs-lookup"><span data-stu-id="bbe65-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="bbe65-140">Se si specifica un valore troppo basso, il runtime può provocare la raccolta prima che sia trascorso sufficiente tempo per ricevere una notifica.</span><span class="sxs-lookup"><span data-stu-id="bbe65-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe65-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbe65-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bbe65-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbe65-142">Description</span></span>  
 <span data-ttu-id="bbe65-143">Nell'esempio seguente, un gruppo di server richieste Web in ingresso.</span><span class="sxs-lookup"><span data-stu-id="bbe65-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="bbe65-144">Per simulare il carico di lavoro dell'elaborazione delle richieste, le matrici di byte vengono aggiunti a un <xref:System.Collections.Generic.List%601> insieme.</span><span class="sxs-lookup"><span data-stu-id="bbe65-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="bbe65-145">Ogni server registrato per notifica di un'operazione di garbage collection e quindi avvia un thread nel `WaitForFullGCProc` metodo utente per monitorare costantemente il <xref:System.GCNotificationStatus> enumerazione restituito dal <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="bbe65-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="bbe65-146">Il <xref:System.GC.WaitForFullGCApproach%2A> e <xref:System.GC.WaitForFullGCComplete%2A> metodi chiamano i rispettivi metodi utente di gestione degli eventi quando viene generata una notifica:</span><span class="sxs-lookup"><span data-stu-id="bbe65-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="bbe65-147">Questo metodo chiama il `RedirectRequests` metodo utente, che indica al server di Accodamento messaggi di richiesta di sospendere l'invio di richieste al server.</span><span class="sxs-lookup"><span data-stu-id="bbe65-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="bbe65-148">Questa situazione viene simulata impostando la variabile a livello di classe `bAllocate` a `false` in modo che non vengano più allocati oggetti.</span><span class="sxs-lookup"><span data-stu-id="bbe65-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="bbe65-149">Successivamente, il `FinishExistingRequests` utente viene chiamato per completare l'elaborazione delle richieste in sospeso al server.</span><span class="sxs-lookup"><span data-stu-id="bbe65-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="bbe65-150">Questa situazione viene simulata cancellando la <xref:System.Collections.Generic.List%601> insieme.</span><span class="sxs-lookup"><span data-stu-id="bbe65-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="bbe65-151">Infine, una garbage collection è causata perché il carico di lavoro è chiaro.</span><span class="sxs-lookup"><span data-stu-id="bbe65-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="bbe65-152">Questo metodo chiama il metodo dell'utente `AcceptRequests` per riprendere l'accettazione di richieste perché il server non è più soggetto a garbage collection completa.</span><span class="sxs-lookup"><span data-stu-id="bbe65-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="bbe65-153">Questa azione viene simulata impostando il `bAllocate` variabile `true` in modo che gli oggetti possono riprendere l'aggiunta di <xref:System.Collections.Generic.List%601> insieme.</span><span class="sxs-lookup"><span data-stu-id="bbe65-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="bbe65-154">Il codice seguente contiene il `Main` metodo dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="bbe65-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="bbe65-155">Il codice seguente contiene il `WaitForFullGCProc` metodo utente, che contiene un ciclo while continuo per le notifiche di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="bbe65-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="bbe65-156">Il codice seguente contiene il `OnFullGCApproachNotify` metodo chiamato dal</span><span class="sxs-lookup"><span data-stu-id="bbe65-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="bbe65-157">Metodo `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="bbe65-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="bbe65-158">Il codice seguente contiene il `OnFullGCApproachComplete` metodo chiamato dal</span><span class="sxs-lookup"><span data-stu-id="bbe65-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="bbe65-159">Metodo `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="bbe65-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="bbe65-160">Il codice seguente contiene i metodi di utente che vengono chiamati dal `OnFullGCApproachNotify` e `OnFullGCCompleteNotify` metodi.</span><span class="sxs-lookup"><span data-stu-id="bbe65-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="bbe65-161">I metodi utente reindirizzano le richieste, completano le richieste esistenti e quindi riprendono le richieste dopo un'operazione completa di garbage collection si è verificato.</span><span class="sxs-lookup"><span data-stu-id="bbe65-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="bbe65-162">L'esempio di codice completo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="bbe65-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bbe65-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe65-163">See Also</span></span>  
 [<span data-ttu-id="bbe65-164">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="bbe65-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
