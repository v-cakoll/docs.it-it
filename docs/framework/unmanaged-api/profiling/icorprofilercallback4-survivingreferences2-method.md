---
title: Metodo ICorProfilerCallback4::SurvivingReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: bec50183e6a8690cb02f3dc06d32b7449e055cea
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865168"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="126af-102">Metodo ICorProfilerCallback4::SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="126af-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="126af-103">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="126af-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="126af-104">Questo metodo viene chiamato se il profiler ha implementato l'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="126af-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="126af-105">Questo callback sostituisce il metodo [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , perché può segnalare intervalli più grandi di oggetti le cui lunghezze superano quelle che possono essere espresse in un ULONG.</span><span class="sxs-lookup"><span data-stu-id="126af-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126af-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="126af-106">Syntax</span></span>  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="126af-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="126af-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="126af-108">[in] Numero di blocchi di oggetti contigui rimasti in seguito alla mancata compattazione dell'operazione di Garbage Collection,</span><span class="sxs-lookup"><span data-stu-id="126af-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="126af-109">ovvero il valore di `cSurvivingObjectIDRanges` è la dimensione delle matrici `objectIDRangeStart` e `cObjectIDRangeLength`, in cui vengono rispettivamente archiviati un `ObjectID` e una lunghezza per ogni blocco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="126af-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="126af-110">I successivi due argomenti di `SurvivingReferences2` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="126af-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="126af-111">In altre parole, `objectIDRangeStart` e `cObjectIDRangeLength` riguardano lo stesso blocco di oggetti contigui.</span><span class="sxs-lookup"><span data-stu-id="126af-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="126af-112">[in] Matrice di valori `ObjectID`, ognuno dei quali è l'indirizzo iniziale di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="126af-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="126af-113">[in] Matrice di Integer, ognuno dei quali è la dimensione di un blocco escluso di oggetti contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="126af-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="126af-114">Viene specificata una dimensione per ogni blocco a cui si fa riferimento nella matrice `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="126af-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="126af-115">Note</span><span class="sxs-lookup"><span data-stu-id="126af-115">Remarks</span></span>  
 <span data-ttu-id="126af-116">Gli elementi delle matrici `objectIDRangeStart` e `cObjectIDRangeLength` devono essere interpretati come indicato di seguito per determinare se un oggetto è stato escluso dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="126af-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="126af-117">Si supponga che un valore `ObjectID` (`ObjectID`) si trovi nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="126af-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="126af-118">Per qualsiasi valore di `i` compreso nell'intervallo seguente, l'oggetto è stato escluso dall'operazione di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="126af-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="126af-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="126af-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="126af-120">Una mancata compattazione dell'operazione di Garbage Collection recupera la memoria occupata dagli oggetti inutilizzati, ma non compatta lo spazio liberato.</span><span class="sxs-lookup"><span data-stu-id="126af-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="126af-121">Di conseguenza, la memoria viene restituita all'heap, ma gli oggetti attivi non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="126af-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="126af-122">Common Language Runtime (CLR) chiama `SurvivingReferences2` per eseguire operazioni di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="126af-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="126af-123">Per la compattazione di Garbage Collection, viene invece chiamato [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="126af-123">For compacting garbage collections, [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="126af-124">Una stessa operazione di Garbage Collection può eseguire la compattazione per una generazione e non eseguirla per un'altra.</span><span class="sxs-lookup"><span data-stu-id="126af-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="126af-125">Per un Garbage Collection in una determinata generazione, il profiler riceverà un callback di `SurvivingReferences2` o un callback di [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) , ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="126af-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="126af-126">Durante una particolare operazione di Garbage Collection possono essere ricevuti più callback `SurvivingReferences2`, a causa del buffer interno limitato, di callback multipli durante l'operazione di Garbage Collection per server e di altri motivi.</span><span class="sxs-lookup"><span data-stu-id="126af-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="126af-127">Nel caso di più callback durante un'operazione di Garbage Collection, le informazioni sono cumulative. Tutti i riferimenti segnalati in qualsiasi callback `SurvivingReferences2` vengono esclusi dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="126af-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="126af-128">Se il profiler implementa entrambe le interfacce [ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback4](icorprofilercallback4-interface.md) , il metodo `SurvivingReferences2` viene chiamato prima del metodo [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , ma solo se `SurvivingReferences2` restituisce correttamente.</span><span class="sxs-lookup"><span data-stu-id="126af-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="126af-129">I profiler possono restituire un valore HRESULT indicante un errore nel metodo `SurvivingReferences2` per evitare di chiamare il secondo metodo.</span><span class="sxs-lookup"><span data-stu-id="126af-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="126af-130">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="126af-130">Requirements</span></span>  
 <span data-ttu-id="126af-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="126af-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126af-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="126af-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="126af-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="126af-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="126af-134">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126af-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126af-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="126af-135">See also</span></span>

- [<span data-ttu-id="126af-136">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="126af-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="126af-137">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="126af-137">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="126af-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="126af-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
