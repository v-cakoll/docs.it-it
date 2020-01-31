---
title: Funzione FunctionEnter3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: 75a9a7174f105d99e9d1c9b220cfc5bf928d46ec
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866970"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="74c3d-102">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="74c3d-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="74c3d-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare il stack frame e gli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="74c3d-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74c3d-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74c3d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74c3d-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="74c3d-106">\[in] identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="74c3d-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="74c3d-107">\[in] handle opaco che rappresenta le informazioni relative a una stack frame specificata.</span><span class="sxs-lookup"><span data-stu-id="74c3d-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="74c3d-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="74c3d-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="74c3d-109">Note</span><span class="sxs-lookup"><span data-stu-id="74c3d-109">Remarks</span></span>  
 <span data-ttu-id="74c3d-110">Il metodo di callback `FunctionEnter3WithInfo` notifica al profiler la chiamata di funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per esaminare i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="74c3d-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="74c3d-111">Per accedere alle informazioni sugli argomenti, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="74c3d-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="74c3d-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="74c3d-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="74c3d-113">La funzione `FunctionEnter3WithInfo` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="74c3d-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="74c3d-114">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="74c3d-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="74c3d-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="74c3d-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="74c3d-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="74c3d-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="74c3d-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="74c3d-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="74c3d-118">L'implementazione di `FunctionEnter3WithInfo` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="74c3d-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="74c3d-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="74c3d-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="74c3d-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionEnter3WithInfo` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="74c3d-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="74c3d-121">La funzione `FunctionEnter3WithInfo` non deve chiamare codice gestito o causare un'allocazione di managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="74c3d-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c3d-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="74c3d-122">Requirements</span></span>  
 <span data-ttu-id="74c3d-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c3d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c3d-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="74c3d-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="74c3d-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74c3d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74c3d-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c3d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c3d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74c3d-127">See also</span></span>

- [<span data-ttu-id="74c3d-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="74c3d-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="74c3d-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="74c3d-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="74c3d-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="74c3d-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="74c3d-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="74c3d-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
