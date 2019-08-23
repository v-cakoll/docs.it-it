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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 354736890a4b042a8da5e747a0ab6ea3777e398e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952895"
---
# <a name="functionenter-function"></a><span data-ttu-id="19c6c-102">Funzione FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="19c6c-102">FunctionEnter Function</span></span>
<span data-ttu-id="19c6c-103">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="19c6c-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19c6c-104">La `FunctionEnter` funzione è deprecata nel .NET Framework versione 2,0 e il suo utilizzo comporterà una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="19c6c-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="19c6c-105">Usare invece la funzione [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="19c6c-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c6c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19c6c-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19c6c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="19c6c-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="19c6c-108">in Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="19c6c-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19c6c-109">Note</span><span class="sxs-lookup"><span data-stu-id="19c6c-109">Remarks</span></span>  
 <span data-ttu-id="19c6c-110">La `FunctionEnter` funzione è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="19c6c-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="19c6c-111">L'implementazione deve usare l' `__declspec`attributo`naked`della classe di archiviazione ().</span><span class="sxs-lookup"><span data-stu-id="19c6c-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="19c6c-112">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="19c6c-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="19c6c-113">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="19c6c-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="19c6c-114">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="19c6c-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="19c6c-115">L'implementazione di `FunctionEnter` non deve essere bloccata perché ritarderà Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="19c6c-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="19c6c-116">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="19c6c-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="19c6c-117">Se viene effettuato un tentativo di Garbage Collection, il runtime si `FunctionEnter` bloccherà fino a quando non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="19c6c-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="19c6c-118">Inoltre, la `FunctionEnter` funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione managed memory.</span><span class="sxs-lookup"><span data-stu-id="19c6c-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c6c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19c6c-119">Requirements</span></span>  
 <span data-ttu-id="19c6c-120">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c6c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c6c-121">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="19c6c-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="19c6c-122">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19c6c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19c6c-123">**Versioni .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="19c6c-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c6c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c6c-124">See also</span></span>

- [<span data-ttu-id="19c6c-125">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="19c6c-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="19c6c-126">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="19c6c-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="19c6c-127">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="19c6c-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="19c6c-128">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="19c6c-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="19c6c-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="19c6c-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
