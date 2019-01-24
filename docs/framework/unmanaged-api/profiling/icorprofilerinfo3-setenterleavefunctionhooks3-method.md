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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc39250021c4f70535eac9653299bd0cb98d5e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680962"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="b61b7-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b61b7-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="b61b7-103">Specifica le funzioni implementate dal profiler che verranno chiamate per il [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), e [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) funzioni.</span><span class="sxs-lookup"><span data-stu-id="b61b7-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b61b7-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b61b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b61b7-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="b61b7-106">[in] Un puntatore all'implementazione da usare come il `FunctionEnter3` callback.</span><span class="sxs-lookup"><span data-stu-id="b61b7-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="b61b7-107">[in] Un puntatore all'implementazione da usare come il `FunctionLeave3` callback.</span><span class="sxs-lookup"><span data-stu-id="b61b7-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="b61b7-108">[in] Un puntatore all'implementazione da usare come il `FunctionTailcall3` callback.</span><span class="sxs-lookup"><span data-stu-id="b61b7-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b61b7-109">Note</span><span class="sxs-lookup"><span data-stu-id="b61b7-109">Remarks</span></span>  
 <span data-ttu-id="b61b7-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), e [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) non forniscono ispezione di stack frame e argomento.</span><span class="sxs-lookup"><span data-stu-id="b61b7-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="b61b7-111">Per accedere a tali informazioni, il `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, e/o `COR_PRF_ENABLE_FRAME_INFO` devono i flag da impostare.</span><span class="sxs-lookup"><span data-stu-id="b61b7-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="b61b7-112">Il profiler può usare il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodo per impostare i flag dell'evento e quindi utilizzare il [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) metodo per registrare il implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b61b7-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b61b7-113">Un solo set di callback può essere attivo in un momento e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="b61b7-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="b61b7-114">Di conseguenza, se un profiler chiama sia la [metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) e il `SetEnterLeaveFunctionHooks3` metodo, `SetEnterLeaveFunctionHooks3` viene usato.</span><span class="sxs-lookup"><span data-stu-id="b61b7-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="b61b7-115">Il `SetEnterLeaveFunctionHooks3` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="b61b7-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b61b7-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b61b7-116">Requirements</span></span>  
 <span data-ttu-id="b61b7-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b61b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b61b7-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b61b7-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b61b7-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b61b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b61b7-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b61b7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61b7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b61b7-121">See also</span></span>
- [<span data-ttu-id="b61b7-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b61b7-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b61b7-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b61b7-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="b61b7-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b61b7-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="b61b7-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b61b7-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="b61b7-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b61b7-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="b61b7-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b61b7-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="b61b7-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b61b7-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b61b7-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b61b7-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="b61b7-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b61b7-130">ICorProfilerInfo3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b61b7-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b61b7-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b61b7-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="b61b7-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
