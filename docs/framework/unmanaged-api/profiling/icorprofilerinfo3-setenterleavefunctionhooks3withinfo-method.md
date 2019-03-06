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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 287f08c4ce5108ac9ae871135976cb45917fa861
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476711"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="e7d79-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e7d79-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="e7d79-103">Specifica le funzioni implementate dal profiler che verranno chiamate per il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hook di funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="e7d79-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7d79-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7d79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7d79-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="e7d79-106">[in] Un puntatore all'implementazione da usare come il `FunctionEnter3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="e7d79-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="e7d79-107">[in] Un puntatore all'implementazione da usare come il `FunctionLeave3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="e7d79-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="e7d79-108">[in] Un puntatore all'implementazione da usare come il `FunctionTailcall3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="e7d79-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7d79-109">Note</span><span class="sxs-lookup"><span data-stu-id="e7d79-109">Remarks</span></span>  
 <span data-ttu-id="e7d79-110">Il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) forniscono l'esame dello stack frame e argomento.</span><span class="sxs-lookup"><span data-stu-id="e7d79-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="e7d79-111">Per accedere a tali informazioni, il `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, e/o `COR_PRF_ENABLE_FRAME_INFO` devono i flag da impostare.</span><span class="sxs-lookup"><span data-stu-id="e7d79-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="e7d79-112">Il profiler può usare la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodo per impostare i flag dell'evento e quindi usare il `SetEnterLeaveFunctionHooks3WithInfo` metodo per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="e7d79-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e7d79-113">Un solo set di callback può essere attivo in un momento e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="e7d79-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="e7d79-114">Pertanto, se un profiler chiama entrambe [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) e `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` viene usato.</span><span class="sxs-lookup"><span data-stu-id="e7d79-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="e7d79-115">Il `SetEnterLeaveFunctionHooks3WithInfo` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="e7d79-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d79-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7d79-116">Requirements</span></span>  
 <span data-ttu-id="e7d79-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7d79-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d79-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7d79-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7d79-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7d79-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7d79-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7d79-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d79-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7d79-121">See also</span></span>
- [<span data-ttu-id="e7d79-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e7d79-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e7d79-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e7d79-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e7d79-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e7d79-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e7d79-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e7d79-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e7d79-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e7d79-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e7d79-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e7d79-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e7d79-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e7d79-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e7d79-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="e7d79-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="e7d79-130">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="e7d79-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="e7d79-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="e7d79-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e7d79-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="e7d79-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
