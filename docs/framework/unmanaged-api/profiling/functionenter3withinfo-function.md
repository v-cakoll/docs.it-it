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
ms.openlocfilehash: 86b1c8b3f5bd88b216c59f5cc6846f83f3c094ee
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440755"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="ea5b8-102">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ea5b8-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="ea5b8-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare il stack frame e gli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea5b8-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea5b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea5b8-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="ea5b8-106">in Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="ea5b8-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="ea5b8-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea5b8-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea5b8-109">Remarks</span></span>  
 <span data-ttu-id="ea5b8-110">Il metodo di callback `FunctionEnter3WithInfo` notifica al profiler la chiamata di funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per esaminare i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="ea5b8-111">Per accedere alle informazioni sugli argomenti, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="ea5b8-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ea5b8-113">La funzione `FunctionEnter3WithInfo` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="ea5b8-114">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="ea5b8-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ea5b8-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="ea5b8-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ea5b8-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ea5b8-118">L'implementazione di `FunctionEnter3WithInfo` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="ea5b8-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ea5b8-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionEnter3WithInfo` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="ea5b8-121">La funzione `FunctionEnter3WithInfo` non deve chiamare codice gestito o causare un'allocazione di managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="ea5b8-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5b8-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea5b8-122">Requirements</span></span>  
 <span data-ttu-id="ea5b8-123">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea5b8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5b8-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="ea5b8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ea5b8-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea5b8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea5b8-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5b8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5b8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea5b8-127">See also</span></span>

- [<span data-ttu-id="ea5b8-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="ea5b8-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="ea5b8-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ea5b8-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="ea5b8-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ea5b8-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="ea5b8-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="ea5b8-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
