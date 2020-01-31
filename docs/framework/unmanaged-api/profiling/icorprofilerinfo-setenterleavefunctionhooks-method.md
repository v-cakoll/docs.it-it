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
ms.openlocfilehash: f7bc1954d11134a4515d2e29e9e0eb1626ae5d26
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863428"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="665d3-102">Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="665d3-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="665d3-103">Specifica le funzioni implementate dal profiler da chiamare sugli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="665d3-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="665d3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="665d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="665d3-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="665d3-106">in Puntatore all'implementazione da utilizzare come callback [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="665d3-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="665d3-107">in Puntatore all'implementazione da utilizzare come callback [FunctionLeave](functionleave-function.md) .</span><span class="sxs-lookup"><span data-stu-id="665d3-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="665d3-108">in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall](functiontailcall-function.md) .</span><span class="sxs-lookup"><span data-stu-id="665d3-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="665d3-109">Note</span><span class="sxs-lookup"><span data-stu-id="665d3-109">Remarks</span></span>  
 <span data-ttu-id="665d3-110">In .NET Framework versione 1,0 ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.</span><span class="sxs-lookup"><span data-stu-id="665d3-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="665d3-111">Può essere attivo un solo set di callback alla volta.</span><span class="sxs-lookup"><span data-stu-id="665d3-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="665d3-112">Se quindi un profiler chiama sia `SetEnterLeaveFunctionHooks` che [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="665d3-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="665d3-113">Il metodo `SetEnterLeaveFunctionHooks` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="665d3-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="665d3-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="665d3-114">Requirements</span></span>  
 <span data-ttu-id="665d3-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665d3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665d3-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="665d3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="665d3-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="665d3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="665d3-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665d3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665d3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="665d3-119">See also</span></span>

- [<span data-ttu-id="665d3-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="665d3-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
