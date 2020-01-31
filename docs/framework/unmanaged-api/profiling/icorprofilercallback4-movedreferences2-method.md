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
ms.openlocfilehash: 2f305852ae218417aa1f4d4fe9d2076c0163fd60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865272"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="9c3b4-102">Metodo ICorProfilerCallback4::MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="9c3b4-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>
<span data-ttu-id="9c3b4-103">Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="9c3b4-104">Questo metodo viene chiamato se il profiler ha implementato l'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9c3b4-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="9c3b4-105">Questo callback sostituisce il metodo [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , perché può segnalare intervalli più grandi di oggetti le cui lunghezze superano quelle che possono essere espresse in un ULONG.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-105">This callback replaces the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3b4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c3b4-106">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c3b4-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c3b4-107">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="9c3b4-108">[in] Numero di blocchi di oggetti contigui spostati in seguito all'operazione di Garbage Collection con compattazione.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="9c3b4-109">Ciò significa che il valore di `cMovedObjectIDRanges` corrisponde alle dimensioni totali delle matrici `oldObjectIDRangeStart`, `newObjectIDRangeStart` e `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="9c3b4-110">I successivi tre argomenti di `MovedReferences2` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="9c3b4-111">In altre parole, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` e `cObjectIDRangeLength[i]` riguardano un singolo blocco di oggetti contigui.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="9c3b4-112">[in] Matrice di valori `ObjectID`, ognuno dei quali è il vecchio indirizzo iniziale (precedente all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="9c3b4-113">[in] Matrice di valori `ObjectID`, ognuno dei quali è il nuovo indirizzo iniziale (successivo all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="9c3b4-114">[in] Matrice di Integer, ognuno dei quali corrisponde alle dimensioni di un blocco di oggetti contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="9c3b4-115">Viene specificata una dimensione per ogni blocco a cui viene fatto riferimento nelle matrici `oldObjectIDRangeStart` e `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c3b4-116">Note</span><span class="sxs-lookup"><span data-stu-id="9c3b4-116">Remarks</span></span>  
 <span data-ttu-id="9c3b4-117">Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="9c3b4-118">Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="9c3b4-119">Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="9c3b4-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="9c3b4-120">In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9c3b4-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="9c3b4-121">Per qualsiasi valore di `i` compreso nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="9c3b4-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="9c3b4-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="9c3b4-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="9c3b4-123">è possibile calcolare il nuovo `ObjectID` come segue:</span><span class="sxs-lookup"><span data-stu-id="9c3b4-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="9c3b4-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="9c3b4-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="9c3b4-125">Nessuno dei valori di `ObjectID` passati da `MovedReferences2` è valido durante il callback vero e proprio, perché è possibile che il Garbage Collector stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="9c3b4-126">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences2`.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="9c3b4-127">Un callback [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) indica che tutti gli oggetti sono stati spostati nelle nuove posizioni ed è possibile eseguire il controllo.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-127">A [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="9c3b4-128">Se il profiler implementa sia le interfacce [ICorProfilerCallback](icorprofilercallback-interface.md) che [ICorProfilerCallback4](icorprofilercallback4-interface.md) , il metodo `MovedReferences2` viene chiamato prima del metodo [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , ma solo se il `MovedReferences2` metodo restituisce correttamente.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="9c3b4-129">I profiler possono restituire un valore HRESULT indicante un errore nel metodo `MovedReferences2` per evitare di chiamare il secondo metodo.</span><span class="sxs-lookup"><span data-stu-id="9c3b4-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c3b4-130">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9c3b4-130">Requirements</span></span>  
 <span data-ttu-id="9c3b4-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c3b4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c3b4-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c3b4-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c3b4-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c3b4-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c3b4-134">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c3b4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3b4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c3b4-135">See also</span></span>

- [<span data-ttu-id="9c3b4-136">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9c3b4-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9c3b4-137">Metodo MovedReferences</span><span class="sxs-lookup"><span data-stu-id="9c3b4-137">MovedReferences Method</span></span>](icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="9c3b4-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="9c3b4-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="9c3b4-139">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="9c3b4-139">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9c3b4-140">Profilatura</span><span class="sxs-lookup"><span data-stu-id="9c3b4-140">Profiling</span></span>](index.md)
