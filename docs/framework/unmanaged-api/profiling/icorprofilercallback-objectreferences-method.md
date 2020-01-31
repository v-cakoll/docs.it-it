---
title: Metodo ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866091"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="bf060-102">Metodo ICorProfilerCallback::ObjectReferences</span><span class="sxs-lookup"><span data-stu-id="bf060-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="bf060-103">Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="bf060-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf060-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf060-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf060-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf060-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bf060-106">in ID dell'oggetto che fa riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="bf060-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="bf060-107">in ID della classe di cui l'oggetto specificato è un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="bf060-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="bf060-108">in Numero di oggetti a cui fa riferimento l'oggetto specificato (ovvero il numero di elementi nella matrice di `objectRefIds`).</span><span class="sxs-lookup"><span data-stu-id="bf060-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="bf060-109">in Matrice di ID di oggetti a cui fa riferimento `objectId`.</span><span class="sxs-lookup"><span data-stu-id="bf060-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf060-110">Note</span><span class="sxs-lookup"><span data-stu-id="bf060-110">Remarks</span></span>  
 <span data-ttu-id="bf060-111">Il metodo `ObjectReferences` viene chiamato per ogni oggetto rimanente nell'heap dopo il completamento di un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bf060-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="bf060-112">Se il profiler restituisce un errore da questo callback, i servizi di profilatura non richiameranno questo callback fino al Garbage Collection successivo.</span><span class="sxs-lookup"><span data-stu-id="bf060-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="bf060-113">Il callback di `ObjectReferences` può essere usato insieme al callback [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) per creare un grafico completo di riferimento all'oggetto per il Runtime.</span><span class="sxs-lookup"><span data-stu-id="bf060-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="bf060-114">Il Common Language Runtime (CLR) garantisce che ogni riferimento a un oggetto venga segnalato solo una volta dal metodo `ObjectReferences`.</span><span class="sxs-lookup"><span data-stu-id="bf060-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="bf060-115">Gli ID oggetto restituiti da `ObjectReferences` non sono validi durante il callback stesso, perché il Garbage Collection potrebbe trovarsi durante lo spostamento di oggetti.</span><span class="sxs-lookup"><span data-stu-id="bf060-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="bf060-116">Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una chiamata `ObjectReferences`.</span><span class="sxs-lookup"><span data-stu-id="bf060-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="bf060-117">Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , il Garbage Collection è completo e l'ispezione può essere eseguita in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="bf060-117">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="bf060-118">Un `ClassId` null indica che `objectId` dispone di un tipo che sta scaricando.</span><span class="sxs-lookup"><span data-stu-id="bf060-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf060-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bf060-119">Requirements</span></span>  
 <span data-ttu-id="bf060-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf060-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf060-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf060-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf060-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf060-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf060-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf060-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf060-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf060-124">See also</span></span>

- [<span data-ttu-id="bf060-125">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bf060-125">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
