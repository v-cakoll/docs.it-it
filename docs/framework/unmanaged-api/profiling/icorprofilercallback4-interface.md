---
title: Interfaccia ICorProfilerCallback4
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4
helpviewer_keywords: ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64a26f5dfb0ad9f06bb1b9eb31dcae36f4623c4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="cb0b9-102">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="cb0b9-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="cb0b9-103">Fornisce metodi di callback che usa common language runtime (CLR) per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb0b9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb0b9-104">Methods</span></span>  
  
|<span data-ttu-id="cb0b9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb0b9-105">Method</span></span>|<span data-ttu-id="cb0b9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb0b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb0b9-107">GetReJITParameters (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="cb0b9-108">Consente al profiler di codice impostare i flag di generazione del codice alternativo per un nuovo corpo del metodo ricompilata.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="cb0b9-109">MovedReferences2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="cb0b9-110">Restituisce il nuovo layout degli oggetti nell'heap a seguito di una garbage collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="cb0b9-111">ReJITCompilationFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="cb0b9-112">Notifica al profiler che il compilatore di just-in-time (JIT) ha terminato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="cb0b9-113">ReJITCompilationStarted (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="cb0b9-114">Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="cb0b9-115">ReJITError (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="cb0b9-116">Segnala un errore durante l'elaborazione di una richiesta di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="cb0b9-117">SurvivingReferences2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="cb0b9-118">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="cb0b9-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb0b9-119">Note</span><span class="sxs-lookup"><span data-stu-id="cb0b9-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb0b9-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb0b9-120">Requirements</span></span>  
 <span data-ttu-id="cb0b9-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb0b9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb0b9-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb0b9-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb0b9-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb0b9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb0b9-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb0b9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0b9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb0b9-125">See Also</span></span>  
 [<span data-ttu-id="cb0b9-126">ICorProfilerCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="cb0b9-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="cb0b9-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="cb0b9-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cb0b9-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cb0b9-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
