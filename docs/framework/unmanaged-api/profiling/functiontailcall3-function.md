---
title: Funzione FunctionTailcall3
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
ms.openlocfilehash: 8d7c226d26d677a8b10df29e0343b71682c46699
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427370"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="34bd5-102">Funzione FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="34bd5-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="34bd5-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span><span class="sxs-lookup"><span data-stu-id="34bd5-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34bd5-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34bd5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34bd5-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="34bd5-106">[in] The identifier of the currently executing function that is about to make a tail call.</span><span class="sxs-lookup"><span data-stu-id="34bd5-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34bd5-107">Note</span><span class="sxs-lookup"><span data-stu-id="34bd5-107">Remarks</span></span>  
 <span data-ttu-id="34bd5-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span><span class="sxs-lookup"><span data-stu-id="34bd5-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="34bd5-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span><span class="sxs-lookup"><span data-stu-id="34bd5-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="34bd5-110">The `FunctionTailcall3` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="34bd5-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="34bd5-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="34bd5-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="34bd5-112">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="34bd5-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="34bd5-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="34bd5-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="34bd5-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="34bd5-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="34bd5-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="34bd5-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="34bd5-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="34bd5-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="34bd5-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span><span class="sxs-lookup"><span data-stu-id="34bd5-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="34bd5-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span><span class="sxs-lookup"><span data-stu-id="34bd5-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bd5-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34bd5-119">Requirements</span></span>  
 <span data-ttu-id="34bd5-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34bd5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34bd5-121">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="34bd5-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="34bd5-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34bd5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34bd5-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34bd5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34bd5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34bd5-124">See also</span></span>

- [<span data-ttu-id="34bd5-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="34bd5-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="34bd5-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="34bd5-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="34bd5-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34bd5-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="34bd5-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34bd5-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="34bd5-129">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34bd5-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="34bd5-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="34bd5-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="34bd5-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34bd5-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="34bd5-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="34bd5-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="34bd5-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="34bd5-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="34bd5-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="34bd5-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
