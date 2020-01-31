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
ms.openlocfilehash: 2d99c6d8bd2af02456c6a90143b524c337483868
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866895"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="62208-102">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="62208-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="62208-103">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sul stack frame.</span><span class="sxs-lookup"><span data-stu-id="62208-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62208-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62208-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62208-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62208-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="62208-106">\[in] identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="62208-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="62208-107">\[in] identificatore della funzione di cui è stato eseguito il mapping, che il profiler ha specificato in precedenza tramite [FunctionIDMapper](functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="62208-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="62208-108">\[in] valore `COR_PRF_FRAME_INFO` che punta alle informazioni relative al stack frame.</span><span class="sxs-lookup"><span data-stu-id="62208-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="62208-109">Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="62208-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="62208-110">Note</span><span class="sxs-lookup"><span data-stu-id="62208-110">Remarks</span></span>  
 <span data-ttu-id="62208-111">La funzione di destinazione della chiamata tail utilizzerà l'stack frame corrente e tornerà direttamente al chiamante della funzione che ha eseguito la chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="62208-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="62208-112">Ciò significa che non verrà emesso un callback [FunctionLeave2](functionleave2-function.md) per una funzione che è la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="62208-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="62208-113">Il valore del parametro `func` non è valido dopo la restituzione della funzione `FunctionTailcall2` perché il valore può cambiare o essere eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="62208-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="62208-114">La funzione `FunctionTailcall2` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="62208-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="62208-115">L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="62208-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="62208-116">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="62208-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="62208-117">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="62208-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="62208-118">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="62208-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="62208-119">L'implementazione di `FunctionTailcall2` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="62208-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="62208-120">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="62208-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="62208-121">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionTailcall2` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="62208-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="62208-122">Inoltre, la funzione `FunctionTailcall2` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.</span><span class="sxs-lookup"><span data-stu-id="62208-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62208-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="62208-123">Requirements</span></span>  
 <span data-ttu-id="62208-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62208-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62208-125">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="62208-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="62208-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62208-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62208-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62208-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62208-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62208-128">See also</span></span>

- [<span data-ttu-id="62208-129">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="62208-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="62208-130">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="62208-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="62208-131">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="62208-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="62208-132">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="62208-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
