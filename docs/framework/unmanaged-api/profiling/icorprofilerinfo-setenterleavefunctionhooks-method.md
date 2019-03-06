---
title: Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 542ccf384a9b6576e5bce8be1ce9a3dc44c2c71d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473828"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="20c86-102">Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="20c86-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="20c86-103">Specifica funzioni implementate dal profiler verrà chiamato su "Immettere", "Continua" e "tailcall" hook di funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="20c86-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20c86-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20c86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20c86-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="20c86-106">[in] Un puntatore all'implementazione da usare come le [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="20c86-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="20c86-107">[in] Un puntatore all'implementazione da usare come le [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="20c86-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="20c86-108">[in] Un puntatore all'implementazione da usare come le [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span><span class="sxs-lookup"><span data-stu-id="20c86-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20c86-109">Note</span><span class="sxs-lookup"><span data-stu-id="20c86-109">Remarks</span></span>  
 <span data-ttu-id="20c86-110">In .NET Framework versione 1.0, ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.</span><span class="sxs-lookup"><span data-stu-id="20c86-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="20c86-111">Un solo set di callback può essere attivo alla volta.</span><span class="sxs-lookup"><span data-stu-id="20c86-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="20c86-112">Di conseguenza, se un profiler chiama entrambe `SetEnterLeaveFunctionHooks` e [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), quindi `SetEnterLeaveFunctionHooks2` ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="20c86-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="20c86-113">Il `SetEnterLeaveFunctionHooks` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="20c86-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c86-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20c86-114">Requirements</span></span>  
 <span data-ttu-id="20c86-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20c86-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c86-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20c86-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20c86-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c86-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20c86-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c86-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c86-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c86-119">See also</span></span>
- [<span data-ttu-id="20c86-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="20c86-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
