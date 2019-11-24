---
title: Metodo ICorProfilerCallback::RuntimeSuspendAborted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: fb09a9422f2aeec239f9aef25fb61c731e0aa2e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430618"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="c6ba0-102">Metodo ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="c6ba0-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="c6ba0-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span><span class="sxs-lookup"><span data-stu-id="c6ba0-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ba0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6ba0-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6ba0-105">Note</span><span class="sxs-lookup"><span data-stu-id="c6ba0-105">Remarks</span></span>  
 <span data-ttu-id="c6ba0-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span><span class="sxs-lookup"><span data-stu-id="c6ba0-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="c6ba0-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="c6ba0-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="c6ba0-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="c6ba0-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ba0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6ba0-109">Requirements</span></span>  
 <span data-ttu-id="c6ba0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ba0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ba0-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6ba0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6ba0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6ba0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6ba0-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ba0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ba0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6ba0-114">See also</span></span>

- [<span data-ttu-id="c6ba0-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c6ba0-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
