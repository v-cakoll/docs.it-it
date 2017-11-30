---
title: Funzione FunctionEnter2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter2
helpviewer_keywords: FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0aa1d98021dcbfc38721d7f30ad305065dced605
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter2-function"></a><span data-ttu-id="27964-102">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="27964-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="27964-103">Notifica al profiler che controllo viene passato a una funzione e fornisce informazioni sullo stack di frame e funzione gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="27964-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="27964-104">Questa funzione sostituisce la [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="27964-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27964-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27964-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27964-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="27964-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="27964-107">[in] Identificatore della funzione a cui il controllo viene passato.</span><span class="sxs-lookup"><span data-stu-id="27964-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="27964-108">[in] Identificatore della funzione modificato, il profiler può essere specificata in precedenza tramite il [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="27964-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="27964-109">[in] Oggetto `COR_PRF_FRAME_INFO` che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="27964-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="27964-110">Il profiler deve trattare come handle opaco che può essere passato al motore di esecuzione di [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="27964-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="27964-111">[in] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura che specifica le posizioni in memoria degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="27964-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="27964-112">Per accedere alle informazioni degli argomenti di `COR_PRF_ENABLE_FUNCTION_ARGS` flag deve essere impostato.</span><span class="sxs-lookup"><span data-stu-id="27964-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="27964-113">Il profiler può utilizzare il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="27964-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27964-114">Note</span><span class="sxs-lookup"><span data-stu-id="27964-114">Remarks</span></span>  
 <span data-ttu-id="27964-115">I valori del `func` e `argumentInfo` parametri non sono validi dopo il `FunctionEnter2` funzione perché i valori potrebbero cambiare o essere distrutti.</span><span class="sxs-lookup"><span data-stu-id="27964-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="27964-116">Il `FunctionEnter2` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="27964-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="27964-117">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27964-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="27964-118">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="27964-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="27964-119">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="27964-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="27964-120">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="27964-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="27964-121">L'implementazione di `FunctionEnter2` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="27964-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="27964-122">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="27964-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="27964-123">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionEnter2` restituisce.</span><span class="sxs-lookup"><span data-stu-id="27964-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="27964-124">Inoltre, il `FunctionEnter2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="27964-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27964-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27964-125">Requirements</span></span>  
 <span data-ttu-id="27964-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27964-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27964-127">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="27964-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="27964-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27964-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27964-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27964-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27964-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27964-130">See Also</span></span>  
 [<span data-ttu-id="27964-131">FunctionLeave2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="27964-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="27964-132">FunctionTailcall2 (funzione)</span><span class="sxs-lookup"><span data-stu-id="27964-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="27964-133">SetEnterLeaveFunctionHooks2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="27964-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="27964-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="27964-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
