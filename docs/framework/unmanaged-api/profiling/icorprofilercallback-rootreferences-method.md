---
title: Metodo ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cfab1d716b5a8b530561e2dc72442591eb0d8e42
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499030"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="e7e37-102">Metodo ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="e7e37-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="e7e37-103">Notifica al profiler con le informazioni sui riferimenti principali dopo l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e7e37-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7e37-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7e37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7e37-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="e7e37-106">[in] Il numero di riferimenti nel `rootRefIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="e7e37-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="e7e37-107">[in] Matrice di ID di oggetto che fanno riferimento a un oggetto statico o un oggetto nello stack.</span><span class="sxs-lookup"><span data-stu-id="e7e37-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7e37-108">Note</span><span class="sxs-lookup"><span data-stu-id="e7e37-108">Remarks</span></span>  
 <span data-ttu-id="e7e37-109">Entrambe `RootReferences` e [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) vengono chiamati per notificare al profiler.</span><span class="sxs-lookup"><span data-stu-id="e7e37-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="e7e37-110">I profiler in genere implementano uno o l'altro, ma non entrambi, poiché le informazioni inviate `RootReferences2` è un superset di che passato `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="e7e37-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="e7e37-111">È possibile che il `rootRefIds` matrice per contenere un oggetto null.</span><span class="sxs-lookup"><span data-stu-id="e7e37-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="e7e37-112">Ad esempio, tutti i riferimenti all'oggetto dichiarati nello stack vengono gestiti dal garbage collector come radici e verrà segnalati sempre.</span><span class="sxs-lookup"><span data-stu-id="e7e37-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="e7e37-113">L'ID di oggetto restituito da `RootReferences` nejsou platné durante il callback vero e proprio, perché l'operazione di garbage collection stia ancora spostando gli oggetti provenienti da indirizzi precedenti per i nuovi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="e7e37-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="e7e37-114">Pertanto, profiler non deve tentare di controllare gli oggetti durante una `RootReferences` chiamare.</span><span class="sxs-lookup"><span data-stu-id="e7e37-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="e7e37-115">Quando [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) viene chiamato, tutti gli oggetti sono stati spostati nelle nuove posizioni e può essere controllati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="e7e37-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e37-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7e37-116">Requirements</span></span>  
 <span data-ttu-id="e7e37-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e37-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e37-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7e37-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7e37-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7e37-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7e37-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e37-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e37-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7e37-121">See also</span></span>
- [<span data-ttu-id="e7e37-122">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e7e37-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
