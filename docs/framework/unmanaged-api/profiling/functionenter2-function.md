---
title: Funzione FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177059"
---
# <a name="functionenter2-function"></a><span data-ttu-id="dc364-102">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="dc364-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="dc364-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli argomenti dello stack frame e della funzione.</span><span class="sxs-lookup"><span data-stu-id="dc364-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="dc364-104">Questa funzione sostituisce la funzione [FunctionEnter.](functionenter-function.md)</span><span class="sxs-lookup"><span data-stu-id="dc364-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc364-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc364-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc364-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc364-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="dc364-107">\[in] Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="dc364-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="dc364-108">\[in] L'identificatore di funzione rimappato, che il profiler ha specificato in precedenza utilizzando la funzione [FunctionIDMapper.](functionidmapper-function.md)</span><span class="sxs-lookup"><span data-stu-id="dc364-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="dc364-109">\[in] `COR_PRF_FRAME_INFO` Un valore che punta alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="dc364-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="dc364-110">Il profiler deve considerare questo come un handle opaco che può essere passato al motore di esecuzione nel [metodo ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)</span><span class="sxs-lookup"><span data-stu-id="dc364-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="dc364-111">\[in] Un puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) che specifica le posizioni in memoria degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="dc364-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="dc364-112">Per accedere alle informazioni `COR_PRF_ENABLE_FUNCTION_ARGS` sugli argomenti, è necessario impostare il flag.</span><span class="sxs-lookup"><span data-stu-id="dc364-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="dc364-113">Il profiler può utilizzare il metodo [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.</span><span class="sxs-lookup"><span data-stu-id="dc364-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc364-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc364-114">Remarks</span></span>  
 <span data-ttu-id="dc364-115">I valori `func` dei `argumentInfo` parametri e non `FunctionEnter2` sono validi dopo la restituzione della funzione perché i valori possono cambiare o essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="dc364-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="dc364-116">La `FunctionEnter2` funzione è un callback; è necessario implementarlo.</span><span class="sxs-lookup"><span data-stu-id="dc364-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="dc364-117">L'implementazione `__declspec`deve`naked`utilizzare l'attributo della classe di archiviazione ( ).</span><span class="sxs-lookup"><span data-stu-id="dc364-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="dc364-118">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="dc364-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="dc364-119">All'ingresso, è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="dc364-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="dc364-120">All'uscita, è necessario ripristinare lo stack rimuovendo tutti i parametri inseriti dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="dc364-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="dc364-121">L'implementazione di non deve bloccarsi perché ritarderà la procedura di `FunctionEnter2` Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dc364-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="dc364-122">L'implementazione non deve tentare un'operazione di Garbage Collection perché lo stack potrebbe non essere in uno stato compatibile con garbage collection.</span><span class="sxs-lookup"><span data-stu-id="dc364-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="dc364-123">Se viene tentata un'operazione `FunctionEnter2` di Garbage Collection, il runtime si bloccherà fino a quando non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="dc364-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="dc364-124">Inoltre, `FunctionEnter2` la funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="dc364-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc364-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc364-125">Requirements</span></span>  
 <span data-ttu-id="dc364-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc364-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc364-127">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="dc364-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="dc364-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc364-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc364-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc364-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc364-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc364-130">See also</span></span>

- [<span data-ttu-id="dc364-131">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="dc364-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="dc364-132">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="dc364-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="dc364-133">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="dc364-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="dc364-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="dc364-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
