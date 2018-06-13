---
title: Metodo ICorProfilerCallback2::SurvivingReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0ed1dc09e8dcee8a4c67e01279c6e13661e252d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459827"
---
# <a name="icorprofilercallback2survivingreferences-method"></a><span data-ttu-id="2714b-102">Metodo ICorProfilerCallback2::SurvivingReferences</span><span class="sxs-lookup"><span data-stu-id="2714b-102">ICorProfilerCallback2::SurvivingReferences Method</span></span>
<span data-ttu-id="2714b-103">Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="2714b-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2714b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2714b-104">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2714b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2714b-105">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="2714b-106">[in] Numero di blocchi di oggetti contigui rimasti in seguito alla mancata compattazione dell'operazione di Garbage Collection,</span><span class="sxs-lookup"><span data-stu-id="2714b-106">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="2714b-107">ovvero il valore di `cSurvivingObjectIDRanges` è la dimensione delle matrici `objectIDRangeStart` e `cObjectIDRangeLength`, in cui vengono rispettivamente archiviati un `ObjectID` e una lunghezza per ogni blocco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="2714b-107">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="2714b-108">I successivi due argomenti di `SurvivingReferences` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="2714b-108">The next two arguments of `SurvivingReferences` are parallel arrays.</span></span> <span data-ttu-id="2714b-109">In altre parole, `objectIDRangeStart` e `cObjectIDRangeLength` riguardano lo stesso blocco di oggetti contigui.</span><span class="sxs-lookup"><span data-stu-id="2714b-109">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="2714b-110">[in] Matrice di valori `ObjectID`, ognuno dei quali è l'indirizzo iniziale di un blocco di oggetti attivi contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="2714b-110">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="2714b-111">[in] Matrice di Integer, ognuno dei quali è la dimensione di un blocco escluso di oggetti contigui in memoria.</span><span class="sxs-lookup"><span data-stu-id="2714b-111">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="2714b-112">Viene specificata una dimensione per ogni blocco a cui si fa riferimento nella matrice `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="2714b-112">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2714b-113">Note</span><span class="sxs-lookup"><span data-stu-id="2714b-113">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2714b-114">Questo metodo segnala le dimensioni come `MAX_ULONG` per gli oggetti maggiori di 4 GB su piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="2714b-114">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="2714b-115">Per gli oggetti che sono maggiori di 4 GB, usare il [icorprofilercallback4:: Survivingreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="2714b-115">For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="2714b-116">Gli elementi delle matrici `objectIDRangeStart` e `cObjectIDRangeLength` devono essere interpretati come indicato di seguito per determinare se un oggetto è stato escluso dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2714b-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="2714b-117">Si supponga che un valore `ObjectID` (`ObjectID`) si trovi nell'intervallo seguente:</span><span class="sxs-lookup"><span data-stu-id="2714b-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="2714b-118">Per qualsiasi valore di `i` compreso nell'intervallo seguente, l'oggetto è stato escluso dall'operazione di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="2714b-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="2714b-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="2714b-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="2714b-120">Una mancata compattazione dell'operazione di Garbage Collection recupera la memoria occupata dagli oggetti inutilizzati, ma non compatta lo spazio liberato.</span><span class="sxs-lookup"><span data-stu-id="2714b-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="2714b-121">Di conseguenza, la memoria viene restituita all'heap, ma gli oggetti attivi non vengono spostati.</span><span class="sxs-lookup"><span data-stu-id="2714b-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="2714b-122">Common Language Runtime (CLR) chiama `SurvivingReferences` per eseguire operazioni di Garbage Collection senza compattazione.</span><span class="sxs-lookup"><span data-stu-id="2714b-122">The common language runtime (CLR) calls `SurvivingReferences` for non-compacting garbage collections.</span></span> <span data-ttu-id="2714b-123">Per la garbage collection con compattazione, [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) viene invece chiamato.</span><span class="sxs-lookup"><span data-stu-id="2714b-123">For compacting garbage collections, [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) is called instead.</span></span> <span data-ttu-id="2714b-124">Una stessa operazione di Garbage Collection può eseguire la compattazione per una generazione e non eseguirla per un'altra.</span><span class="sxs-lookup"><span data-stu-id="2714b-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="2714b-125">Per una Garbage Collection in una determinata generazione, il profiler riceverà un callback `SurvivingReferences` o un callback `MovedReferences`, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="2714b-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences` callback or a `MovedReferences` callback, but not both.</span></span>  
  
 <span data-ttu-id="2714b-126">Durante una particolare operazione di Garbage Collection possono essere ricevuti più callback `SurvivingReferences`, a causa del buffer interno limitato, di callback multipli durante l'operazione di Garbage Collection per server e di altri motivi.</span><span class="sxs-lookup"><span data-stu-id="2714b-126">Multiple `SurvivingReferences` callbacks might be received during a particular garbage collection, due to limited internal buffering, multiple threads reporting in the case of server garbage collection, and other reasons.</span></span> <span data-ttu-id="2714b-127">Nel caso di più callback durante un'operazione di Garbage Collection, le informazioni sono cumulative. Tutti i riferimenti segnalati in qualsiasi callback `SurvivingReferences` vengono esclusi dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2714b-127">In the case of multiple callbacks during a garbage collection, the information is cumulative — all references that are reported in any `SurvivingReferences` callback survive the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2714b-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2714b-128">Requirements</span></span>  
 <span data-ttu-id="2714b-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2714b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2714b-130">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2714b-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2714b-131">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2714b-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2714b-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2714b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2714b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2714b-133">See Also</span></span>  
 [<span data-ttu-id="2714b-134">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2714b-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="2714b-135">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="2714b-135">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="2714b-136">Metodo SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="2714b-136">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)
