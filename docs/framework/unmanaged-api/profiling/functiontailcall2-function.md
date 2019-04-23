---
title: Funzione FunctionTailcall2
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06dd3b028f4f43ca8681c80a5caa4716104068dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080891"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="b8b36-102">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="b8b36-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="b8b36-103">Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail ad un'altra funzione e fornisce informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b8b36-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8b36-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8b36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8b36-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="b8b36-106">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8b36-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="b8b36-107">[in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8b36-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="b8b36-108">[in] Oggetto `COR_PRF_FRAME_INFO` valore che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b8b36-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="b8b36-109">Il profiler deve trattarlo come un handle opaco che può essere passato al motore di esecuzione la [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b8b36-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8b36-110">Note</span><span class="sxs-lookup"><span data-stu-id="b8b36-110">Remarks</span></span>  
 <span data-ttu-id="b8b36-111">La funzione di destinazione della chiamata tail verrà utilizzato lo stack frame corrente e restituirà direttamente al chiamante della funzione che ha effettuato la parte finale di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8b36-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="b8b36-112">Ciò significa che un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback non verrà generato per una funzione che rappresenta la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="b8b36-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="b8b36-113">Il valore dei `func` parametro non valido dopo il `FunctionTailcall2` funzione perché il valore potrebbe cambiare o essere distrutto.</span><span class="sxs-lookup"><span data-stu-id="b8b36-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="b8b36-114">Il `FunctionTailcall2` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="b8b36-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="b8b36-115">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b8b36-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b8b36-116">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b8b36-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="b8b36-117">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="b8b36-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="b8b36-118">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="b8b36-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b8b36-119">L'implementazione di `FunctionTailcall2` non devono bloccare perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b8b36-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b8b36-120">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="b8b36-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b8b36-121">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionTailcall2` restituisce.</span><span class="sxs-lookup"><span data-stu-id="b8b36-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="b8b36-122">Inoltre, il `FunctionTailcall2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="b8b36-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8b36-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8b36-123">Requirements</span></span>  
 <span data-ttu-id="b8b36-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8b36-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8b36-125">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b8b36-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b8b36-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8b36-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8b36-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b36-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b36-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8b36-128">See also</span></span>

- [<span data-ttu-id="b8b36-129">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="b8b36-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="b8b36-130">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="b8b36-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="b8b36-131">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="b8b36-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="b8b36-132">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b8b36-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
