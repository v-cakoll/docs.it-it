---
title: Interfaccia ICorProfilerCallback4
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205134"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="c13a5-102">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="c13a5-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="c13a5-103">Fornisce metodi di callback che common language runtime (CLR) usa per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="c13a5-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c13a5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c13a5-104">Methods</span></span>  
  
|<span data-ttu-id="c13a5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c13a5-105">Method</span></span>|<span data-ttu-id="c13a5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c13a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c13a5-107">Metodo GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="c13a5-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="c13a5-108">Consente al profiler di codice impostare i flag di generazione di codice alternativo per il corpo di un nuovo metodo ricompilata.</span><span class="sxs-lookup"><span data-stu-id="c13a5-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="c13a5-109">Metodo MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="c13a5-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="c13a5-110">Indica il nuovo layout degli oggetti nell'heap come risultato di una garbage collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="c13a5-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="c13a5-111">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c13a5-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="c13a5-112">Notifica al profiler che il compilatore JIT just-in-time ha terminato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="c13a5-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="c13a5-113">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c13a5-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="c13a5-114">Notifica al profiler che il compilatore JIT just-in-time è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="c13a5-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="c13a5-115">Metodo ReJITError</span><span class="sxs-lookup"><span data-stu-id="c13a5-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="c13a5-116">Segnala un errore durante l'elaborazione di una richiesta di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="c13a5-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="c13a5-117">Metodo SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="c13a5-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="c13a5-118">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="c13a5-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c13a5-119">Note</span><span class="sxs-lookup"><span data-stu-id="c13a5-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13a5-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c13a5-120">Requirements</span></span>  
 <span data-ttu-id="c13a5-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c13a5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13a5-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c13a5-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c13a5-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c13a5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c13a5-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13a5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13a5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c13a5-125">See also</span></span>

- [<span data-ttu-id="c13a5-126">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c13a5-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="c13a5-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c13a5-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c13a5-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c13a5-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
