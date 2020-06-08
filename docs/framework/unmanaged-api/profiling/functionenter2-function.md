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
ms.openlocfilehash: 8c88e97f8187ac347f4ff39890c8d87ee80c8f9e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500715"
---
# <a name="functionenter2-function"></a><span data-ttu-id="9fd0c-102">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="9fd0c-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="9fd0c-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli stack frame e sugli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="9fd0c-104">Questa funzione sostituisce la funzione [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd0c-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd0c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fd0c-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fd0c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fd0c-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="9fd0c-107">\[in] identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="9fd0c-108">\[in] identificatore della funzione di cui è stato eseguito il mapping, specificato in precedenza dal profiler tramite la funzione [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd0c-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="9fd0c-109">\[in] `COR_PRF_FRAME_INFO` valore che punta alle informazioni relative all'stack frame.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="9fd0c-110">Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd0c-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="9fd0c-111">\[in] puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) che specifica le posizioni in memoria degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="9fd0c-112">Per accedere alle informazioni sugli argomenti, `COR_PRF_ENABLE_FUNCTION_ARGS` è necessario impostare il flag.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="9fd0c-113">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fd0c-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9fd0c-114">Remarks</span></span>  
 <span data-ttu-id="9fd0c-115">I valori dei `func` parametri e `argumentInfo` non sono validi dopo la `FunctionEnter2` restituzione della funzione perché i valori possono essere modificati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="9fd0c-116">La `FunctionEnter2` funzione è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="9fd0c-117">L'implementazione deve usare l' `__declspec` `naked` attributo della classe di archiviazione ().</span><span class="sxs-lookup"><span data-stu-id="9fd0c-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="9fd0c-118">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="9fd0c-119">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="9fd0c-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="9fd0c-120">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="9fd0c-121">L'implementazione di `FunctionEnter2` non deve essere bloccata perché ritarderà Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="9fd0c-122">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="9fd0c-123">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando non viene `FunctionEnter2` restituito.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="9fd0c-124">Inoltre, la `FunctionEnter2` funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione managed memory.</span><span class="sxs-lookup"><span data-stu-id="9fd0c-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fd0c-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fd0c-125">Requirements</span></span>  
 <span data-ttu-id="9fd0c-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fd0c-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fd0c-127">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="9fd0c-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9fd0c-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fd0c-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fd0c-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fd0c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd0c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fd0c-130">See also</span></span>

- [<span data-ttu-id="9fd0c-131">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="9fd0c-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="9fd0c-132">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="9fd0c-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="9fd0c-133">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="9fd0c-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="9fd0c-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="9fd0c-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
