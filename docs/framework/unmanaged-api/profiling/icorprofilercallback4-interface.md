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
ms.openlocfilehash: 8bcddc143cacc3df016e6b8dd7907a67354c4311
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455742"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="de6dd-102">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="de6dd-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="de6dd-103">Fornisce metodi di callback che usa common language runtime (CLR) per comunicare informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="de6dd-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de6dd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="de6dd-104">Methods</span></span>  
  
|<span data-ttu-id="de6dd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="de6dd-105">Method</span></span>|<span data-ttu-id="de6dd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de6dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de6dd-107">Metodo GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="de6dd-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="de6dd-108">Consente al profiler di codice impostare i flag di generazione del codice alternativo per un nuovo corpo del metodo ricompilata.</span><span class="sxs-lookup"><span data-stu-id="de6dd-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="de6dd-109">Metodo MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="de6dd-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="de6dd-110">Restituisce il nuovo layout degli oggetti nell'heap a seguito di una garbage collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="de6dd-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="de6dd-111">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="de6dd-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="de6dd-112">Notifica al profiler che il compilatore di just-in-time (JIT) ha terminato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="de6dd-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="de6dd-113">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="de6dd-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="de6dd-114">Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="de6dd-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="de6dd-115">Metodo ReJITError</span><span class="sxs-lookup"><span data-stu-id="de6dd-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="de6dd-116">Segnala un errore durante l'elaborazione di una richiesta di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="de6dd-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="de6dd-117">Metodo SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="de6dd-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="de6dd-118">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="de6dd-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de6dd-119">Note</span><span class="sxs-lookup"><span data-stu-id="de6dd-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de6dd-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de6dd-120">Requirements</span></span>  
 <span data-ttu-id="de6dd-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de6dd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de6dd-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de6dd-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de6dd-123">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="de6dd-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de6dd-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de6dd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de6dd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de6dd-125">See Also</span></span>  
 [<span data-ttu-id="de6dd-126">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="de6dd-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="de6dd-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="de6dd-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="de6dd-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="de6dd-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
