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
ms.openlocfilehash: 90ddb30c3d27d5f431c355abd3a6f792564e616d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866044"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="2b84a-102">Metodo ICorProfilerCallback::RemotingClientInvocationFinished</span><span class="sxs-lookup"><span data-stu-id="2b84a-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="2b84a-103">Notifica al profiler che una chiamata remota è stata eseguita fino al completamento nel client.</span><span class="sxs-lookup"><span data-stu-id="2b84a-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b84a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b84a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2b84a-105">Note</span><span class="sxs-lookup"><span data-stu-id="2b84a-105">Remarks</span></span>  
 <span data-ttu-id="2b84a-106">Se la chiamata remota è sincrona, viene eseguita anche fino al completamento sul server.</span><span class="sxs-lookup"><span data-stu-id="2b84a-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="2b84a-107">Se la chiamata remota era asincrona, una risposta potrebbe essere ancora prevista quando viene gestita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2b84a-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="2b84a-108">Se è prevista una risposta, si verificherà come chiamata a [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) e a una chiamata aggiuntiva a `RemotingClientInvocationFinished` per indicare l'elaborazione secondaria richiesta di una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="2b84a-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="2b84a-109">Ognuna delle coppie di callback seguenti si verificherà nello stesso thread:</span><span class="sxs-lookup"><span data-stu-id="2b84a-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="2b84a-110">`RemotingClientInvocationStarted` e [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="2b84a-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="2b84a-111">Metodo [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="2b84a-111">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="2b84a-112">Metodo [ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="2b84a-112">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="2b84a-113">È necessario tenere presenti i seguenti problemi con i callback di comunicazione remota:</span><span class="sxs-lookup"><span data-stu-id="2b84a-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="2b84a-114">L'esecuzione di una funzione di comunicazione remota non viene riflessa dall'API del profiler, quindi le notifiche per le funzioni chiamate dal client ed eseguite sul server non vengono ricevute correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b84a-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="2b84a-115">La chiamata effettiva avviene tramite un oggetto proxy. il profiler sembra che alcune funzioni siano compilate tramite JIT ma mai usate.</span><span class="sxs-lookup"><span data-stu-id="2b84a-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="2b84a-116">Il profiler non riceve notifiche accurate per gli eventi di comunicazione remota asincrona.</span><span class="sxs-lookup"><span data-stu-id="2b84a-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b84a-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2b84a-117">Requirements</span></span>  
 <span data-ttu-id="2b84a-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b84a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b84a-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2b84a-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2b84a-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b84a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b84a-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b84a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b84a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b84a-122">See also</span></span>

- [<span data-ttu-id="2b84a-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2b84a-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
