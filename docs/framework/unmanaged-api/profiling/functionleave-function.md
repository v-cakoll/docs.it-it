---
title: Funzione FunctionLeave
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave
helpviewer_keywords: FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14b8c1c5d36178e672bee363a192cd4eae435467
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave-function"></a><span data-ttu-id="e8032-102">Funzione FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="e8032-102">FunctionLeave Function</span></span>
<span data-ttu-id="e8032-103">Notifica al profiler che una funzione sta per restituire al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e8032-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8032-104">Il `FunctionLeave` funzione è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e8032-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="e8032-105">Continuerà a funzionare, ma comporta una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8032-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="e8032-106">Utilizzare il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) funzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="e8032-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8032-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8032-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8032-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8032-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="e8032-109">[in] Identificatore della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="e8032-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8032-110">Note</span><span class="sxs-lookup"><span data-stu-id="e8032-110">Remarks</span></span>  
 <span data-ttu-id="e8032-111">Il `FunctionLeave` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="e8032-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="e8032-112">L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8032-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e8032-113">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e8032-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="e8032-114">In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="e8032-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="e8032-115">All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="e8032-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e8032-116">L'implementazione di `FunctionLeave` non devono bloccarsi perché ritarderà l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e8032-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e8032-117">L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage.</span><span class="sxs-lookup"><span data-stu-id="e8032-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e8032-118">Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionLeave` restituisce.</span><span class="sxs-lookup"><span data-stu-id="e8032-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="e8032-119">Inoltre, il `FunctionLeave` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="e8032-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8032-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8032-120">Requirements</span></span>  
 <span data-ttu-id="e8032-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8032-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8032-122">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e8032-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e8032-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8032-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8032-124">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e8032-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8032-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8032-125">See Also</span></span>  
 [<span data-ttu-id="e8032-126">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="e8032-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="e8032-127">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="e8032-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="e8032-128">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="e8032-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="e8032-129">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="e8032-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="e8032-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="e8032-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
