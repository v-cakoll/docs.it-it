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
ms.openlocfilehash: f7a945fb7ef10f995be2d779a88b98bbce2fdfb3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866843"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="ae7de-102">Funzione FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ae7de-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="ae7de-103">Notifica al profiler che il controllo viene restituito da una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) per recuperare il stack frame e il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="ae7de-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae7de-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae7de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae7de-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="ae7de-106">\[in] identificatore della funzione da cui viene restituito il controllo.</span><span class="sxs-lookup"><span data-stu-id="ae7de-106">\[in] The identifier of the function from which control is returned.</span></span>

- `eltInfo`

  <span data-ttu-id="ae7de-107">\[in] handle opaco che rappresenta le informazioni relative a una stack frame specificata.</span><span class="sxs-lookup"><span data-stu-id="ae7de-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="ae7de-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="ae7de-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae7de-109">Note</span><span class="sxs-lookup"><span data-stu-id="ae7de-109">Remarks</span></span>  
 <span data-ttu-id="ae7de-110">Il metodo di callback `FunctionLeave3WithInfo` notifica al profiler la chiamata di funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) per esaminare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="ae7de-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="ae7de-111">Per accedere alle informazioni sul valore restituito, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="ae7de-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="ae7de-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ae7de-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ae7de-113">La funzione `FunctionLeave3WithInfo` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="ae7de-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="ae7de-114">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ae7de-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="ae7de-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ae7de-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ae7de-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="ae7de-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ae7de-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="ae7de-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ae7de-118">L'implementazione di `FunctionLeave3WithInfo` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ae7de-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="ae7de-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ae7de-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ae7de-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionLeave3WithInfo` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="ae7de-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="ae7de-121">La funzione `FunctionLeave3WithInfo` non deve chiamare codice gestito o causare un'allocazione di managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="ae7de-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7de-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ae7de-122">Requirements</span></span>  
 <span data-ttu-id="ae7de-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae7de-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7de-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="ae7de-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ae7de-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae7de-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae7de-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7de-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7de-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae7de-127">See also</span></span>

- [<span data-ttu-id="ae7de-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="ae7de-128">GetFunctionLeave3Info</span></span>](icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="ae7de-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ae7de-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="ae7de-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ae7de-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="ae7de-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="ae7de-131">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="ae7de-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ae7de-132">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="ae7de-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ae7de-133">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="ae7de-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="ae7de-134">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="ae7de-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ae7de-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="ae7de-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="ae7de-136">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="ae7de-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="ae7de-137">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="ae7de-138">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="ae7de-138">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
