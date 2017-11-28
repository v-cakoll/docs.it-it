---
title: Funzione FunctionTailcall3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall3
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall3
helpviewer_keywords: FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5d274c966a345e0e2984018bcd8aa1e2dade03b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="76022-102">Funzione FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="76022-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="76022-103">Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail a un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="76022-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76022-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76022-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76022-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76022-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="76022-106">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="76022-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76022-107">Note</span><span class="sxs-lookup"><span data-stu-id="76022-107">Remarks</span></span>  
 <span data-ttu-id="76022-108">Il `FunctionTailcall3` funzione di callback di notifica al profiler che vengono chiamate funzioni.</span><span class="sxs-lookup"><span data-stu-id="76022-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="76022-109">Utilizzare il [metodo ICorProfilerInfo3:: Setenterleavefunctionhooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="76022-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="76022-110">Il `FunctionTailcall3` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="76022-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="76022-111">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="76022-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="76022-112">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="76022-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="76022-113">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="76022-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="76022-114">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="76022-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="76022-115">L'implementazione di `FunctionTailcall3` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="76022-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="76022-116">L'implementazione non deve tentare una garbage collection, perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="76022-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="76022-117">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionTailcall3` restituisce.</span><span class="sxs-lookup"><span data-stu-id="76022-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="76022-118">Il `FunctionTailcall3` funzione non deve chiamare codice gestito o causare un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="76022-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76022-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76022-119">Requirements</span></span>  
 <span data-ttu-id="76022-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76022-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76022-121">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="76022-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="76022-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76022-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76022-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76022-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76022-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76022-124">See Also</span></span>  
 [<span data-ttu-id="76022-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="76022-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="76022-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="76022-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="76022-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="76022-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="76022-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="76022-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="76022-129">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="76022-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="76022-130">Metodo SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="76022-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="76022-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="76022-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="76022-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="76022-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="76022-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="76022-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="76022-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="76022-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
