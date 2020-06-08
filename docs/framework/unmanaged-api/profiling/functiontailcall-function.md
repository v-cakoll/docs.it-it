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
ms.openlocfilehash: 42ea497bdcab71518bec08514b827d76f0317d57
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500598"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="2dcb3-102">Funzione FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="2dcb3-102">FunctionTailcall Function</span></span>
<span data-ttu-id="2dcb3-103">Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2dcb3-104">La `FunctionTailcall` funzione è deprecata nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2dcb3-105">Continuerà a funzionare, ma comporterà una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="2dcb3-106">Usare invece la funzione [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2dcb3-106">Use the [FunctionTailcall2](functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dcb3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2dcb3-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dcb3-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="2dcb3-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="2dcb3-109">\[in] identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-109">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="2dcb3-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2dcb3-110">Remarks</span></span>  
 <span data-ttu-id="2dcb3-111">La funzione di destinazione della chiamata tail utilizzerà l'stack frame corrente e tornerà direttamente al chiamante della funzione che ha eseguito la chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="2dcb3-112">Ciò significa che non verrà emesso un callback [FunctionLeave](functionleave-function.md) per una funzione che è la destinazione di una chiamata tail.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-112">This means that a [FunctionLeave](functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="2dcb3-113">La `FunctionTailcall` funzione è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="2dcb3-114">L'implementazione deve usare l' `__declspec` `naked` attributo della classe di archiviazione ().</span><span class="sxs-lookup"><span data-stu-id="2dcb3-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2dcb3-115">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="2dcb3-116">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="2dcb3-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="2dcb3-117">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2dcb3-118">L'implementazione di `FunctionTailcall` non deve essere bloccata perché ritarderà Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2dcb3-119">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2dcb3-120">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando non viene `FunctionTailcall` restituito.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="2dcb3-121">Inoltre, la `FunctionTailcall` funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione managed memory.</span><span class="sxs-lookup"><span data-stu-id="2dcb3-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dcb3-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2dcb3-122">Requirements</span></span>  
 <span data-ttu-id="2dcb3-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dcb3-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dcb3-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="2dcb3-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2dcb3-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dcb3-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dcb3-126">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="2dcb3-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dcb3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dcb3-127">See also</span></span>

- [<span data-ttu-id="2dcb3-128">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="2dcb3-128">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="2dcb3-129">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="2dcb3-129">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="2dcb3-130">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="2dcb3-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2dcb3-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="2dcb3-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
