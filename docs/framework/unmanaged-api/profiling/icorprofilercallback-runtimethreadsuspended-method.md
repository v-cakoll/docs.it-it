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
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865870"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="a50c6-102">Metodo ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="a50c6-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="a50c6-103">Notifica al profiler che il thread specificato è stato sospeso o sta per essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="a50c6-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a50c6-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a50c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a50c6-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a50c6-106">in ID del thread che è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="a50c6-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50c6-107">Note</span><span class="sxs-lookup"><span data-stu-id="a50c6-107">Remarks</span></span>  
 <span data-ttu-id="a50c6-108">La notifica di `RuntimeThreadSuspended` può verificarsi in qualsiasi momento tra i callback ICorProfilerCallback [:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) e i callback [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) associati.</span><span class="sxs-lookup"><span data-stu-id="a50c6-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="a50c6-109">Le notifiche che si verificano tra [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) e `RuntimeResumeStarted` sono per i thread che erano in esecuzione nel codice non gestito e sono stati sospesi al momento dell'immissione nel Runtime.</span><span class="sxs-lookup"><span data-stu-id="a50c6-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="a50c6-110">In genere, questo callback si verifica subito dopo la sospensione di un thread.</span><span class="sxs-lookup"><span data-stu-id="a50c6-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="a50c6-111">Tuttavia, se il thread attualmente in esecuzione (il thread che ha chiamato questo callback) è quello che viene sospeso, questo callback si verificherà immediatamente prima della sospensione del thread.</span><span class="sxs-lookup"><span data-stu-id="a50c6-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50c6-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a50c6-112">Requirements</span></span>  
 <span data-ttu-id="a50c6-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a50c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50c6-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a50c6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a50c6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a50c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a50c6-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50c6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a50c6-117">See also</span></span>

- [<span data-ttu-id="a50c6-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a50c6-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a50c6-119">Metodo RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="a50c6-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
