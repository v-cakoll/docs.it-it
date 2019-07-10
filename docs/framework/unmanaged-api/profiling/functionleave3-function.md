---
title: Funzione FunctionLeave3
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27b2241f7eb0e1ce8b0728a54028f9b4a6112e36
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781259"
---
# <a name="functionleave3-function"></a><span data-ttu-id="776b9-102">Funzione FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="776b9-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="776b9-103">Notifica al profiler che controllo viene restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="776b9-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="776b9-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="776b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="776b9-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="776b9-106">[in] L'identificatore della funzione da cui il controllo viene restituito.</span><span class="sxs-lookup"><span data-stu-id="776b9-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="776b9-107">Note</span><span class="sxs-lookup"><span data-stu-id="776b9-107">Remarks</span></span>  
 <span data-ttu-id="776b9-108">Il `FunctionLeave3` funzione di callback di notifica al profiler le funzioni che vengono chiamati, ma non supporta l'esame del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="776b9-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="776b9-109">Usare la [metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="776b9-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="776b9-110">Il `FunctionLeave3` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="776b9-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="776b9-111">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="776b9-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="776b9-112">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="776b9-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="776b9-113">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="776b9-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="776b9-114">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="776b9-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="776b9-115">L'implementazione di `FunctionLeave3` non devono bloccare, perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="776b9-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="776b9-116">L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="776b9-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="776b9-117">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionLeave3` restituisce.</span><span class="sxs-lookup"><span data-stu-id="776b9-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="776b9-118">Il `FunctionLeave3` funzione non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="776b9-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776b9-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="776b9-119">Requirements</span></span>  
 <span data-ttu-id="776b9-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="776b9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776b9-121">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="776b9-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="776b9-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="776b9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="776b9-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776b9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776b9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="776b9-124">See also</span></span>

- [<span data-ttu-id="776b9-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="776b9-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="776b9-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="776b9-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="776b9-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="776b9-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="776b9-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="776b9-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="776b9-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="776b9-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="776b9-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="776b9-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="776b9-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="776b9-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="776b9-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="776b9-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="776b9-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="776b9-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="776b9-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="776b9-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
