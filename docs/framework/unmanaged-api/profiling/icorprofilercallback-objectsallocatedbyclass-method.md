---
title: Metodo ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4229332ef3a079a5a294e27b624dde0e1fb46691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782960"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="683f5-102">Metodo ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="683f5-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="683f5-103">Notifica al profiler sul numero di istanze di ogni classe specificata che sono stati creati dopo l'ultima garbage collection.</span><span class="sxs-lookup"><span data-stu-id="683f5-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="683f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="683f5-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="683f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="683f5-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="683f5-106">[in] Le dimensioni dei `classIds` e `cObjects` matrici.</span><span class="sxs-lookup"><span data-stu-id="683f5-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="683f5-107">[in] Matrice di ID, dove ogni ID specifica una classe con una o più istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="683f5-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="683f5-108">[in] Matrice di interi, in cui ogni integer che specifica il numero di istanze per la classe corrispondente nel `classIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="683f5-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="683f5-109">Note</span><span class="sxs-lookup"><span data-stu-id="683f5-109">Remarks</span></span>  
 <span data-ttu-id="683f5-110">Il `classIds` e `cObjects` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="683f5-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="683f5-111">Ad esempio, `classIds[i]` e `cObjects[i]` fare riferimento alla classe stessa.</span><span class="sxs-lookup"><span data-stu-id="683f5-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="683f5-112">Se non è stata creata alcuna istanza di una classe dopo la precedente di garbage collection, la classe viene omesso.</span><span class="sxs-lookup"><span data-stu-id="683f5-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="683f5-113">Il `ObjectsAllocatedByClass` callback non segnalerà gli oggetti allocati nell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="683f5-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="683f5-114">I numeri di segnalati da `ObjectsAllocatedByClass` sono solo una stima.</span><span class="sxs-lookup"><span data-stu-id="683f5-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="683f5-115">Per i conteggi esatti, utilizzare [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="683f5-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="683f5-116">Il `classIds` matrice può contenere una o più voci null se il corrispondente `cObjects` matrice dispone di tipi in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="683f5-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="683f5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="683f5-117">Requirements</span></span>  
 <span data-ttu-id="683f5-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="683f5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="683f5-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="683f5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="683f5-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="683f5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="683f5-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="683f5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683f5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="683f5-122">See also</span></span>

- [<span data-ttu-id="683f5-123">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="683f5-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
