---
title: Metodo ICorProfilerCallback::ObjectsAllocatedByClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28c0ff537a5b2133bdeb1db8aeadf5545d8dfd0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="fc5c3-102">Metodo ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="fc5c3-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="fc5c3-103">Notifica al profiler il numero di istanze di ogni classe specificata che sono stati creati dall'operazione di garbage collection più recente.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc5c3-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc5c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc5c3-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="fc5c3-106">[in] Le dimensioni del `classIds` e `cObjects` matrici.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="fc5c3-107">[in] Matrice di ID, in cui ogni ID specifica una classe con una o più istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="fc5c3-108">[in] Una matrice di interi, in cui ogni integer che specifica il numero di istanze per la classe corrispondente nel `classIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc5c3-109">Note</span><span class="sxs-lookup"><span data-stu-id="fc5c3-109">Remarks</span></span>  
 <span data-ttu-id="fc5c3-110">Il `classIds` e `cObjects` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="fc5c3-111">Ad esempio, `classIds[i]` e `cObjects[i]` riferimento alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="fc5c3-112">Se nessuna istanza di una classe è stata creata dall'operazione di garbage collection precedente, la classe viene omesso.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="fc5c3-113">Il `ObjectsAllocatedByClass` callback non segnalerà gli oggetti allocati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="fc5c3-114">I numeri segnalati da `ObjectsAllocatedByClass` sono solo stime.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="fc5c3-115">Per i conteggi esatti, utilizzare [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="fc5c3-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="fc5c3-116">Il `classIds` matrice può contenere uno o più voci null se il corrispondente `cObjects` matrice dispone di tipi in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="fc5c3-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5c3-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc5c3-117">Requirements</span></span>  
 <span data-ttu-id="fc5c3-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc5c3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5c3-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc5c3-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc5c3-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc5c3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc5c3-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5c3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5c3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc5c3-122">See Also</span></span>  
 [<span data-ttu-id="fc5c3-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fc5c3-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
