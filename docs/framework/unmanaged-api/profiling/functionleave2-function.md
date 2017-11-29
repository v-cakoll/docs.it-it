---
title: Funzione FunctionLeave2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave2
helpviewer_keywords: FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c2dd85e23a54a20920e30e22bc91f88a813be39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave2-function"></a><span data-ttu-id="f002e-102">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="f002e-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="f002e-103">Notifica al profiler che una funzione sta per restituire al chiamante e fornisce informazioni sul valore restituito dello stack frame e la funzione.</span><span class="sxs-lookup"><span data-stu-id="f002e-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f002e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f002e-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f002e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f002e-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="f002e-106">[in] Identificatore della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="f002e-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="f002e-107">[in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite il [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f002e-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="f002e-108">[in] Oggetto `COR_PRF_FRAME_INFO` che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="f002e-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="f002e-109">Il profiler deve trattare come handle opaco che può essere passato al motore di esecuzione di [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="f002e-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="f002e-110">[in] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struttura che specifica la posizione di memoria del valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="f002e-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="f002e-111">Per accedere alle informazioni sul valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostato.</span><span class="sxs-lookup"><span data-stu-id="f002e-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="f002e-112">Il profiler può utilizzare il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f002e-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f002e-113">Note</span><span class="sxs-lookup"><span data-stu-id="f002e-113">Remarks</span></span>  
 <span data-ttu-id="f002e-114">I valori del `func` e `retvalRange` parametri non sono validi dopo il `FunctionLeave2` funzione perché i valori potrebbero cambiare o essere distrutti.</span><span class="sxs-lookup"><span data-stu-id="f002e-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="f002e-115">Il `FunctionLeave2` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="f002e-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="f002e-116">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f002e-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="f002e-117">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="f002e-117">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="f002e-118">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="f002e-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="f002e-119">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="f002e-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f002e-120">L'implementazione di `FunctionLeave2` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f002e-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="f002e-121">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="f002e-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f002e-122">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionLeave2` restituisce.</span><span class="sxs-lookup"><span data-stu-id="f002e-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="f002e-123">Inoltre, il `FunctionLeave2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="f002e-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f002e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f002e-124">Requirements</span></span>  
 <span data-ttu-id="f002e-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f002e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f002e-126">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f002e-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f002e-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f002e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f002e-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f002e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f002e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f002e-129">See Also</span></span>  
 [<span data-ttu-id="f002e-130">FunctionEnter2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="f002e-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="f002e-131">FunctionTailcall2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="f002e-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="f002e-132">SetEnterLeaveFunctionHooks2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="f002e-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="f002e-133">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="f002e-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
