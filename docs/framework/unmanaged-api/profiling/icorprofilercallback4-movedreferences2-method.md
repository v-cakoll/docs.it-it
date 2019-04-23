---
title: Metodo ICorProfilerCallback4::MovedReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d368c88503853d0620f28f02f88a6d887c1aa681
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156403"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="17d0d-102">Metodo ICorProfilerCallback4::MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="17d0d-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>
<span data-ttu-id="17d0d-103">Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="17d0d-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="17d0d-104">Questo metodo viene chiamato se il profiler ha implementato il [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="17d0d-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="17d0d-105">Questo callback sostituisce il [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) metodo, perché può indicare intervalli più ampi di oggetti le cui lunghezze superano quelle che possono essere espresse in ULONG.</span><span class="sxs-lookup"><span data-stu-id="17d0d-105">This callback replaces the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d0d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17d0d-106">Syntax</span></span>  
  
```  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d0d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="17d0d-107">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="17d0d-108">[in] Numero di blocchi di oggetti contigui spostati in seguito all'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="17d0d-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="17d0d-109">Ciò significa che il valore di `cMovedObjectIDRanges` corrisponde alle dimensioni totali delle matrici `oldObjectIDRangeStart`, `newObjectIDRangeStart` e `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="17d0d-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="17d0d-110">I successivi tre argomenti di `MovedReferences2` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="17d0d-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="17d0d-111">In altre parole, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` e `cObjectIDRangeLength[i]` riguardano un singolo blocco di oggetti contigui.</span><span class="sxs-lookup"><span data-stu-id="17d0d-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="17d0d-112">[in] Matrice di valori `ObjectID`, ognuno dei quali è il vecchio indirizzo iniziale (precedente all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="17d0d-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="17d0d-113">[in] Matrice di valori `ObjectID`, ognuno dei quali è il nuovo indirizzo iniziale (successivo all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="17d0d-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="17d0d-114">[in] Matrice di Integer, ognuno dei quali corrisponde alle dimensioni di un blocco di oggetti contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="17d0d-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="17d0d-115">Viene specificata una dimensione per ogni blocco a cui viene fatto riferimento nelle matrici `oldObjectIDRangeStart` e `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="17d0d-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17d0d-116">Note</span><span class="sxs-lookup"><span data-stu-id="17d0d-116">Remarks</span></span>  
 <span data-ttu-id="17d0d-117">Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato.</span><span class="sxs-lookup"><span data-stu-id="17d0d-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="17d0d-118">Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="17d0d-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="17d0d-119">Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="17d0d-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="17d0d-120">In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:</span><span class="sxs-lookup"><span data-stu-id="17d0d-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="17d0d-121">Per qualsiasi valore di `i` compreso nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="17d0d-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="17d0d-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="17d0d-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="17d0d-123">è possibile calcolare il nuovo `ObjectID` come segue:</span><span class="sxs-lookup"><span data-stu-id="17d0d-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="17d0d-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="17d0d-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="17d0d-125">Nessuno dei valori di `ObjectID` passati da `MovedReferences2` è valido durante il callback vero e proprio, perché è possibile che il Garbage Collector stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove.</span><span class="sxs-lookup"><span data-stu-id="17d0d-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="17d0d-126">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences2`.</span><span class="sxs-lookup"><span data-stu-id="17d0d-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="17d0d-127">Oggetto [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indica che tutti gli oggetti sono stati spostati nelle nuove posizioni e possa eseguire l'ispezione.</span><span class="sxs-lookup"><span data-stu-id="17d0d-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="17d0d-128">Se il profiler implementa sia il [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e il [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfacce, il `MovedReferences2` metodo viene chiamato prima di [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) metodo, ma solo se il `MovedReferences2` metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="17d0d-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="17d0d-129">I profiler possono restituire un valore HRESULT indicante un errore nel metodo `MovedReferences2` per evitare di chiamare il secondo metodo.</span><span class="sxs-lookup"><span data-stu-id="17d0d-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d0d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17d0d-130">Requirements</span></span>  
 <span data-ttu-id="17d0d-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d0d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d0d-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17d0d-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17d0d-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17d0d-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17d0d-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d0d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d0d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17d0d-135">See also</span></span>

- [<span data-ttu-id="17d0d-136">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="17d0d-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="17d0d-137">Metodo MovedReferences</span><span class="sxs-lookup"><span data-stu-id="17d0d-137">MovedReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="17d0d-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="17d0d-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="17d0d-139">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="17d0d-139">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="17d0d-140">Profilatura</span><span class="sxs-lookup"><span data-stu-id="17d0d-140">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
