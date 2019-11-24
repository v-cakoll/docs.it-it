---
title: Metodo ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439820"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="f238d-102">Metodo ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="f238d-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="f238d-103">Notifies the code profiler that garbage collection has started.</span><span class="sxs-lookup"><span data-stu-id="f238d-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f238d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f238d-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f238d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f238d-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="f238d-106">[in] The total number of entries in the `generationCollected` array.</span><span class="sxs-lookup"><span data-stu-id="f238d-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="f238d-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="f238d-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="f238d-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span><span class="sxs-lookup"><span data-stu-id="f238d-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="f238d-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span><span class="sxs-lookup"><span data-stu-id="f238d-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f238d-110">Note</span><span class="sxs-lookup"><span data-stu-id="f238d-110">Remarks</span></span>  
 <span data-ttu-id="f238d-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="f238d-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="f238d-112">These callbacks need not occur on the same thread.</span><span class="sxs-lookup"><span data-stu-id="f238d-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="f238d-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="f238d-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="f238d-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="f238d-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="f238d-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="f238d-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f238d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f238d-116">Requirements</span></span>  
 <span data-ttu-id="f238d-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f238d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f238d-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f238d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f238d-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f238d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f238d-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f238d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f238d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f238d-121">See also</span></span>

- [<span data-ttu-id="f238d-122">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f238d-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f238d-123">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="f238d-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
