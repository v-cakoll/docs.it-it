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
ms.openlocfilehash: cf0726a12b0274fd7a38e82b66c33430d26b031a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497452"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="b57ed-102">Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="b57ed-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="b57ed-103">Specifica le funzioni implementate dal profiler da chiamare sugli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="b57ed-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b57ed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b57ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b57ed-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="b57ed-106">in Puntatore all'implementazione da utilizzare come callback [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b57ed-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="b57ed-107">in Puntatore all'implementazione da utilizzare come callback [FunctionLeave](functionleave-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b57ed-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="b57ed-108">in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall](functiontailcall-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b57ed-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b57ed-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b57ed-109">Remarks</span></span>  
 <span data-ttu-id="b57ed-110">In .NET Framework versione 1,0 ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b57ed-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="b57ed-111">Può essere attivo un solo set di callback alla volta.</span><span class="sxs-lookup"><span data-stu-id="b57ed-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="b57ed-112">Se quindi un profiler chiama sia `SetEnterLeaveFunctionHooks` che [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="b57ed-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="b57ed-113">Il `SetEnterLeaveFunctionHooks` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="b57ed-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b57ed-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b57ed-114">Requirements</span></span>  
 <span data-ttu-id="b57ed-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b57ed-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b57ed-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b57ed-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b57ed-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b57ed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b57ed-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b57ed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57ed-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b57ed-119">See also</span></span>

- [<span data-ttu-id="b57ed-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b57ed-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
