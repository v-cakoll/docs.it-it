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
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075899"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="7c7d4-102">Metodo ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="7c7d4-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="7c7d4-103">Notifica al profiler che il compilatore JIT just-in-time è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c7d4-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c7d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c7d4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7c7d4-106">[in] L'ID della funzione che il compilatore JIT è stata avviata da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="7c7d4-107">[in] L'ID di ricompilazione della nuova versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="7c7d4-108">[in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="7c7d4-109">Un valore di `true` non danneggia il runtime, ma può influenzare i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c7d4-110">Note</span><span class="sxs-lookup"><span data-stu-id="7c7d4-110">Remarks</span></span>  
 <span data-ttu-id="7c7d4-111">È possibile ricevere più di una coppia di `ReJITCompilationStarted` e [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) metodo viene chiamato per ogni funzione a causa della modalità il runtime gestisce i costruttori di classe.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="7c7d4-112">Ad esempio, il runtime Avvia ricompilazione di un metodo, ma deve essere eseguito il costruttore della classe per classe B.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="7c7d4-113">Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="7c7d4-114">Mentre il costruttore è in esecuzione, che effettua una chiamata al metodo A, che fa sì che il metodo venga ricompilato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="7c7d4-115">In questo scenario, la ricompilazione prima del metodo verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="7c7d4-116">Tuttavia, entrambi tenta di ricompilare metodo un oggetto vengono segnalata con eventi di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="7c7d4-117">I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread contemporaneamente dei callback.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="7c7d4-118">Ad esempio, il thread chiama `ReJITCompilationStarted`; tuttavia, prima che il thread chiami [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), il thread B chiama [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID (funzione) dal `ReJITCompilationStarted` callback per il thread A. Può sembrare che l'ID di funzione non deve ancora essere valido perché una chiamata a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) non ha ancora ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="7c7d4-119">Tuttavia, in questo caso, l'ID di funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="7c7d4-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c7d4-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c7d4-120">Requirements</span></span>  
 <span data-ttu-id="7c7d4-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c7d4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c7d4-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c7d4-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c7d4-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c7d4-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7c7d4-124">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7c7d4-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c7d4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c7d4-125">See also</span></span>

- [<span data-ttu-id="7c7d4-126">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7c7d4-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7c7d4-127">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="7c7d4-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="7c7d4-128">Metodo JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7c7d4-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="7c7d4-129">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7c7d4-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
