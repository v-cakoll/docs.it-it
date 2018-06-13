---
title: Metodo ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3e21d42340378c576bfc65750fba26a257b82cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457746"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="4effa-102">Metodo ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="4effa-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="4effa-103">Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="4effa-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4effa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4effa-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4effa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4effa-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4effa-106">[in] L'ID della funzione che il compilatore JIT è stata avviata da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="4effa-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="4effa-107">[in] L'ID della ricompilazione della nuova versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="4effa-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4effa-108">[in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="4effa-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="4effa-109">Il valore `true` non influisce sul runtime, ma possono influenzare i risultati di profilatura.</span><span class="sxs-lookup"><span data-stu-id="4effa-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4effa-110">Note</span><span class="sxs-lookup"><span data-stu-id="4effa-110">Remarks</span></span>  
 <span data-ttu-id="4effa-111">È possibile ricevere più di una coppia di `ReJITCompilationStarted` e [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) metodo chiama per ogni funzione a causa del modo il runtime gestisce i costruttori di classe.</span><span class="sxs-lookup"><span data-stu-id="4effa-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="4effa-112">Ad esempio, il runtime Avvia ricompilazione di un metodo, ma il costruttore della classe per classe B deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="4effa-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="4effa-113">Pertanto, il runtime ricompila il costruttore di classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="4effa-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="4effa-114">Durante l'esecuzione, il costruttore che effettua una chiamata al metodo che determina il metodo per la ricompilazione nuovamente.</span><span class="sxs-lookup"><span data-stu-id="4effa-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="4effa-115">In questo scenario, viene interrotta la ricompilazione prima del metodo.</span><span class="sxs-lookup"><span data-stu-id="4effa-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="4effa-116">Tuttavia, entrambi tenta ricompilare metodo vengono segnalata con gli eventi di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="4effa-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="4effa-117">I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread effettuano callback simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="4effa-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="4effa-118">Ad esempio, il thread chiama `ReJITCompilationStarted`; tuttavia, prima di un thread chiama [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID (funzione) dal `ReJITCompilationStarted` callback per thread A. Potrebbe sembrare che l'ID della funzione non deve ancora essere valido perché una chiamata a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) non ha ancora ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="4effa-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="4effa-119">Tuttavia, in questo caso, l'ID della funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="4effa-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4effa-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4effa-120">Requirements</span></span>  
 <span data-ttu-id="4effa-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4effa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4effa-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4effa-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4effa-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4effa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4effa-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4effa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4effa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4effa-125">See Also</span></span>  
 [<span data-ttu-id="4effa-126">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4effa-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4effa-127">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="4effa-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="4effa-128">Metodo JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="4effa-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="4effa-129">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="4effa-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
