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
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868577"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="1d87e-102">Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="1d87e-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="1d87e-103">Specifica le funzioni implementate dal profiler da chiamare sulle versioni aggiornate degli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="1d87e-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d87e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d87e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d87e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d87e-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="1d87e-106">in Puntatore all'implementazione da utilizzare come callback [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1d87e-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="1d87e-107">in Puntatore all'implementazione da utilizzare come callback [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1d87e-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="1d87e-108">in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1d87e-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d87e-109">Note</span><span class="sxs-lookup"><span data-stu-id="1d87e-109">Remarks</span></span>  
 <span data-ttu-id="1d87e-110">Il metodo `SetEnterLeaveFunctionHooks2` è simile al metodo [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d87e-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="1d87e-111">Usare la prima per specificare le funzioni da usare come le versioni più recenti dei callback enter/leave/tailcall e la seconda per specificare le funzioni da usare come versioni precedenti dei callback enter/leave/tailcall.</span><span class="sxs-lookup"><span data-stu-id="1d87e-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="1d87e-112">È possibile che sia attivo un solo set di callback alla volta.</span><span class="sxs-lookup"><span data-stu-id="1d87e-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="1d87e-113">Se quindi un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` che `SetEnterLeaveFunctionHooks2`, viene usato `SetEnterLeaveFunctionHooks2`.</span><span class="sxs-lookup"><span data-stu-id="1d87e-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="1d87e-114">Il metodo `SetEnterLeaveFunctionHooks2` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="1d87e-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d87e-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1d87e-115">Requirements</span></span>  
 <span data-ttu-id="1d87e-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d87e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d87e-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d87e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d87e-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d87e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d87e-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d87e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d87e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d87e-120">See also</span></span>

- [<span data-ttu-id="1d87e-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1d87e-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1d87e-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="1d87e-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
