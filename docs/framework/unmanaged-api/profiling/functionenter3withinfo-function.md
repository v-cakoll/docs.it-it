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
ms.openlocfilehash: 16e086f54865307e116a9e522b2fbadee8502249
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105677"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="5c6d6-102">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5c6d6-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="5c6d6-103">Notifica al profiler di controllo viene passato a una funzione e fornisce un handle che può essere passato al [metodo ICorProfilerInfo3::GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare gli argomenti di stack frame e la funzione.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c6d6-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c6d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c6d6-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="5c6d6-106">[in] L'identificatore della funzione a cui il controllo viene passato.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="5c6d6-107">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="5c6d6-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c6d6-109">Note</span><span class="sxs-lookup"><span data-stu-id="5c6d6-109">Remarks</span></span>  
 <span data-ttu-id="5c6d6-110">Il `FunctionEnter3WithInfo` metodo di callback di notifica al profiler le funzioni che vengono chiamati e consente al profiler di usare il [ICorProfilerInfo3::GetFunctionEnter3Info (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) per esaminare i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="5c6d6-111">Per accedere alle informazioni sull'argomento, il `COR_PRF_ENABLE_FUNCTION_ARGS` flag deve essere impostata.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="5c6d6-112">Il profiler può usare la [SetEventMask (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento e quindi utilizzare il [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="5c6d6-113">Il `FunctionEnter3WithInfo` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="5c6d6-114">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="5c6d6-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="5c6d6-116">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="5c6d6-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="5c6d6-117">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5c6d6-118">L'implementazione di `FunctionEnter3WithInfo` non devono bloccare, perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="5c6d6-119">L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5c6d6-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionEnter3WithInfo` restituisce.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="5c6d6-121">Il `FunctionEnter3WithInfo` funzione non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="5c6d6-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6d6-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c6d6-122">Requirements</span></span>  
 <span data-ttu-id="5c6d6-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6d6-124">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5c6d6-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5c6d6-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c6d6-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c6d6-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c6d6-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c6d6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c6d6-127">See also</span></span>

- [<span data-ttu-id="5c6d6-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="5c6d6-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="5c6d6-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="5c6d6-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="5c6d6-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="5c6d6-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="5c6d6-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="5c6d6-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
