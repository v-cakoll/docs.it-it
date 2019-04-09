---
title: Metodo ICorProfilerInfo2::GetObjectGeneration
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64e362be57a96bbe0f61b964ab413234f30d0ed1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143780"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="b0bc3-102">Metodo ICorProfilerInfo2::GetObjectGeneration</span><span class="sxs-lookup"><span data-stu-id="b0bc3-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="b0bc3-103">Ottiene il segmento dell'heap che contiene l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="b0bc3-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0bc3-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0bc3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0bc3-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="b0bc3-106">[in] L'ID dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b0bc3-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="b0bc3-107">[out] Un puntatore a un [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struttura, che descrive un intervallo (vale a dire, un blocco) di memoria all'interno della generazione viene sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b0bc3-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="b0bc3-108">Questo intervallo contiene l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="b0bc3-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0bc3-109">Note</span><span class="sxs-lookup"><span data-stu-id="b0bc3-109">Remarks</span></span>  
 <span data-ttu-id="b0bc3-110">Il `GetObjectGeneration` metodo può essere chiamato da qualsiasi callback del profiler, purché non sia in corso operazioni di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b0bc3-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="b0bc3-111">Vale a dire, può essere chiamato da qualsiasi callback a eccezione di quelli che si verificano tra [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) e [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="b0bc3-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bc3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0bc3-112">Requirements</span></span>  
 <span data-ttu-id="b0bc3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0bc3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0bc3-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0bc3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0bc3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0bc3-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b0bc3-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b0bc3-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0bc3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0bc3-117">See also</span></span>

- [<span data-ttu-id="b0bc3-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b0bc3-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b0bc3-119">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b0bc3-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
