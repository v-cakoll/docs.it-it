---
title: Funzione FunctionEnter
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: ad34592223433f0bf541c390674bcf96839b6ca8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440822"
---
# <a name="functionenter-function"></a><span data-ttu-id="c49fa-102">Funzione FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="c49fa-102">FunctionEnter Function</span></span>
<span data-ttu-id="c49fa-103">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="c49fa-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c49fa-104">La funzione `FunctionEnter` è deprecata nel .NET Framework versione 2,0 e il suo utilizzo comporterà una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c49fa-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="c49fa-105">Usare invece la funzione [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c49fa-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49fa-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c49fa-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c49fa-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c49fa-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="c49fa-108">in Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="c49fa-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c49fa-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c49fa-109">Remarks</span></span>  
 <span data-ttu-id="c49fa-110">La funzione `FunctionEnter` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="c49fa-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="c49fa-111">L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="c49fa-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="c49fa-112">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="c49fa-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="c49fa-113">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="c49fa-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="c49fa-114">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="c49fa-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c49fa-115">L'implementazione di `FunctionEnter` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c49fa-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="c49fa-116">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c49fa-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c49fa-117">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionEnter` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="c49fa-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="c49fa-118">Inoltre, la funzione `FunctionEnter` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.</span><span class="sxs-lookup"><span data-stu-id="c49fa-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c49fa-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c49fa-119">Requirements</span></span>  
 <span data-ttu-id="c49fa-120">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c49fa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c49fa-121">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="c49fa-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c49fa-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c49fa-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c49fa-123">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="c49fa-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49fa-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c49fa-124">See also</span></span>

- [<span data-ttu-id="c49fa-125">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="c49fa-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="c49fa-126">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="c49fa-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="c49fa-127">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="c49fa-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="c49fa-128">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="c49fa-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="c49fa-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="c49fa-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
