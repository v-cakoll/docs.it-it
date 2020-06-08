---
title: Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: eb658d682ce589b7dfdcfc0228d0c657310e6f7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496233"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="6158e-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="6158e-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="6158e-103">Specifica le funzioni implementate dal profiler che verranno chiamate nelle funzioni [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="6158e-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6158e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6158e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6158e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6158e-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="6158e-106">in Puntatore all'implementazione da utilizzare come `FunctionEnter3` callback.</span><span class="sxs-lookup"><span data-stu-id="6158e-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="6158e-107">in Puntatore all'implementazione da utilizzare come `FunctionLeave3` callback.</span><span class="sxs-lookup"><span data-stu-id="6158e-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="6158e-108">in Puntatore all'implementazione da utilizzare come `FunctionTailcall3` callback.</span><span class="sxs-lookup"><span data-stu-id="6158e-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6158e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6158e-109">Remarks</span></span>  
 <span data-ttu-id="6158e-110">Gli hook [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md) non forniscono stack frame e l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="6158e-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="6158e-111">Per accedere a tali informazioni, `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` è necessario impostare i flag, e/o `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="6158e-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="6158e-112">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il metodo [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="6158e-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6158e-113">Solo un set di callback può essere attivo alla volta e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="6158e-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="6158e-114">Se pertanto un profiler chiama sia il [metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) che il `SetEnterLeaveFunctionHooks3` metodo, `SetEnterLeaveFunctionHooks3` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6158e-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="6158e-115">Il `SetEnterLeaveFunctionHooks3` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="6158e-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6158e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6158e-116">Requirements</span></span>  
 <span data-ttu-id="6158e-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6158e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6158e-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6158e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6158e-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6158e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6158e-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6158e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6158e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6158e-121">See also</span></span>

- [<span data-ttu-id="6158e-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6158e-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="6158e-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6158e-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="6158e-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6158e-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="6158e-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="6158e-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="6158e-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6158e-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="6158e-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6158e-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="6158e-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6158e-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="6158e-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="6158e-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="6158e-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="6158e-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="6158e-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6158e-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6158e-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="6158e-132">Profiling</span></span>](index.md)
