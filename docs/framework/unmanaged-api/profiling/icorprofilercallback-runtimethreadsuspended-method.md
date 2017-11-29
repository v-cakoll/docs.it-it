---
title: Metodo ICorProfilerCallback::RuntimeThreadSuspended
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadSuspended
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d2ab0244e898a60db8fe392ccbd8c0ebfd5523
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="b1d09-102">Metodo ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="b1d09-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="b1d09-103">Notifica al profiler che il thread specificato è stato sospeso o sta per essere sospesa.</span><span class="sxs-lookup"><span data-stu-id="b1d09-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1d09-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1d09-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1d09-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1d09-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b1d09-106">[in] L'ID del thread che è stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="b1d09-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1d09-107">Note</span><span class="sxs-lookup"><span data-stu-id="b1d09-107">Remarks</span></span>  
 <span data-ttu-id="b1d09-108">Il `RuntimeThreadSuspended` notifica può verificarsi in qualsiasi momento compreso tra il [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) associati [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="b1d09-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="b1d09-109">Le notifiche che si verificano tra [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e `RuntimeResumeStarted` per i thread che erano in esecuzione nel codice non gestito e sono stati sospesi al momento dell'accesso al runtime.</span><span class="sxs-lookup"><span data-stu-id="b1d09-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="b1d09-110">In genere, questo callback si verifica subito dopo un thread è sospeso.</span><span class="sxs-lookup"><span data-stu-id="b1d09-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="b1d09-111">Tuttavia, se il thread attualmente in esecuzione (il thread che ha chiamato il callback) è quello che viene sospeso, questo callback si verifica prima che il thread è sospeso.</span><span class="sxs-lookup"><span data-stu-id="b1d09-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1d09-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1d09-112">Requirements</span></span>  
 <span data-ttu-id="b1d09-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d09-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1d09-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1d09-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1d09-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1d09-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d09-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d09-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1d09-117">See Also</span></span>  
 [<span data-ttu-id="b1d09-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b1d09-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b1d09-119">RuntimeThreadResumed (metodo)</span><span class="sxs-lookup"><span data-stu-id="b1d09-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
