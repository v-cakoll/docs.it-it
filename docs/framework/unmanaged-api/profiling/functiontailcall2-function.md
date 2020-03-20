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
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175187"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="0e55a-102">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="0e55a-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="0e55a-103">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="0e55a-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e55a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e55a-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e55a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e55a-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="0e55a-106">\[in] L'identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="0e55a-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="0e55a-107">\[in] L'identificatore di funzione rimappato, specificato in precedenza dal profiler tramite [FunctionIDMapper](functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="0e55a-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="0e55a-108">\[in] `COR_PRF_FRAME_INFO` Un valore che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="0e55a-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="0e55a-109">Il profiler deve considerare questo come un handle opaco che può essere passato al motore di esecuzione nel [metodo ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)</span><span class="sxs-lookup"><span data-stu-id="0e55a-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e55a-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0e55a-110">Remarks</span></span>  
 <span data-ttu-id="0e55a-111">La funzione di destinazione della chiamata tail utilizzerà lo stack frame corrente e tornerà direttamente al chiamante della funzione che ha effettuato la chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="0e55a-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="0e55a-112">Ciò significa che un callback [FunctionLeave2](functionleave2-function.md) non verrà generato per una funzione che è la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="0e55a-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="0e55a-113">Il valore `func` del parametro non `FunctionTailcall2` è valido dopo la restituzione della funzione perché il valore può cambiare o essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="0e55a-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="0e55a-114">La `FunctionTailcall2` funzione è un callback; è necessario implementarlo.</span><span class="sxs-lookup"><span data-stu-id="0e55a-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="0e55a-115">L'implementazione `__declspec`deve`naked`utilizzare l'attributo della classe di archiviazione ( ).</span><span class="sxs-lookup"><span data-stu-id="0e55a-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="0e55a-116">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="0e55a-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="0e55a-117">All'ingresso, è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="0e55a-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="0e55a-118">All'uscita, è necessario ripristinare lo stack rimuovendo tutti i parametri inseriti dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="0e55a-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0e55a-119">L'implementazione di non deve bloccarsi perché ritarderà la procedura di `FunctionTailcall2` Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0e55a-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="0e55a-120">L'implementazione non deve tentare un'operazione di Garbage Collection perché lo stack potrebbe non essere in uno stato compatibile con garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0e55a-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0e55a-121">Se viene tentata un'operazione `FunctionTailcall2` di Garbage Collection, il runtime si bloccherà fino a quando non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="0e55a-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="0e55a-122">Inoltre, `FunctionTailcall2` la funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="0e55a-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e55a-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e55a-123">Requirements</span></span>  
 <span data-ttu-id="0e55a-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e55a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e55a-125">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0e55a-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0e55a-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e55a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e55a-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e55a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e55a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e55a-128">See also</span></span>

- [<span data-ttu-id="0e55a-129">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="0e55a-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="0e55a-130">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="0e55a-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="0e55a-131">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="0e55a-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="0e55a-132">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="0e55a-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
