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
ms.openlocfilehash: fd224279b3df6c9e8e55cd81ebfbf2e5ea2428d5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440774"
---
# <a name="functionenter3-function"></a><span data-ttu-id="1d157-102">Funzione FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="1d157-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="1d157-103">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="1d157-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d157-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d157-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d157-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d157-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="1d157-106">in Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="1d157-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d157-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1d157-107">Remarks</span></span>  
 <span data-ttu-id="1d157-108">La funzione di callback `FunctionEnter3` notifica al profiler che le funzioni vengono chiamate, ma non supporta l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="1d157-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="1d157-109">Usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="1d157-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="1d157-110">La funzione `FunctionEnter3` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="1d157-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="1d157-111">L'implementazione deve usare l'`__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1d157-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="1d157-112">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="1d157-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="1d157-113">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="1d157-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="1d157-114">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="1d157-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d157-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d157-115">Requirements</span></span>  
 <span data-ttu-id="1d157-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d157-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d157-117">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="1d157-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1d157-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d157-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d157-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d157-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d157-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d157-120">See also</span></span>

- [<span data-ttu-id="1d157-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="1d157-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="1d157-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="1d157-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="1d157-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1d157-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="1d157-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1d157-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="1d157-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1d157-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="1d157-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="1d157-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="1d157-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1d157-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="1d157-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="1d157-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="1d157-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="1d157-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="1d157-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="1d157-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
