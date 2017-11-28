---
title: Metodo ICorProfilerCallback2::GarbageCollectionStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="d14fe-102">Metodo ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="d14fe-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="d14fe-103">Notifica al profiler di codice che ha avviato l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d14fe-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d14fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d14fe-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d14fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d14fe-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="d14fe-106">[in] Il numero totale di voci di `generationCollected` matrice.</span><span class="sxs-lookup"><span data-stu-id="d14fe-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="d14fe-107">[in] Una matrice di valori booleani, che sono `true` se la generazione che corrisponde all'indice della matrice viene raccolto da garbage collection; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d14fe-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d14fe-108">La matrice viene indicizzata da un valore di [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumerazione che indica la generazione.</span><span class="sxs-lookup"><span data-stu-id="d14fe-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="d14fe-109">[in] Il valore di [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumerazione che indica il motivo per l'operazione di garbage collection è stata attivata.</span><span class="sxs-lookup"><span data-stu-id="d14fe-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d14fe-110">Note</span><span class="sxs-lookup"><span data-stu-id="d14fe-110">Remarks</span></span>  
 <span data-ttu-id="d14fe-111">Tutti i callback relativi a questa operazione di garbage collection si verificheranno tra il `GarbageCollectionStarted` callback e i corrispondenti [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="d14fe-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="d14fe-112">Questi callback non devono verificarsi sullo stesso thread.</span><span class="sxs-lookup"><span data-stu-id="d14fe-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="d14fe-113">È consigliabile per il profiler controllare gli oggetti nei rispettivi percorsi originali durante il `GarbageCollectionStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="d14fe-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="d14fe-114">Il garbage collector verrà avviato lo spostamento di oggetti dopo l'uscita da `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="d14fe-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="d14fe-115">Dopo che il profiler ha restituito da questo callback, il profiler deve considerare tutti gli ID oggetto risulta valido finché riceve un `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="d14fe-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d14fe-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d14fe-116">Requirements</span></span>  
 <span data-ttu-id="d14fe-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d14fe-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d14fe-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d14fe-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d14fe-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d14fe-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d14fe-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d14fe-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14fe-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14fe-121">See Also</span></span>  
 [<span data-ttu-id="d14fe-122">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d14fe-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d14fe-123">ICorProfilerCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d14fe-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
