---
title: Funzione FunctionIDMapper
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 151b790afaf6a251ba5d8d8932f44a503cde853a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458598"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="5d3b5-102">Funzione FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="5d3b5-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="5d3b5-103">Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da utilizzare per il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), e [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) i callback per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="5d3b5-104">`FunctionIDMapper` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d3b5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d3b5-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d3b5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d3b5-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="5d3b5-107">[in] Identificatore della funzione di cui eseguire nuovamente il mapping.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="5d3b5-108">[out] Un puntatore a un valore che il profiler imposta su `true` se vuole ricevere `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` callback; in caso contrario, questo valore viene impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d3b5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5d3b5-109">Return Value</span></span>  
 <span data-ttu-id="5d3b5-110">Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="5d3b5-111">Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="5d3b5-112">In caso contrario, un valore restituito null produrrà risultati imprevedibili, compresa la probabilmente un arresto del processo.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d3b5-113">Note</span><span class="sxs-lookup"><span data-stu-id="5d3b5-113">Remarks</span></span>  
 <span data-ttu-id="5d3b5-114">Il `FunctionIDMapper` funzione è un callback.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="5d3b5-115">Viene implementata dal profiler per modificare il mapping di un ID funzione a un altro identificatore che è più utile per il profiler.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="5d3b5-116">Il `FunctionIDMapper` restituisce l'ID alternativo da utilizzare per qualsiasi funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="5d3b5-117">Il motore di esecuzione rispetta quindi la richiesta del profiler passando tale ID alternativo, oltre all'ID funzione tradizionale, al profiler nel `clientData` parametro il `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` hook, per identificare la funzione per cui viene chiamato l'hook.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="5d3b5-118">È possibile utilizzare il [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) specificare l'implementazione del metodo di `FunctionIDMapper` (funzione).</span><span class="sxs-lookup"><span data-stu-id="5d3b5-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="5d3b5-119">È possibile chiamare il `ICorProfilerInfo::SetFunctionIDMapper` metodo una sola volta e si consiglia di eseguire questa operazione nel [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="5d3b5-120">Per impostazione predefinita, si presuppone che un profiler che imposta il flag COR_PRF_MONITOR_ENTERLEAVE tramite [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), e gli hook tramite [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), dovrebbe essere visualizzato il `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` i callback per ogni funzione.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="5d3b5-121">Tuttavia, i profiler possono implementare `FunctionIDMapper` per evitare selettivamente di ricevere i callback per determinate funzioni impostando `pbHookFunction` a `false`.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="5d3b5-122">I profiler devono poter supportare i casi in cui più thread di un'applicazione profilata chiamano il metodo/funzione stesso contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="5d3b5-123">In questi casi, il profiler può ricevere più `FunctionIDMapper` i callback per lo stesso `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="5d3b5-124">Il profiler deve essere determinato restituire gli stessi valori da questo callback quando viene chiamato più volte con lo stesso `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="5d3b5-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d3b5-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d3b5-125">Requirements</span></span>  
 <span data-ttu-id="5d3b5-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d3b5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d3b5-127">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="5d3b5-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5d3b5-128">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5d3b5-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d3b5-129">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d3b5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3b5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d3b5-130">See Also</span></span>  
 [<span data-ttu-id="5d3b5-131">Metodo SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="5d3b5-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="5d3b5-132">Funzione FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="5d3b5-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [<span data-ttu-id="5d3b5-133">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="5d3b5-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="5d3b5-134">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="5d3b5-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="5d3b5-135">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="5d3b5-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="5d3b5-136">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="5d3b5-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
