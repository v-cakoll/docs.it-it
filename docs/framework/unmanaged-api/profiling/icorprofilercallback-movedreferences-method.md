---
title: Metodo ICorProfilerCallback::MovedReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
ms.openlocfilehash: d78e7e863ab953182ea7c1ff342593b4bdf3215d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445881"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="56b10-102">Metodo ICorProfilerCallback::MovedReferences</span><span class="sxs-lookup"><span data-stu-id="56b10-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="56b10-103">Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="56b10-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56b10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56b10-104">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="56b10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56b10-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="56b10-106">[in] Numero di blocchi di oggetti contigui spostati in seguito all'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="56b10-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="56b10-107">Ciò significa che il valore di `cMovedObjectIDRanges` corrisponde alle dimensioni totali delle matrici `oldObjectIDRangeStart`, `newObjectIDRangeStart` e `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="56b10-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="56b10-108">I successivi tre argomenti di `MovedReferences` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="56b10-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="56b10-109">In altre parole, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` e `cObjectIDRangeLength[i]` riguardano un singolo blocco di oggetti contigui.</span><span class="sxs-lookup"><span data-stu-id="56b10-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="56b10-110">[in] Matrice di valori `ObjectID`, ognuno dei quali è il vecchio indirizzo iniziale (precedente all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="56b10-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="56b10-111">[in] Matrice di valori `ObjectID`, ognuno dei quali è il nuovo indirizzo iniziale (successivo all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="56b10-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="56b10-112">[in] Matrice di Integer, ognuno dei quali corrisponde alle dimensioni di un blocco di oggetti contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="56b10-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="56b10-113">Viene specificata una dimensione per ogni blocco a cui viene fatto riferimento nelle matrici `oldObjectIDRangeStart` e `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="56b10-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56b10-114">Note</span><span class="sxs-lookup"><span data-stu-id="56b10-114">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="56b10-115">Questo metodo segnala le dimensioni come `MAX_ULONG` per gli oggetti maggiori di 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="56b10-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="56b10-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span><span class="sxs-lookup"><span data-stu-id="56b10-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="56b10-117">Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato.</span><span class="sxs-lookup"><span data-stu-id="56b10-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="56b10-118">Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="56b10-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="56b10-119">Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="56b10-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="56b10-120">In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:</span><span class="sxs-lookup"><span data-stu-id="56b10-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="56b10-121">Per qualsiasi valore di `i` compreso nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="56b10-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="56b10-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="56b10-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="56b10-123">è possibile calcolare il nuovo `ObjectID` come segue:</span><span class="sxs-lookup"><span data-stu-id="56b10-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="56b10-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="56b10-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="56b10-125">Nessuno dei valori di `ObjectID` passati da `MovedReferences` è valido durante il callback vero e proprio, perché è possibile che l'operazione di Garbage Collection stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove.</span><span class="sxs-lookup"><span data-stu-id="56b10-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="56b10-126">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences`.</span><span class="sxs-lookup"><span data-stu-id="56b10-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="56b10-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span><span class="sxs-lookup"><span data-stu-id="56b10-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56b10-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56b10-128">Requirements</span></span>  
 <span data-ttu-id="56b10-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56b10-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56b10-130">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56b10-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56b10-131">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56b10-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56b10-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56b10-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b10-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56b10-133">See also</span></span>

- [<span data-ttu-id="56b10-134">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="56b10-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="56b10-135">Metodo MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="56b10-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="56b10-136">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="56b10-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="56b10-137">Profilatura</span><span class="sxs-lookup"><span data-stu-id="56b10-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
