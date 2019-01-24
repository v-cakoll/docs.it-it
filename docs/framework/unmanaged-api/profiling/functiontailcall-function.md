---
title: Funzione FunctionTailcall
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a38d4858d248ef4eefbcb9d97c13e68d9507fb12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665032"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="d6e90-102">Funzione FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="d6e90-102">FunctionTailcall Function</span></span>
<span data-ttu-id="d6e90-103">Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail ad un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="d6e90-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6e90-104">Il `FunctionTailcall` funzione è obsoleta in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="d6e90-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d6e90-105">Continuerà a funzionare, ma comporta una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d6e90-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="d6e90-106">Usare la [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="d6e90-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e90-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6e90-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6e90-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6e90-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="d6e90-109">[in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="d6e90-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e90-110">Note</span><span class="sxs-lookup"><span data-stu-id="d6e90-110">Remarks</span></span>  
 <span data-ttu-id="d6e90-111">La funzione di destinazione della chiamata tail verrà utilizzato lo stack frame corrente e restituirà direttamente al chiamante della funzione che ha effettuato la parte finale di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d6e90-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="d6e90-112">Ciò significa che un [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback non verrà generato per una funzione che rappresenta la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="d6e90-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="d6e90-113">Il `FunctionTailcall` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="d6e90-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="d6e90-114">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d6e90-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d6e90-115">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="d6e90-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="d6e90-116">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="d6e90-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="d6e90-117">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6e90-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d6e90-118">L'implementazione di `FunctionTailcall` non devono bloccare perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d6e90-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d6e90-119">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di garbage collection adatto.</span><span class="sxs-lookup"><span data-stu-id="d6e90-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d6e90-120">Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionTailcall` restituisce.</span><span class="sxs-lookup"><span data-stu-id="d6e90-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="d6e90-121">Inoltre, il `FunctionTailcall` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="d6e90-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e90-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6e90-122">Requirements</span></span>  
 <span data-ttu-id="d6e90-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6e90-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e90-124">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d6e90-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d6e90-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e90-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e90-126">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="d6e90-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e90-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6e90-127">See also</span></span>
- [<span data-ttu-id="d6e90-128">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="d6e90-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d6e90-129">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="d6e90-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d6e90-130">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="d6e90-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d6e90-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="d6e90-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
