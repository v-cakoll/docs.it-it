---
title: Funzione FunctionLeave2
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: 0b1ecd1266528f8a08ef114de2f111dd0f71ca8b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866931"
---
# <a name="functionleave2-function"></a><span data-ttu-id="e999f-102">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="e999f-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="e999f-103">Notifica al profiler che una funzione sta per tornare al chiamante e fornisce informazioni sull'stack frame e sul valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="e999f-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e999f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e999f-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e999f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e999f-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="e999f-106">\[in] identificatore della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="e999f-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="e999f-107">\[in] identificatore della funzione di cui è stato eseguito il mapping, specificato in precedenza dal profiler tramite la funzione [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e999f-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="e999f-108">\[in] valore `COR_PRF_FRAME_INFO` che punta alle informazioni relative al stack frame.</span><span class="sxs-lookup"><span data-stu-id="e999f-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="e999f-109">Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e999f-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="e999f-110">\[in] puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) che specifica la posizione di memoria del valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="e999f-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="e999f-111">Per accedere alle informazioni sul valore restituito, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="e999f-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="e999f-112">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.</span><span class="sxs-lookup"><span data-stu-id="e999f-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="e999f-113">Note</span><span class="sxs-lookup"><span data-stu-id="e999f-113">Remarks</span></span>  
 <span data-ttu-id="e999f-114">I valori dei parametri `func` e `retvalRange` non sono validi dopo che la funzione `FunctionLeave2` restituisce il risultato perché i valori possono essere modificati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="e999f-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="e999f-115">La funzione `FunctionLeave2` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="e999f-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="e999f-116">L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="e999f-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e999f-117">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e999f-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e999f-118">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="e999f-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e999f-119">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="e999f-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e999f-120">L'implementazione di `FunctionLeave2` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e999f-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e999f-121">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e999f-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e999f-122">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionLeave2` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="e999f-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="e999f-123">Inoltre, la funzione `FunctionLeave2` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.</span><span class="sxs-lookup"><span data-stu-id="e999f-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e999f-124">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e999f-124">Requirements</span></span>  
 <span data-ttu-id="e999f-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e999f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e999f-126">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="e999f-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e999f-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e999f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e999f-128">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e999f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e999f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e999f-129">See also</span></span>

- [<span data-ttu-id="e999f-130">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="e999f-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="e999f-131">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="e999f-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="e999f-132">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="e999f-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="e999f-133">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="e999f-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
