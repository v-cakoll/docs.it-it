---
title: Metodo ICorProfilerCallback::RemotingClientInvocationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bec96ef50416d946b1f12fd503e04f976ca58f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662937"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="1aab0-102">Metodo ICorProfilerCallback::RemotingClientInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="1aab0-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="1aab0-103">Notifica al profiler che ha avviato una chiamata remota.</span><span class="sxs-lookup"><span data-stu-id="1aab0-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aab0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1aab0-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1aab0-105">Note</span><span class="sxs-lookup"><span data-stu-id="1aab0-105">Remarks</span></span>  
 <span data-ttu-id="1aab0-106">Questo evento è lo stesso per le chiamate sincrone e asincrone.</span><span class="sxs-lookup"><span data-stu-id="1aab0-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="1aab0-107">Ognuna delle seguenti coppie di callback si verificherà nello stesso thread:</span><span class="sxs-lookup"><span data-stu-id="1aab0-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="1aab0-108">`RemotingClientInvocationStarted` e [RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="1aab0-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="1aab0-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="1aab0-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="1aab0-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="1aab0-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="1aab0-111">È necessario considerare i seguenti problemi con i callback di .NET remoting:</span><span class="sxs-lookup"><span data-stu-id="1aab0-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="1aab0-112">Esecuzione di una funzione di .NET remoting non verrà riportata dal profiler API, in modo che le notifiche per le funzioni che vengono chiamate dal client ed eseguite nel server non vengono ricevute correttamente.</span><span class="sxs-lookup"><span data-stu-id="1aab0-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="1aab0-113">La chiamata effettiva avviene tramite un oggetto proxy. il profiler, perché sembra che alcune funzioni vengono compilati tramite JIT, ma mai utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1aab0-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="1aab0-114">Il profiler non riceve notifiche accurate per gli eventi di .NET remoting asincrono.</span><span class="sxs-lookup"><span data-stu-id="1aab0-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aab0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1aab0-115">Requirements</span></span>  
 <span data-ttu-id="1aab0-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aab0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aab0-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1aab0-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1aab0-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aab0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aab0-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aab0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aab0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aab0-120">See also</span></span>

- [<span data-ttu-id="1aab0-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1aab0-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
