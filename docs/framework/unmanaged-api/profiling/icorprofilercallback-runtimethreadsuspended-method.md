---
title: Metodo ICorProfilerCallback::RuntimeThreadSuspended
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d03e760d2b08cd9ee8cdfd85e2e28223aeacd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747229"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="0f7c6-102">Metodo ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="0f7c6-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="0f7c6-103">Notifica al profiler che il thread specificato è stato sospeso o sta per essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f7c6-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f7c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f7c6-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0f7c6-106">[in] L'ID del thread che è stata sospesa.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f7c6-107">Note</span><span class="sxs-lookup"><span data-stu-id="0f7c6-107">Remarks</span></span>  
 <span data-ttu-id="0f7c6-108">Il `RuntimeThreadSuspended` notifica può verificarsi in qualsiasi momento tra il [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) associate [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) i callback.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="0f7c6-109">Le notifiche che si verificano tra [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e `RuntimeResumeStarted` sono per i thread che era in esecuzione nel codice non gestito e sono stati sospesi al momento dell'accesso al runtime.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="0f7c6-110">In genere, questo callback si verifica solo dopo che un thread viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="0f7c6-111">Tuttavia, se il thread attualmente in esecuzione (il thread che ha chiamato tale callback) è quello che è stato sospeso, questo callback si verificherà prima che il thread viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="0f7c6-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7c6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f7c6-112">Requirements</span></span>  
 <span data-ttu-id="0f7c6-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f7c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f7c6-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f7c6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f7c6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f7c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f7c6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f7c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7c6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f7c6-117">See also</span></span>

- [<span data-ttu-id="0f7c6-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0f7c6-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0f7c6-119">Metodo RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="0f7c6-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
