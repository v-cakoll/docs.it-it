---
title: Metodo ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9c9cd0b042dc22f35c38e349ab8881dafc602731
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445011"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="96d95-102">Metodo ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="96d95-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="96d95-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span><span class="sxs-lookup"><span data-stu-id="96d95-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96d95-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96d95-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="96d95-106">[in] The identifier of the function containing the `catch` block.</span><span class="sxs-lookup"><span data-stu-id="96d95-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="96d95-107">[in] The identifier of the exception being handled.</span><span class="sxs-lookup"><span data-stu-id="96d95-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96d95-108">Note</span><span class="sxs-lookup"><span data-stu-id="96d95-108">Remarks</span></span>  
 <span data-ttu-id="96d95-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span><span class="sxs-lookup"><span data-stu-id="96d95-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="96d95-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span><span class="sxs-lookup"><span data-stu-id="96d95-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="96d95-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span><span class="sxs-lookup"><span data-stu-id="96d95-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="96d95-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="96d95-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="96d95-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="96d95-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="96d95-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="96d95-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d95-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96d95-115">Requirements</span></span>  
 <span data-ttu-id="96d95-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96d95-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d95-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96d95-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96d95-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d95-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d95-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d95-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d95-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96d95-120">See also</span></span>

- [<span data-ttu-id="96d95-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="96d95-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="96d95-122">Metodo ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="96d95-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
