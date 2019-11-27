---
title: Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.date: 03/30/2017
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
ms.openlocfilehash: 4068c8fee13a6086bc6b48bcc6d4117357062747
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449794"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="2bbbd-102">Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="2bbbd-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="2bbbd-103">Specifica le funzioni implementate dal profiler da chiamare sulle versioni aggiornate degli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bbbd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bbbd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bbbd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bbbd-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="2bbbd-106">in Puntatore all'implementazione da utilizzare come callback [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2bbbd-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="2bbbd-107">in Puntatore all'implementazione da utilizzare come callback [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2bbbd-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="2bbbd-108">in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2bbbd-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bbbd-109">Note</span><span class="sxs-lookup"><span data-stu-id="2bbbd-109">Remarks</span></span>  
 <span data-ttu-id="2bbbd-110">Il metodo `SetEnterLeaveFunctionHooks2` è simile al metodo [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2bbbd-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="2bbbd-111">Usare la prima per specificare le funzioni da usare come le versioni più recenti dei callback enter/leave/tailcall e la seconda per specificare le funzioni da usare come versioni precedenti dei callback enter/leave/tailcall.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="2bbbd-112">È possibile che sia attivo un solo set di callback alla volta.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="2bbbd-113">Se quindi un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` che `SetEnterLeaveFunctionHooks2`, viene usato `SetEnterLeaveFunctionHooks2`.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="2bbbd-114">Il metodo `SetEnterLeaveFunctionHooks2` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bbbd-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bbbd-115">Requirements</span></span>  
 <span data-ttu-id="2bbbd-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bbbd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bbbd-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2bbbd-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2bbbd-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bbbd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bbbd-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bbbd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbbd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bbbd-120">See also</span></span>

- [<span data-ttu-id="2bbbd-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2bbbd-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="2bbbd-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2bbbd-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
