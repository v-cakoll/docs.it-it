---
title: Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: b17ab9382e5195881e5629d482e4327fc67562f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449599"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="499d4-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="499d4-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="499d4-103">Specifica le funzioni implementate dal profiler che verranno chiamate sugli hook [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="499d4-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="499d4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="499d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="499d4-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="499d4-106">in Puntatore all'implementazione da utilizzare come callback `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="499d4-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="499d4-107">in Puntatore all'implementazione da utilizzare come callback `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="499d4-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="499d4-108">in Puntatore all'implementazione da utilizzare come callback `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="499d4-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="499d4-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="499d4-109">Remarks</span></span>  
 <span data-ttu-id="499d4-110">Gli hook [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) forniscono stack frame e l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="499d4-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="499d4-111">Per accedere a tali informazioni, è necessario impostare i flag `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`e/o `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="499d4-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="499d4-112">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il metodo `SetEnterLeaveFunctionHooks3WithInfo` per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="499d4-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="499d4-113">Solo un set di callback può essere attivo alla volta e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="499d4-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="499d4-114">Se pertanto un profiler chiama sia [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) che `SetEnterLeaveFunctionHooks3WithInfo`, viene utilizzato `SetEnterLeaveFunctionHooks3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="499d4-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="499d4-115">Il metodo `SetEnterLeaveFunctionHooks3WithInfo` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="499d4-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499d4-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="499d4-116">Requirements</span></span>  
 <span data-ttu-id="499d4-117">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499d4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499d4-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="499d4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="499d4-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="499d4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="499d4-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499d4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499d4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="499d4-121">See also</span></span>

- [<span data-ttu-id="499d4-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="499d4-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="499d4-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="499d4-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="499d4-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="499d4-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="499d4-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="499d4-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="499d4-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="499d4-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="499d4-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="499d4-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="499d4-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="499d4-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="499d4-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="499d4-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="499d4-130">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="499d4-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="499d4-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="499d4-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="499d4-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="499d4-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
