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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a36f9b54ce7ac6a0a5a22b33a4d07150a96f40b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452543"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="ff224-102">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ff224-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="ff224-103">Notifica al profiler di controllo viene passato a una funzione e fornisce un handle che può essere passato al [ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare gli argomenti di stack frame e la funzione.</span><span class="sxs-lookup"><span data-stu-id="ff224-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff224-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff224-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff224-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff224-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="ff224-106">[in] Identificatore della funzione a cui il controllo viene passato.</span><span class="sxs-lookup"><span data-stu-id="ff224-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="ff224-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="ff224-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="ff224-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="ff224-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff224-109">Note</span><span class="sxs-lookup"><span data-stu-id="ff224-109">Remarks</span></span>  
 <span data-ttu-id="ff224-110">Il `FunctionEnter3WithInfo` metodo di callback di notifica al profiler le funzioni che vengono chiamati e consente al profiler di usare il [ICorProfilerInfo3:: GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per controllare i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ff224-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="ff224-111">Per accedere alle informazioni di argomento, la `COR_PRF_ENABLE_FUNCTION_ARGS` flag deve essere impostata.</span><span class="sxs-lookup"><span data-stu-id="ff224-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="ff224-112">Il profiler può utilizzare il [metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ff224-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ff224-113">Il `FunctionEnter3WithInfo` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="ff224-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="ff224-114">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ff224-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="ff224-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ff224-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ff224-116">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="ff224-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ff224-117">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="ff224-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ff224-118">L'implementazione di `FunctionEnter3WithInfo` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ff224-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="ff224-119">L'implementazione non deve tentare una garbage collection, perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="ff224-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ff224-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionEnter3WithInfo` restituisce.</span><span class="sxs-lookup"><span data-stu-id="ff224-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="ff224-121">Il `FunctionEnter3WithInfo` funzione non deve chiamare codice gestito o causare un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="ff224-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff224-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff224-122">Requirements</span></span>  
 <span data-ttu-id="ff224-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff224-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff224-124">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="ff224-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ff224-125">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ff224-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff224-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff224-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff224-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff224-127">See Also</span></span>  
 [<span data-ttu-id="ff224-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="ff224-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)  
 [<span data-ttu-id="ff224-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ff224-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="ff224-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ff224-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="ff224-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="ff224-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
