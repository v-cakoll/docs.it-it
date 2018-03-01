---
title: Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c460cfd24a83ca2a6c75e061b7a797c8f455bc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="22a48-102">Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="22a48-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="22a48-103">Specifica di funzioni implementate dal profiler venga chiamata per le versioni aggiornate del "Immettere", "lasciare" e "tailcall" hook delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="22a48-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22a48-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22a48-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22a48-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="22a48-106">[in] Un puntatore all'implementazione da usare come il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="22a48-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="22a48-107">[in] Un puntatore all'implementazione da usare come il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="22a48-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="22a48-108">[in] Un puntatore all'implementazione da usare come il [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="22a48-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a48-109">Note</span><span class="sxs-lookup"><span data-stu-id="22a48-109">Remarks</span></span>  
 <span data-ttu-id="22a48-110">Il `SetEnterLeaveFunctionHooks2` è simile al metodo di [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="22a48-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="22a48-111">Utilizzare il primo per specificare le funzioni da utilizzare come le versioni più recenti di invio lasciare/tali callback e quest'ultimo per specificare le funzioni da utilizzare come le versioni precedenti dell'invio lasciare/tali callback.</span><span class="sxs-lookup"><span data-stu-id="22a48-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="22a48-112">Un solo set di callback può essere attivo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="22a48-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="22a48-113">Pertanto, se un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` e `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="22a48-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="22a48-114">Il `SetEnterLeaveFunctionHooks2` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="22a48-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a48-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22a48-115">Requirements</span></span>  
 <span data-ttu-id="22a48-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a48-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a48-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22a48-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22a48-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22a48-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a48-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a48-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a48-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a48-120">See Also</span></span>  
 [<span data-ttu-id="22a48-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="22a48-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="22a48-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="22a48-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
