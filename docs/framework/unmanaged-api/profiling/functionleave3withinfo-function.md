---
title: Funzione FunctionLeave3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 714514d5b6a36d028da442bcc05accc0686417cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500616"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="af5c2-102">Funzione FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af5c2-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="af5c2-103">Notifica al profiler che controllo viene restituito da una funzione e fornisce un handle che può essere passato al [metodo ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare lo stack frame e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="af5c2-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af5c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af5c2-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af5c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af5c2-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="af5c2-106">[in] L'identificatore della funzione da cui il controllo viene restituito.</span><span class="sxs-lookup"><span data-stu-id="af5c2-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="af5c2-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="af5c2-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="af5c2-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="af5c2-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af5c2-109">Note</span><span class="sxs-lookup"><span data-stu-id="af5c2-109">Remarks</span></span>  
 <span data-ttu-id="af5c2-110">Il `FunctionLeave3WithInfo` metodo di callback di notifica al profiler le funzioni che vengono chiamate e consente al profiler di usare il [metodo ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per controllare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="af5c2-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="af5c2-111">Per accedere alle informazioni di valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostata.</span><span class="sxs-lookup"><span data-stu-id="af5c2-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="af5c2-112">Il profiler può usare la [SetEventMask (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento e quindi utilizzare il [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="af5c2-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="af5c2-113">Il `FunctionLeave3WithInfo` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="af5c2-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="af5c2-114">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="af5c2-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="af5c2-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="af5c2-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="af5c2-116">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="af5c2-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="af5c2-117">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="af5c2-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="af5c2-118">L'implementazione di `FunctionLeave3WithInfo` non devono bloccare, perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="af5c2-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="af5c2-119">L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="af5c2-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="af5c2-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionLeave3WithInfo` restituisce.</span><span class="sxs-lookup"><span data-stu-id="af5c2-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="af5c2-121">Il `FunctionLeave3WithInfo` funzione non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="af5c2-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af5c2-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af5c2-122">Requirements</span></span>  
 <span data-ttu-id="af5c2-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af5c2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af5c2-124">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="af5c2-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="af5c2-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af5c2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af5c2-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af5c2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5c2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af5c2-127">See also</span></span>
- [<span data-ttu-id="af5c2-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="af5c2-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="af5c2-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="af5c2-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="af5c2-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="af5c2-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="af5c2-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="af5c2-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="af5c2-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af5c2-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="af5c2-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af5c2-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="af5c2-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="af5c2-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="af5c2-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af5c2-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="af5c2-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="af5c2-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="af5c2-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="af5c2-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="af5c2-138">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="af5c2-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
