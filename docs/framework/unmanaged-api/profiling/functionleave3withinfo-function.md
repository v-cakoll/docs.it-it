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
ms.openlocfilehash: a62f402fbfae6188ab0423ea7a55a4dfc6cb4112
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427405"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="4fc43-102">Funzione FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fc43-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="4fc43-103">Notifica al profiler che il controllo viene restituito da una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare il stack frame e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4fc43-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fc43-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fc43-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4fc43-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="4fc43-106">in Identificatore della funzione da cui viene restituito il controllo.</span><span class="sxs-lookup"><span data-stu-id="4fc43-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="4fc43-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="4fc43-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="4fc43-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="4fc43-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc43-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4fc43-109">Remarks</span></span>  
 <span data-ttu-id="4fc43-110">Il metodo di callback `FunctionLeave3WithInfo` notifica al profiler la chiamata di funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per esaminare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="4fc43-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="4fc43-111">Per accedere alle informazioni sul valore restituito, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="4fc43-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="4fc43-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4fc43-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="4fc43-113">La funzione `FunctionLeave3WithInfo` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="4fc43-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="4fc43-114">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4fc43-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="4fc43-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4fc43-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="4fc43-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="4fc43-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="4fc43-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="4fc43-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="4fc43-118">L'implementazione di `FunctionLeave3WithInfo` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4fc43-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="4fc43-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4fc43-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="4fc43-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionLeave3WithInfo` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="4fc43-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="4fc43-121">La funzione `FunctionLeave3WithInfo` non deve chiamare codice gestito o causare un'allocazione di managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="4fc43-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc43-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fc43-122">Requirements</span></span>  
 <span data-ttu-id="4fc43-123">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fc43-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc43-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="4fc43-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4fc43-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fc43-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fc43-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc43-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc43-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fc43-127">See also</span></span>

- [<span data-ttu-id="4fc43-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="4fc43-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="4fc43-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="4fc43-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="4fc43-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4fc43-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="4fc43-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="4fc43-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="4fc43-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fc43-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="4fc43-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fc43-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4fc43-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="4fc43-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="4fc43-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4fc43-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="4fc43-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4fc43-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4fc43-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4fc43-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="4fc43-138">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="4fc43-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
