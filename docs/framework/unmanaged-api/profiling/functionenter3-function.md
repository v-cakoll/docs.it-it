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
ms.openlocfilehash: b435e1a3504dd623421f977ffc48264f8b0dcb5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500702"
---
# <a name="functionenter3-function"></a><span data-ttu-id="b986e-102">Funzione FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b986e-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="b986e-103">Notifica al profiler che il controllo viene passato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="b986e-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b986e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b986e-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b986e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b986e-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="b986e-106">\[in] identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="b986e-106">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b986e-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b986e-107">Remarks</span></span>  
 <span data-ttu-id="b986e-108">La `FunctionEnter3` funzione di callback invia una notifica al profiler mentre le funzioni vengono chiamate, ma non supporta l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b986e-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="b986e-109">Usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b986e-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b986e-110">La `FunctionEnter3` funzione è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="b986e-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="b986e-111">L'implementazione deve usare l' `__declspec(naked)` attributo della classe di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b986e-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b986e-112">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b986e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b986e-113">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="b986e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b986e-114">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="b986e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b986e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b986e-115">Requirements</span></span>  
 <span data-ttu-id="b986e-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b986e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b986e-117">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="b986e-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b986e-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b986e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b986e-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b986e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b986e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b986e-120">See also</span></span>

- [<span data-ttu-id="b986e-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b986e-121">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="b986e-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b986e-122">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="b986e-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b986e-123">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="b986e-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b986e-124">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="b986e-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b986e-125">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b986e-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b986e-126">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="b986e-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b986e-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b986e-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b986e-128">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="b986e-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="b986e-129">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="b986e-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b986e-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
