---
title: Funzione FunctionTailcall3
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 636ff5613b2681a73986cc5bfe9a28954f014588
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598792"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="575da-102">Funzione FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="575da-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="575da-103">Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail ad un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="575da-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="575da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575da-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="575da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="575da-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="575da-106">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="575da-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="575da-107">Note</span><span class="sxs-lookup"><span data-stu-id="575da-107">Remarks</span></span>  
 <span data-ttu-id="575da-108">Il `FunctionTailcall3` funzione di callback di notifica al profiler che vengono chiamate le funzioni.</span><span class="sxs-lookup"><span data-stu-id="575da-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="575da-109">Usare la [metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="575da-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="575da-110">Il `FunctionTailcall3` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="575da-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="575da-111">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="575da-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="575da-112">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="575da-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="575da-113">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="575da-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="575da-114">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="575da-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="575da-115">L'implementazione di `FunctionTailcall3` non devono bloccare, perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="575da-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="575da-116">L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="575da-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="575da-117">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionTailcall3` restituisce.</span><span class="sxs-lookup"><span data-stu-id="575da-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="575da-118">Il `FunctionTailcall3` funzione non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="575da-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="575da-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="575da-119">Requirements</span></span>  
 <span data-ttu-id="575da-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="575da-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="575da-121">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="575da-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="575da-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="575da-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="575da-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="575da-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575da-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="575da-124">See also</span></span>

- [<span data-ttu-id="575da-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="575da-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="575da-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="575da-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="575da-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="575da-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="575da-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="575da-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="575da-129">Funzione FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="575da-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="575da-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="575da-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="575da-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="575da-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="575da-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="575da-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="575da-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="575da-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="575da-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="575da-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
