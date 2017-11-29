---
title: Metodo ICorProfilerCallback::RemotingClientInvocationStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae91a35af0e4a0895fa58783521de1d3b95179a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="70f6f-102">Metodo ICorProfilerCallback::RemotingClientInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="70f6f-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="70f6f-103">Notifica al profiler che ha avviato una chiamata remota.</span><span class="sxs-lookup"><span data-stu-id="70f6f-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70f6f-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="70f6f-105">Note</span><span class="sxs-lookup"><span data-stu-id="70f6f-105">Remarks</span></span>  
 <span data-ttu-id="70f6f-106">Questo evento è lo stesso per le chiamate sincrone e asincrone.</span><span class="sxs-lookup"><span data-stu-id="70f6f-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="70f6f-107">Ognuna delle seguenti coppie di callback si verificherà sullo stesso thread:</span><span class="sxs-lookup"><span data-stu-id="70f6f-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="70f6f-108">`RemotingClientInvocationStarted`e [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="70f6f-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="70f6f-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="70f6f-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="70f6f-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="70f6f-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="70f6f-111">È necessario tenere presente quanto segue i callback remoti:</span><span class="sxs-lookup"><span data-stu-id="70f6f-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="70f6f-112">Esecuzione di una funzione di comunicazione remota non viene riflessa dal profiler API, in modo non vengono ricevute correttamente le notifiche per le funzioni vengono chiamate dal client ed eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="70f6f-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="70f6f-113">La chiamata effettiva avviene tramite un oggetto proxy. il profiler, perché sembra che alcune funzioni vengono compilati tramite JIT, ma mai utilizzato.</span><span class="sxs-lookup"><span data-stu-id="70f6f-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="70f6f-114">Il profiler non riceve notifiche accurate per gli eventi remoti asincroni.</span><span class="sxs-lookup"><span data-stu-id="70f6f-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f6f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70f6f-115">Requirements</span></span>  
 <span data-ttu-id="70f6f-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70f6f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f6f-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70f6f-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70f6f-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70f6f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70f6f-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f6f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f6f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70f6f-120">See Also</span></span>  
 [<span data-ttu-id="70f6f-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="70f6f-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
