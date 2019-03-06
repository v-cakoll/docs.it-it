---
title: Metodo ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee520ba95a8eefcc3322af0d0dd6e03c70d35cd4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468702"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="83bf6-102">Metodo ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="83bf6-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="83bf6-103">Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler.</span><span class="sxs-lookup"><span data-stu-id="83bf6-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="83bf6-104">Questo metodo estende la [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) metodo con un parametro di dati aggiuntivi che i profiler possono usare per distinguere tra runtime.</span><span class="sxs-lookup"><span data-stu-id="83bf6-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bf6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83bf6-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83bf6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="83bf6-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="83bf6-107">[in] Un puntatore a un [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementazione che verrà chiamato per eseguire il mapping di `FunctionID` valori ai rispettivi valori alternativi.</span><span class="sxs-lookup"><span data-stu-id="83bf6-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="83bf6-108">[in] Un puntatore che viene passato a ogni [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) funzione chiamata eseguita dal runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="83bf6-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="83bf6-109">Il profiler può usare queste informazioni per distinguere tra runtime.</span><span class="sxs-lookup"><span data-stu-id="83bf6-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83bf6-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83bf6-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83bf6-111">Note</span><span class="sxs-lookup"><span data-stu-id="83bf6-111">Remarks</span></span>  
 <span data-ttu-id="83bf6-112">Le alternative per i valori FunctionID verranno passate agli hook di ingresso/uscita del profiler funzione ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), e [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; oppure [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), e [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) che vengono specificati per il [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) oppure [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="83bf6-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="83bf6-113">Il `FunctionIDMapper2` metodo può essere impostato solo una volta, è consigliabile impostarla [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="83bf6-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83bf6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83bf6-114">Requirements</span></span>  
 <span data-ttu-id="83bf6-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83bf6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83bf6-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83bf6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83bf6-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83bf6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83bf6-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83bf6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bf6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83bf6-119">See also</span></span>
- [<span data-ttu-id="83bf6-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="83bf6-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="83bf6-121">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="83bf6-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="83bf6-122">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="83bf6-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="83bf6-123">Profilatura</span><span class="sxs-lookup"><span data-stu-id="83bf6-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
