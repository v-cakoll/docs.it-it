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
ms.openlocfilehash: 78489aae840ff17e68b10bd7593fb7be4dae1af7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496737"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="276fc-102">Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="276fc-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="276fc-103">Specifica le funzioni implementate dal profiler da chiamare sulle versioni aggiornate degli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="276fc-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="276fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="276fc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="276fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="276fc-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="276fc-106">in Puntatore all'implementazione da utilizzare come callback [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="276fc-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="276fc-107">in Puntatore all'implementazione da utilizzare come callback [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="276fc-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="276fc-108">in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="276fc-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="276fc-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="276fc-109">Remarks</span></span>  
 <span data-ttu-id="276fc-110">Il `SetEnterLeaveFunctionHooks2` metodo è simile al metodo [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="276fc-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="276fc-111">Usare la prima per specificare le funzioni da usare come le versioni più recenti dei callback enter/leave/tailcall e la seconda per specificare le funzioni da usare come versioni precedenti dei callback enter/leave/tailcall.</span><span class="sxs-lookup"><span data-stu-id="276fc-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="276fc-112">È possibile che sia attivo un solo set di callback alla volta.</span><span class="sxs-lookup"><span data-stu-id="276fc-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="276fc-113">Pertanto, se un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` che `SetEnterLeaveFunctionHooks2` , `SetEnterLeaveFunctionHooks2` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="276fc-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="276fc-114">Il `SetEnterLeaveFunctionHooks2` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="276fc-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="276fc-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="276fc-115">Requirements</span></span>  
 <span data-ttu-id="276fc-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="276fc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="276fc-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="276fc-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="276fc-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="276fc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="276fc-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="276fc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276fc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="276fc-120">See also</span></span>

- [<span data-ttu-id="276fc-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="276fc-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="276fc-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="276fc-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
