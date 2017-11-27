---
title: Metodo ICorProfilerCallback::RemotingClientInvocationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77f86d12d3a19f1b02ece35c8b717e78802f74f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="e1fde-102">Metodo ICorProfilerCallback::RemotingClientInvocationFinished</span><span class="sxs-lookup"><span data-stu-id="e1fde-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="e1fde-103">Notifica al profiler che una chiamata remota completamento dell'esecuzione nel client.</span><span class="sxs-lookup"><span data-stu-id="e1fde-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1fde-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e1fde-105">Note</span><span class="sxs-lookup"><span data-stu-id="e1fde-105">Remarks</span></span>  
 <span data-ttu-id="e1fde-106">Se la chiamata remota era sincrona, è inoltre eseguito fino al completamento nel server.</span><span class="sxs-lookup"><span data-stu-id="e1fde-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="e1fde-107">Se la chiamata remota è asincrona, potrebbe essere prevede una risposta comunque quando la chiamata è stata gestita.</span><span class="sxs-lookup"><span data-stu-id="e1fde-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="e1fde-108">Se si prevede una risposta, si verificherà come una chiamata a [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e una chiamata aggiuntiva al `RemotingClientInvocationFinished` per indicare l'elaborazione necessaria secondario di una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="e1fde-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="e1fde-109">Ognuna delle seguenti coppie di callback si verificherà sullo stesso thread:</span><span class="sxs-lookup"><span data-stu-id="e1fde-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="e1fde-110">`RemotingClientInvocationStarted`e [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="e1fde-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="e1fde-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="e1fde-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="e1fde-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="e1fde-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="e1fde-113">È necessario tenere presente quanto segue i callback remoti:</span><span class="sxs-lookup"><span data-stu-id="e1fde-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="e1fde-114">Esecuzione di una funzione di comunicazione remota non viene riflessa dal profiler API, in modo non vengono ricevute correttamente le notifiche per le funzioni vengono chiamate dal client ed eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="e1fde-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="e1fde-115">La chiamata effettiva avviene tramite un oggetto proxy. il profiler, perché sembra che alcune funzioni vengono compilati tramite JIT, ma mai utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e1fde-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="e1fde-116">Il profiler non riceve notifiche accurate per gli eventi remoti asincroni.</span><span class="sxs-lookup"><span data-stu-id="e1fde-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fde-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1fde-117">Requirements</span></span>  
 <span data-ttu-id="e1fde-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1fde-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fde-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1fde-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1fde-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1fde-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1fde-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1fde-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fde-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1fde-122">See Also</span></span>  
 [<span data-ttu-id="e1fde-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e1fde-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
