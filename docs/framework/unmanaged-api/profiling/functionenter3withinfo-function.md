---
title: Funzione FunctionEnter3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: ff4b32185e604611eaaead2847c11bc139d405a6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500689"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="0129a-102">Funzione FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0129a-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="0129a-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare il stack frame e gli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="0129a-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0129a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0129a-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0129a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0129a-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="0129a-106">\[in] identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="0129a-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="0129a-107">\[in] handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="0129a-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="0129a-108">Questo handle è valido solo durante il callback a cui viene passato.</span><span class="sxs-lookup"><span data-stu-id="0129a-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="0129a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0129a-109">Remarks</span></span>  
 <span data-ttu-id="0129a-110">Il `FunctionEnter3WithInfo` metodo di callback invia una notifica al profiler quando vengono chiamate le funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per esaminare i valori degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="0129a-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="0129a-111">Per accedere alle informazioni sugli argomenti, `COR_PRF_ENABLE_FUNCTION_ARGS` è necessario impostare il flag.</span><span class="sxs-lookup"><span data-stu-id="0129a-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="0129a-112">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="0129a-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="0129a-113">La `FunctionEnter3WithInfo` funzione è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="0129a-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="0129a-114">L'implementazione deve usare l' `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0129a-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="0129a-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="0129a-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="0129a-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="0129a-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="0129a-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="0129a-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0129a-118">L'implementazione di `FunctionEnter3WithInfo` non deve essere bloccata, perché ritarderà Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0129a-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="0129a-119">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0129a-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0129a-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando non viene `FunctionEnter3WithInfo` restituito.</span><span class="sxs-lookup"><span data-stu-id="0129a-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="0129a-121">La `FunctionEnter3WithInfo` funzione non deve chiamare nel codice gestito o causare un managed memory allocazione in qualsiasi modo.</span><span class="sxs-lookup"><span data-stu-id="0129a-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0129a-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0129a-122">Requirements</span></span>  
 <span data-ttu-id="0129a-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0129a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0129a-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="0129a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0129a-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0129a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0129a-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0129a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0129a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0129a-127">See also</span></span>

- [<span data-ttu-id="0129a-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="0129a-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="0129a-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="0129a-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="0129a-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="0129a-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="0129a-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="0129a-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
