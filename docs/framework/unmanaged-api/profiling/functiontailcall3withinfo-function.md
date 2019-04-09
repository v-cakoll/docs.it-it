---
title: Funzione FunctionTailcall3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4352d006c95a5b85341625220e6c7e62a86b482a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178087"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="e2d2e-102">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d2e-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="e2d2e-103">Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail ad un'altra funzione e fornisce un handle che può essere passato al [metodo ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) per recuperare il frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2d2e-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2d2e-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="e2d2e-106">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="e2d2e-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="e2d2e-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d2e-109">Note</span><span class="sxs-lookup"><span data-stu-id="e2d2e-109">Remarks</span></span>  
 <span data-ttu-id="e2d2e-110">Il `FunctionTailcall3WithInfo` metodo di callback di notifica al profiler le funzioni che vengono chiamate e consente al profiler di usare il [metodo ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) per esaminare lo stack frame.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="e2d2e-111">Per accedere alle informazioni sullo stack frame, la `COR_PRF_ENABLE_FRAME_INFO` flag deve essere impostata.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="e2d2e-112">Il profiler può usare la [SetEventMask (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento e quindi utilizzare il [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e2d2e-113">Il `FunctionTailcall3WithInfo` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="e2d2e-114">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="e2d2e-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="e2d2e-116">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="e2d2e-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="e2d2e-117">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e2d2e-118">L'implementazione di `FunctionTailcall3WithInfo` non devono bloccare, perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="e2d2e-119">L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e2d2e-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionTailcall3WithInfo` restituisce.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="e2d2e-121">Inoltre, la funzione FunctionTailcall3WithInfo non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="e2d2e-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d2e-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2d2e-122">Requirements</span></span>  
 <span data-ttu-id="e2d2e-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d2e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d2e-124">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e2d2e-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e2d2e-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d2e-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e2d2e-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e2d2e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2d2e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2d2e-127">See also</span></span>

- [<span data-ttu-id="e2d2e-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e2d2e-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e2d2e-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e2d2e-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e2d2e-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e2d2e-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e2d2e-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d2e-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e2d2e-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d2e-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e2d2e-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e2d2e-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e2d2e-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e2d2e-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="e2d2e-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e2d2e-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e2d2e-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e2d2e-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e2d2e-137">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="e2d2e-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
