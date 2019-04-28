---
title: Funzione FunctionEnter3
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a731df84af0991f80c560db417df0ffe053a5e2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598935"
---
# <a name="functionenter3-function"></a><span data-ttu-id="136f1-102">Funzione FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="136f1-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="136f1-103">Notifica al profiler di controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="136f1-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="136f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="136f1-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="136f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="136f1-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="136f1-106">[in] L'identificatore della funzione a cui il controllo viene passato.</span><span class="sxs-lookup"><span data-stu-id="136f1-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="136f1-107">Note</span><span class="sxs-lookup"><span data-stu-id="136f1-107">Remarks</span></span>  
 <span data-ttu-id="136f1-108">Il `FunctionEnter3` funzione di callback di notifica al profiler le funzioni che vengono chiamate, ma viene non esame degli argomenti di supporto.</span><span class="sxs-lookup"><span data-stu-id="136f1-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="136f1-109">Usare la [metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="136f1-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="136f1-110">Il `FunctionEnter3` funzione è un callback, è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="136f1-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="136f1-111">L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="136f1-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="136f1-112">Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="136f1-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="136f1-113">In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="136f1-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="136f1-114">In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.</span><span class="sxs-lookup"><span data-stu-id="136f1-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="136f1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="136f1-115">Requirements</span></span>  
 <span data-ttu-id="136f1-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="136f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="136f1-117">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="136f1-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="136f1-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="136f1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="136f1-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="136f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136f1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="136f1-120">See also</span></span>

- [<span data-ttu-id="136f1-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="136f1-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="136f1-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="136f1-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="136f1-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="136f1-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="136f1-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="136f1-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="136f1-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="136f1-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="136f1-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="136f1-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="136f1-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="136f1-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="136f1-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="136f1-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="136f1-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="136f1-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="136f1-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="136f1-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
