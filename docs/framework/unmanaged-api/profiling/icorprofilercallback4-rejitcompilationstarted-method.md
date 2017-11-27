---
title: Metodo ICorProfilerCallback4::ReJITCompilationStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ddcacf72d21ec076fe74a1c069311ef3f73a20c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c4763-102">Metodo ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c4763-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c4763-103">Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="c4763-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4763-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4763-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4763-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4763-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c4763-106">[in] L'ID della funzione che il compilatore JIT è stata avviata da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="c4763-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c4763-107">[in] L'ID della ricompilazione della nuova versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="c4763-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c4763-108">[in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="c4763-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c4763-109">Il valore `true` non influisce sul runtime, ma possono influenzare i risultati di profilatura.</span><span class="sxs-lookup"><span data-stu-id="c4763-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4763-110">Note</span><span class="sxs-lookup"><span data-stu-id="c4763-110">Remarks</span></span>  
 <span data-ttu-id="c4763-111">È possibile ricevere più di una coppia di `ReJITCompilationStarted` e [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) metodo chiama per ogni funzione a causa del modo il runtime gestisce i costruttori di classe.</span><span class="sxs-lookup"><span data-stu-id="c4763-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c4763-112">Ad esempio, il runtime Avvia ricompilazione di un metodo, ma il costruttore della classe per classe B deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="c4763-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c4763-113">Pertanto, il runtime ricompila il costruttore di classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="c4763-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c4763-114">Durante l'esecuzione, il costruttore che effettua una chiamata al metodo che determina il metodo per la ricompilazione nuovamente.</span><span class="sxs-lookup"><span data-stu-id="c4763-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c4763-115">In questo scenario, viene interrotta la ricompilazione prima del metodo.</span><span class="sxs-lookup"><span data-stu-id="c4763-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c4763-116">Tuttavia, entrambi tenta ricompilare metodo vengono segnalata con gli eventi di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c4763-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c4763-117">I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread effettuano callback simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="c4763-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c4763-118">Ad esempio, il thread chiama `ReJITCompilationStarted`; tuttavia, prima di un thread chiama [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID (funzione) dal `ReJITCompilationStarted` callback per thread A. Potrebbe sembrare che l'ID della funzione non deve ancora essere valido perché una chiamata a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) non ha ancora ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="c4763-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c4763-119">Tuttavia, in questo caso, l'ID della funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="c4763-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4763-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4763-120">Requirements</span></span>  
 <span data-ttu-id="c4763-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4763-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4763-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4763-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4763-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4763-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4763-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4763-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4763-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4763-125">See Also</span></span>  
 [<span data-ttu-id="c4763-126">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c4763-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c4763-127">ICorProfilerCallback4 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c4763-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="c4763-128">JITCompilationFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="c4763-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="c4763-129">ReJITCompilationFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="c4763-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
