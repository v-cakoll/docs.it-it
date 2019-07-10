---
title: Metodo ICorProfilerCallback::RemotingClientInvocationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8c29393f3127ec02d343221f28152fffbadb2b7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782939"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="db55e-102">Metodo ICorProfilerCallback::RemotingClientInvocationFinished</span><span class="sxs-lookup"><span data-stu-id="db55e-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="db55e-103">Notifica al profiler che una chiamata remota completamento dell'esecuzione nel client.</span><span class="sxs-lookup"><span data-stu-id="db55e-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db55e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db55e-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="db55e-105">Note</span><span class="sxs-lookup"><span data-stu-id="db55e-105">Remarks</span></span>  
 <span data-ttu-id="db55e-106">Se la chiamata ai servizi remoti è sincrona, è inoltre eseguito fino al completamento nel server.</span><span class="sxs-lookup"><span data-stu-id="db55e-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="db55e-107">Se la chiamata remota è asincrona, una risposta ancora prevedibile quando la chiamata è stata gestita.</span><span class="sxs-lookup"><span data-stu-id="db55e-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="db55e-108">Se si prevede una risposta, che verrà eseguito come una chiamata a [RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e una chiamata aggiuntiva al `RemotingClientInvocationFinished` per indicare l'elaborazione necessaria secondario di una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="db55e-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="db55e-109">Ognuna delle seguenti coppie di callback si verificherà nello stesso thread:</span><span class="sxs-lookup"><span data-stu-id="db55e-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="db55e-110">`RemotingClientInvocationStarted` e [RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="db55e-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="db55e-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="db55e-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="db55e-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="db55e-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="db55e-113">È necessario considerare i seguenti problemi con i callback di .NET remoting:</span><span class="sxs-lookup"><span data-stu-id="db55e-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="db55e-114">Esecuzione di una funzione di .NET remoting non verrà riportata dal profiler API, in modo che le notifiche per le funzioni che vengono chiamate dal client ed eseguite nel server non vengono ricevute correttamente.</span><span class="sxs-lookup"><span data-stu-id="db55e-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="db55e-115">La chiamata effettiva avviene tramite un oggetto proxy. il profiler, perché sembra che alcune funzioni vengono compilati tramite JIT, ma mai utilizzato.</span><span class="sxs-lookup"><span data-stu-id="db55e-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="db55e-116">Il profiler non riceve notifiche accurate per gli eventi di .NET remoting asincrono.</span><span class="sxs-lookup"><span data-stu-id="db55e-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db55e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db55e-117">Requirements</span></span>  
 <span data-ttu-id="db55e-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db55e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db55e-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db55e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db55e-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db55e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db55e-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db55e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db55e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db55e-122">See also</span></span>

- [<span data-ttu-id="db55e-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="db55e-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
