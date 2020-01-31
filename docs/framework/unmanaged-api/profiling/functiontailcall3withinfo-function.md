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
ms.openlocfilehash: 0aa43954c3e10d04524bf976d0dd3b29d2bc724c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866830"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="3f61b-102">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3f61b-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="3f61b-103">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) per recuperare il stack frame.</span><span class="sxs-lookup"><span data-stu-id="3f61b-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f61b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f61b-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f61b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f61b-105">Parameters</span></span>  

- `functionIDOrClientID`

  <span data-ttu-id="3f61b-106">\[in] identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="3f61b-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `eltInfo`

  <span data-ttu-id="3f61b-107">\[in] handle opaco che rappresenta le informazioni relative a una stack frame specificata.</span><span class="sxs-lookup"><span data-stu-id="3f61b-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="3f61b-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="3f61b-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f61b-109">Note</span><span class="sxs-lookup"><span data-stu-id="3f61b-109">Remarks</span></span>  
 <span data-ttu-id="3f61b-110">Il metodo di callback `FunctionTailcall3WithInfo` notifica al profiler la chiamata di funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) per esaminare l'stack frame.</span><span class="sxs-lookup"><span data-stu-id="3f61b-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="3f61b-111">Per accedere alle informazioni stack frame, è necessario impostare il flag di `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="3f61b-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="3f61b-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="3f61b-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="3f61b-113">La funzione `FunctionTailcall3WithInfo` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="3f61b-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="3f61b-114">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3f61b-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="3f61b-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="3f61b-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3f61b-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="3f61b-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3f61b-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3f61b-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3f61b-118">L'implementazione di `FunctionTailcall3WithInfo` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3f61b-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="3f61b-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3f61b-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3f61b-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionTailcall3WithInfo` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="3f61b-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="3f61b-121">Inoltre, la funzione FunctionTailcall3WithInfo non deve chiamare nel codice gestito o causare un'allocazione managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="3f61b-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f61b-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3f61b-122">Requirements</span></span>  
 <span data-ttu-id="3f61b-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f61b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f61b-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="3f61b-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3f61b-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f61b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f61b-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f61b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f61b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f61b-127">See also</span></span>

- [<span data-ttu-id="3f61b-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="3f61b-128">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="3f61b-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="3f61b-129">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="3f61b-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="3f61b-130">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="3f61b-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3f61b-131">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="3f61b-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3f61b-132">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="3f61b-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="3f61b-133">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="3f61b-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3f61b-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="3f61b-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="3f61b-135">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="3f61b-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="3f61b-136">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="3f61b-137">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="3f61b-137">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
