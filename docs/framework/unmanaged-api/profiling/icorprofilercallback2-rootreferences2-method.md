---
title: Metodo ICorProfilerCallback2::RootReferences2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.RootReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a0b2e23ba586e7a20ed11de6433b2d87cbe7219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="56dea-102">Metodo ICorProfilerCallback2::RootReferences2</span><span class="sxs-lookup"><span data-stu-id="56dea-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="56dea-103">Notifica al profiler sui riferimenti principali dopo un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="56dea-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="56dea-104">Questo metodo è un'estensione del [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="56dea-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56dea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56dea-105">Syntax</span></span>  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56dea-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="56dea-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="56dea-107">[in] Il numero di elementi di `rootRefIds`, `rootKinds`, `rootFlags`, e `rootIds` matrici.</span><span class="sxs-lookup"><span data-stu-id="56dea-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="56dea-108">[in] Matrice di ID oggetto, ognuno dei quali fa riferimento a un oggetto statico o un oggetto di nello stack.</span><span class="sxs-lookup"><span data-stu-id="56dea-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="56dea-109">Gli elementi di `rootKinds` matrice forniscono informazioni per classificare gli elementi corrispondenti nel `rootRefIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="56dea-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="56dea-110">[in] Matrice di [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) valori che indicano il tipo di radice di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="56dea-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="56dea-111">[in] Matrice di [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) valori che descrivono le proprietà di una radice di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="56dea-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="56dea-112">[in] Una matrice di UINT_PTR valori che puntano a un intero che contiene informazioni aggiuntive sulla radice di garbage collection, in base al valore di `rootKinds` parametro.</span><span class="sxs-lookup"><span data-stu-id="56dea-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="56dea-113">Se il tipo di radice è uno stack, l'ID di radice è per la funzione che contiene la variabile.</span><span class="sxs-lookup"><span data-stu-id="56dea-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="56dea-114">Se l'ID della radice è 0, la funzione è una funzione senza nome all'interna di CLR.</span><span class="sxs-lookup"><span data-stu-id="56dea-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="56dea-115">Se il tipo di radice è un handle, l'ID di radice è per l'handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="56dea-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="56dea-116">Per altri tipi di primo livello, l'ID è un valore opaco e deve essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="56dea-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56dea-117">Note</span><span class="sxs-lookup"><span data-stu-id="56dea-117">Remarks</span></span>  
 <span data-ttu-id="56dea-118">Il `rootRefIds`, `rootKinds`, `rootFlags`, e `rootIds` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="56dea-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="56dea-119">Vale a dire `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, e `rootIds[i]` riguardano la stessa radice.</span><span class="sxs-lookup"><span data-stu-id="56dea-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="56dea-120">Entrambi `RootReferences` e `RootReferences2` vengono chiamati per notificare al profiler.</span><span class="sxs-lookup"><span data-stu-id="56dea-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="56dea-121">I profiler in genere implementano un metodo o l'altro, ma non ad entrambi, in quanto le informazioni passate in `RootReferences2` è un superset di passati `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="56dea-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="56dea-122">È possibile che le voci in `rootRefIds` pari a zero, il che implica che il riferimento alla radice corrispondente è null e non fa riferimento a un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="56dea-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="56dea-123">L'ID di oggetto restituito da `RootReferences2` non validi durante il callback vero e proprio, perché l'operazione di garbage collection potrebbe essere ancora spostando gli oggetti provenienti da indirizzi precedenti a nuovi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="56dea-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="56dea-124">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="56dea-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="56dea-125">Quando [ICorProfilerCallback2::](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) viene chiamato, tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="56dea-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56dea-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56dea-126">Requirements</span></span>  
 <span data-ttu-id="56dea-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56dea-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56dea-128">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56dea-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56dea-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56dea-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56dea-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56dea-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dea-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56dea-131">See Also</span></span>  
 [<span data-ttu-id="56dea-132">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="56dea-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="56dea-133">ICorProfilerCallback2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="56dea-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
