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
ms.openlocfilehash: bd87709a9e8b0e943bcf89aa528872d465526218
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454285"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="a9172-102">Funzione FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9172-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="a9172-103">Notifica al profiler che controllo viene restituito da una funzione e fornisce un handle che può essere passato al [ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare lo stack frame e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="a9172-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9172-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9172-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9172-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9172-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="a9172-106">[in] Identificatore della funzione da cui il controllo viene restituito.</span><span class="sxs-lookup"><span data-stu-id="a9172-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a9172-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="a9172-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a9172-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="a9172-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9172-109">Note</span><span class="sxs-lookup"><span data-stu-id="a9172-109">Remarks</span></span>  
 <span data-ttu-id="a9172-110">Il `FunctionLeave3WithInfo` metodo di callback di notifica al profiler le funzioni che vengono chiamate e consente al profiler di usare il [ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) per controllare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="a9172-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="a9172-111">Per accedere alle informazioni di valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostata.</span><span class="sxs-lookup"><span data-stu-id="a9172-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="a9172-112">Il profiler può utilizzare il [metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="a9172-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a9172-113">Il `FunctionLeave3WithInfo` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="a9172-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="a9172-114">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a9172-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="a9172-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="a9172-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="a9172-116">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="a9172-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="a9172-117">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="a9172-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a9172-118">L'implementazione di `FunctionLeave3WithInfo` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a9172-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="a9172-119">L'implementazione non deve tentare una garbage collection, perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="a9172-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a9172-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionLeave3WithInfo` restituisce.</span><span class="sxs-lookup"><span data-stu-id="a9172-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="a9172-121">Il `FunctionLeave3WithInfo` funzione non deve chiamare codice gestito o causare un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="a9172-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9172-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9172-122">Requirements</span></span>  
 <span data-ttu-id="a9172-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9172-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9172-124">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="a9172-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a9172-125">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a9172-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9172-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9172-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9172-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9172-127">See Also</span></span>  
 [<span data-ttu-id="a9172-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="a9172-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)  
 [<span data-ttu-id="a9172-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="a9172-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="a9172-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a9172-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="a9172-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="a9172-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="a9172-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9172-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="a9172-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9172-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="a9172-134">Metodo SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="a9172-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="a9172-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9172-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="a9172-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="a9172-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="a9172-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="a9172-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="a9172-138">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="a9172-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
