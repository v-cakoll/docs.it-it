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
ms.openlocfilehash: 32d86f19e9c50694c7d113195e6967645b710666
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866869"
---
# <a name="functionleave3-function"></a><span data-ttu-id="b6d95-102">Funzione FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b6d95-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="b6d95-103">Notifica al profiler che il controllo viene restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="b6d95-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6d95-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6d95-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="b6d95-106">\[in] identificatore della funzione da cui viene restituito il controllo.</span><span class="sxs-lookup"><span data-stu-id="b6d95-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b6d95-107">Note</span><span class="sxs-lookup"><span data-stu-id="b6d95-107">Remarks</span></span>  
 <span data-ttu-id="b6d95-108">La funzione di callback `FunctionLeave3` notifica al profiler che le funzioni vengono chiamate, ma non supporta l'ispezione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="b6d95-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="b6d95-109">Usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b6d95-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b6d95-110">La funzione `FunctionLeave3` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="b6d95-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="b6d95-111">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b6d95-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b6d95-112">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b6d95-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b6d95-113">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="b6d95-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b6d95-114">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b6d95-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b6d95-115">L'implementazione di `FunctionLeave3` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6d95-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="b6d95-116">L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6d95-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b6d95-117">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionLeave3` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="b6d95-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="b6d95-118">La funzione `FunctionLeave3` non deve chiamare codice gestito o causare un'allocazione di managed memory in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="b6d95-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d95-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b6d95-119">Requirements</span></span>  
 <span data-ttu-id="b6d95-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d95-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d95-121">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="b6d95-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b6d95-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6d95-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6d95-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d95-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d95-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6d95-124">See also</span></span>

- [<span data-ttu-id="b6d95-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b6d95-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="b6d95-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b6d95-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="b6d95-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b6d95-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="b6d95-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b6d95-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="b6d95-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b6d95-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b6d95-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b6d95-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="b6d95-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b6d95-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b6d95-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b6d95-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="b6d95-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="b6d95-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="b6d95-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b6d95-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
