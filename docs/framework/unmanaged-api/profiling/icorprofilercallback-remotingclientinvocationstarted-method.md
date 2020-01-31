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
ms.openlocfilehash: 93bd1010374413f3f4ef7e1424ff8194dded8bb3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866050"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="cfcaa-102">Metodo ICorProfilerCallback::RemotingClientInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="cfcaa-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="cfcaa-103">Notifica al profiler che è stata avviata una chiamata remota.</span><span class="sxs-lookup"><span data-stu-id="cfcaa-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcaa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfcaa-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cfcaa-105">Note</span><span class="sxs-lookup"><span data-stu-id="cfcaa-105">Remarks</span></span>  
 <span data-ttu-id="cfcaa-106">Questo evento è lo stesso per le chiamate sincrone e asincrone.</span><span class="sxs-lookup"><span data-stu-id="cfcaa-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="cfcaa-107">Ognuna delle coppie di callback seguenti si verificherà nello stesso thread:</span><span class="sxs-lookup"><span data-stu-id="cfcaa-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="cfcaa-108">`RemotingClientInvocationStarted` e [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfcaa-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="cfcaa-109">Metodo [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfcaa-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="cfcaa-110">Metodo [ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="cfcaa-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="cfcaa-111">È necessario tenere presenti i seguenti problemi con i callback di comunicazione remota:</span><span class="sxs-lookup"><span data-stu-id="cfcaa-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="cfcaa-112">L'esecuzione di una funzione di comunicazione remota non viene riflessa dall'API del profiler, quindi le notifiche per le funzioni chiamate dal client ed eseguite sul server non vengono ricevute correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfcaa-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="cfcaa-113">La chiamata effettiva avviene tramite un oggetto proxy. il profiler sembra che alcune funzioni siano compilate tramite JIT ma mai usate.</span><span class="sxs-lookup"><span data-stu-id="cfcaa-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="cfcaa-114">Il profiler non riceve notifiche accurate per gli eventi di comunicazione remota asincrona.</span><span class="sxs-lookup"><span data-stu-id="cfcaa-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfcaa-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cfcaa-115">Requirements</span></span>  
 <span data-ttu-id="cfcaa-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfcaa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfcaa-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfcaa-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cfcaa-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfcaa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfcaa-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcaa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcaa-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfcaa-120">See also</span></span>

- [<span data-ttu-id="cfcaa-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cfcaa-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
