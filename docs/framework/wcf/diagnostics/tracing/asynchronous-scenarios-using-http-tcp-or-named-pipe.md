---
title: Scenari asincroni con trasporti HTTP, TCP o pipe con nome
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76c4c225b333af6d376fa409a05ea5727ede6e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="067f1-102">Scenari asincroni con trasporti HTTP, TCP o pipe con nome</span><span class="sxs-lookup"><span data-stu-id="067f1-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="067f1-103">In questo argomento vengono descritti attività e trasferimenti per vari scenari Request/Reply asincroni, con richieste multithreading che utilizzano HTTP, TCP o named pipe.</span><span class="sxs-lookup"><span data-stu-id="067f1-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="067f1-104">Request/Reply asincroni senza errori</span><span class="sxs-lookup"><span data-stu-id="067f1-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="067f1-105">Contenuto della sezione vengono descritti attività e trasferimenti per uno scenario Request/Reply asincrono, con client multithreading.</span><span class="sxs-lookup"><span data-stu-id="067f1-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="067f1-106">L'attività del chiamante termina quando viene restituito `beginCall` e viene restituito `endCall`.</span><span class="sxs-lookup"><span data-stu-id="067f1-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="067f1-107">Se viene chiamato un callback, viene restituito il callback.</span><span class="sxs-lookup"><span data-stu-id="067f1-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="067f1-108">L'attività chiamata termina quando viene restituito `beginCall`, viene restituito `endCall` o quando viene restituito il callback, se chiamato da tale attività.</span><span class="sxs-lookup"><span data-stu-id="067f1-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="067f1-109">Client asincrono senza callback</span><span class="sxs-lookup"><span data-stu-id="067f1-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="067f1-110">La propagazione è attivata su entrambi i lati, con l'utilizzo di HTTP</span><span class="sxs-lookup"><span data-stu-id="067f1-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 <span data-ttu-id="067f1-111">![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span><span class="sxs-lookup"><span data-stu-id="067f1-111">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span></span>  
  
 <span data-ttu-id="067f1-112">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="067f1-112">Figure 1.</span></span> <span data-ttu-id="067f1-113">Client asincrono, senza callback, `propagateActivity` = `true` su entrambi i lati, HTTP</span><span class="sxs-lookup"><span data-stu-id="067f1-113">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, HTTP</span></span>  
  
 <span data-ttu-id="067f1-114">Se `propagateActivity` = `true`, ProcessMessage indica l'attività ProcessAction da trasferire.</span><span class="sxs-lookup"><span data-stu-id="067f1-114">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="067f1-115">Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.</span><span class="sxs-lookup"><span data-stu-id="067f1-115">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="067f1-116">La propagazione è disattivata su uno dei due lati, con l'utilizzo di HTTP</span><span class="sxs-lookup"><span data-stu-id="067f1-116">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="067f1-117">Se `propagateActivity` = `false` su un lato, ProcessMessage non indica l'attività ProcessAction da trasferire.</span><span class="sxs-lookup"><span data-stu-id="067f1-117">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="067f1-118">Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID.</span><span class="sxs-lookup"><span data-stu-id="067f1-118">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="067f1-119">Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale.</span><span class="sxs-lookup"><span data-stu-id="067f1-119">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="067f1-120">L'effettiva attività ProcessAction può essere trasferita con tale ID.</span><span class="sxs-lookup"><span data-stu-id="067f1-120">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="067f1-121">![Scenari asincroni con HTTP &#47; TCP &#47; Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span><span class="sxs-lookup"><span data-stu-id="067f1-121">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span></span>  
  
 <span data-ttu-id="067f1-122">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="067f1-122">Figure 2.</span></span> <span data-ttu-id="067f1-123">Client asincrono, senza callback, `propagateActivity` = `false` su entrambi i lati, HTTP</span><span class="sxs-lookup"><span data-stu-id="067f1-123">Asynchronous client, no callback, `propagateActivity`=`false` on either side, HTTP</span></span>  
  
 <span data-ttu-id="067f1-124">Per gli scenari basati su HTTP, ReceiveBytes viene richiamato nel primo messaggio da inviare ed esiste per la durata della richiesta.</span><span class="sxs-lookup"><span data-stu-id="067f1-124">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="067f1-125">Un'attività elaborazione azione viene creata in un client asincrono quando `propagateActivity` = `false` nel chiamante o chiamato e quando il messaggio di risposta non include un'intestazione Action.</span><span class="sxs-lookup"><span data-stu-id="067f1-125">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="067f1-126">La propagazione è attivata su entrambi i lati, con l'utilizzo di TCP o named pipe</span><span class="sxs-lookup"><span data-stu-id="067f1-126">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="067f1-127">![Scenari asincroni con HTTP &#47; TCP &#47; Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span><span class="sxs-lookup"><span data-stu-id="067f1-127">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span></span>  
  
 <span data-ttu-id="067f1-128">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="067f1-128">Figure 3.</span></span> <span data-ttu-id="067f1-129">Client asincrono, senza callback, `propagateActivity` = `true` su entrambi i lati, Named Pipe/TCP</span><span class="sxs-lookup"><span data-stu-id="067f1-129">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, Named-Pipe/TCP</span></span>  
  
 <span data-ttu-id="067f1-130">Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.</span><span class="sxs-lookup"><span data-stu-id="067f1-130">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="067f1-131">Come nella figura 1, se `propagateActivity` = `true`, ProcessMessage indica l'attività ProcessAction da trasferire.</span><span class="sxs-lookup"><span data-stu-id="067f1-131">Similar to Figure 1, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="067f1-132">La propagazione è disattivata su uno dei due lati, con l'utilizzo di TCP o named pipe</span><span class="sxs-lookup"><span data-stu-id="067f1-132">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="067f1-133">Per uno scenario basato su named pipe o TCP, ReceiveBytes viene richiamato quando il client è aperto ed esiste per la durata della connessione.</span><span class="sxs-lookup"><span data-stu-id="067f1-133">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="067f1-134">Come nella figura 2, se `propagateActivity` = `false` su un lato, ProcessMessage non indica l'attività ProcessAction da trasferire.</span><span class="sxs-lookup"><span data-stu-id="067f1-134">Similar to Fig.2, If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="067f1-135">Pertanto, viene richiamata una nuova attività ProcessAction temporanea con un nuovo ID.</span><span class="sxs-lookup"><span data-stu-id="067f1-135">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="067f1-136">Quando la risposta asincrona viene abbinata alla richiesta nel codice di ServiceModel, l'ID attività può essere recuperato dal contesto locale.</span><span class="sxs-lookup"><span data-stu-id="067f1-136">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="067f1-137">L'effettiva attività ProcessAction può essere trasferita con tale ID.</span><span class="sxs-lookup"><span data-stu-id="067f1-137">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="067f1-138">![Scenari asincroni con HTTP &#47; TCP &#47; Named pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span><span class="sxs-lookup"><span data-stu-id="067f1-138">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span></span>  
  
 <span data-ttu-id="067f1-139">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="067f1-139">Figure 4.</span></span> <span data-ttu-id="067f1-140">Client asincrono, senza callback, `propagateActivity` = `false` su entrambi i lati, Named Pipe/TCP</span><span class="sxs-lookup"><span data-stu-id="067f1-140">Asynchronous client, no callback, `propagateActivity`=`false` on either side, Named-Pipe/TCP</span></span>  
  
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="067f1-141">Client asincrono con callback</span><span class="sxs-lookup"><span data-stu-id="067f1-141">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="067f1-142">Questo scenario aggiunge attività G e A', per il callback e `endCall`, e i rispettivi trasferimenti dentro/fuori.</span><span class="sxs-lookup"><span data-stu-id="067f1-142">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="067f1-143">Questa sezione viene illustrata solo l'utilizzo di HTTP con `propragateActivity` = `true`.</span><span class="sxs-lookup"><span data-stu-id="067f1-143">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="067f1-144">Tuttavia, l'attività e trasferimenti aggiuntivi si applicano anche agli altri casi (ovvero, `propagateActivity` = `false`, utilizzando TCP o Named Pipe).</span><span class="sxs-lookup"><span data-stu-id="067f1-144">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="067f1-145">Il callback crea un'attività nuova (G) quando il client chiama codice utente per notificare che i risultati sono pronti.</span><span class="sxs-lookup"><span data-stu-id="067f1-145">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="067f1-146">Il codice utente chiama quindi `endCall` all'interno del callback (come mostrato in Figura 5) o fuori del callback (Figura 6).</span><span class="sxs-lookup"><span data-stu-id="067f1-146">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="067f1-147">Poiché non è noto quale attività utente `endCall` viene chiamata da questa attività viene etichettata `A’`.</span><span class="sxs-lookup"><span data-stu-id="067f1-147">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="067f1-148">È possibile che A' sia identico ad A o diverso.</span><span class="sxs-lookup"><span data-stu-id="067f1-148">It is possible that A’ can be identical to or different from A.</span></span>  
  
 <span data-ttu-id="067f1-149">![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span><span class="sxs-lookup"><span data-stu-id="067f1-149">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span></span>  
  
 <span data-ttu-id="067f1-150">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="067f1-150">Figure 5.</span></span> <span data-ttu-id="067f1-151">Client asincrono con callback, `endCall` all'interno del callback</span><span class="sxs-lookup"><span data-stu-id="067f1-151">Asynchronous client with callback, `endCall` in Callback</span></span>  
  
 <span data-ttu-id="067f1-152">![Scenari asincroni](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span><span class="sxs-lookup"><span data-stu-id="067f1-152">![Asynchronous Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span></span>  
  
 <span data-ttu-id="067f1-153">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="067f1-153">Figure 6.</span></span> <span data-ttu-id="067f1-154">Client asincrono con callback, `endCall` esternamente al callback</span><span class="sxs-lookup"><span data-stu-id="067f1-154">Asynchronous client with callback, `endCall` outside of Callback</span></span>  
  
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="067f1-155">Server asincrono con callback</span><span class="sxs-lookup"><span data-stu-id="067f1-155">Asynchronous Server with Callback</span></span>  
 <span data-ttu-id="067f1-156">![Scenari asincroni con HTTP &#47; TCP &#47; Nome &#45; Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span><span class="sxs-lookup"><span data-stu-id="067f1-156">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span></span>  
  
 <span data-ttu-id="067f1-157">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="067f1-157">Figure 7.</span></span> <span data-ttu-id="067f1-158">Server asincrono con callback</span><span class="sxs-lookup"><span data-stu-id="067f1-158">Asynchronous server, with callback</span></span>  
  
 <span data-ttu-id="067f1-159">Le stack dei canali richiama il client in Messaggio Ricevere: le tracce di questa elaborazione vengono create nell'attività ProcessRequest stessa.</span><span class="sxs-lookup"><span data-stu-id="067f1-159">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="067f1-160">Request/Reply asincroni con errori</span><span class="sxs-lookup"><span data-stu-id="067f1-160">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="067f1-161">I messaggi di errore vengono ricevuti durante `endCall`.</span><span class="sxs-lookup"><span data-stu-id="067f1-161">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="067f1-162">In caso contrario, attività e trasferimenti sono simili agli scenari precedenti.</span><span class="sxs-lookup"><span data-stu-id="067f1-162">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="067f1-163">Unidirezionale asincrono con o senza errori</span><span class="sxs-lookup"><span data-stu-id="067f1-163">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="067f1-164">Al client non vengono restituite risposte né errori.</span><span class="sxs-lookup"><span data-stu-id="067f1-164">No response or fault is returned to the client.</span></span>
