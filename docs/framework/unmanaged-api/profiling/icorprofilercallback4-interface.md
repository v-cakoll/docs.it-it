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
ms.openlocfilehash: 295d3d440529623f4569fd6c5f4debe7e4558990
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499441"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="20b73-102">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="20b73-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="20b73-103">Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni al profiler.</span><span class="sxs-lookup"><span data-stu-id="20b73-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20b73-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="20b73-104">Methods</span></span>  
  
|<span data-ttu-id="20b73-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="20b73-105">Method</span></span>|<span data-ttu-id="20b73-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20b73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20b73-107">Metodo GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="20b73-107">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="20b73-108">Consente all'Code Profiler di impostare flag di generazione del codice alternativi per un nuovo corpo del metodo ricompilato.</span><span class="sxs-lookup"><span data-stu-id="20b73-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="20b73-109">Metodo MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="20b73-109">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="20b73-110">Segnala il nuovo layout degli oggetti nell'heap in seguito a un Garbage Collection di compattazione.</span><span class="sxs-lookup"><span data-stu-id="20b73-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="20b73-111">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="20b73-111">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="20b73-112">Notifica al profiler che il compilatore just-in-time (JIT) ha completato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="20b73-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="20b73-113">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="20b73-113">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="20b73-114">Notifica al profiler che il compilatore JIT (just-in-Time) ha iniziato a ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="20b73-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="20b73-115">Metodo ReJITError</span><span class="sxs-lookup"><span data-stu-id="20b73-115">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="20b73-116">Segnala un errore rilevato durante l'elaborazione di una richiesta di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="20b73-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="20b73-117">Metodo SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="20b73-117">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="20b73-118">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="20b73-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20b73-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20b73-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b73-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20b73-120">Requirements</span></span>  
 <span data-ttu-id="20b73-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b73-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b73-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20b73-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20b73-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20b73-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20b73-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20b73-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b73-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20b73-125">See also</span></span>

- [<span data-ttu-id="20b73-126">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="20b73-126">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="20b73-127">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="20b73-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="20b73-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="20b73-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
