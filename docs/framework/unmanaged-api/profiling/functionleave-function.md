---
title: Funzione FunctionLeave
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2614ad988496a22f0e6234c2f3300e22ef548308
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452442"
---
# <a name="functionleave-function"></a><span data-ttu-id="fa34c-102">Funzione FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="fa34c-102">FunctionLeave Function</span></span>
<span data-ttu-id="fa34c-103">Notifica al profiler che una funzione sta per restituire al chiamante.</span><span class="sxs-lookup"><span data-stu-id="fa34c-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa34c-104">Il `FunctionLeave` funzione è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa34c-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="fa34c-105">Continuerà a funzionare, ma comporta una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fa34c-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="fa34c-106">Utilizzare il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) funzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="fa34c-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa34c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa34c-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa34c-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa34c-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="fa34c-109">[in] Identificatore della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="fa34c-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa34c-110">Note</span><span class="sxs-lookup"><span data-stu-id="fa34c-110">Remarks</span></span>  
 <span data-ttu-id="fa34c-111">Il `FunctionLeave` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="fa34c-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="fa34c-112">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fa34c-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="fa34c-113">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="fa34c-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="fa34c-114">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="fa34c-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="fa34c-115">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="fa34c-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="fa34c-116">L'implementazione di `FunctionLeave` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="fa34c-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="fa34c-117">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="fa34c-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="fa34c-118">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionLeave` restituisce.</span><span class="sxs-lookup"><span data-stu-id="fa34c-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="fa34c-119">Inoltre, il `FunctionLeave` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="fa34c-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa34c-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa34c-120">Requirements</span></span>  
 <span data-ttu-id="fa34c-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa34c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa34c-122">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="fa34c-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fa34c-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fa34c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa34c-124">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="fa34c-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa34c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa34c-125">See Also</span></span>  
 [<span data-ttu-id="fa34c-126">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="fa34c-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="fa34c-127">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="fa34c-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="fa34c-128">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="fa34c-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="fa34c-129">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="fa34c-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="fa34c-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="fa34c-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
