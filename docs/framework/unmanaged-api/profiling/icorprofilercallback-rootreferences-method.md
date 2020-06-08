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
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499909"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="29ace-102">Metodo ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="29ace-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="29ace-103">Notifica al profiler informazioni sui riferimenti radice dopo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="29ace-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ace-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29ace-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="29ace-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29ace-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="29ace-106">in Numero di riferimenti nella `rootRefIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="29ace-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="29ace-107">in Matrice di ID oggetto che fanno riferimento a un oggetto statico o a un oggetto nello stack.</span><span class="sxs-lookup"><span data-stu-id="29ace-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29ace-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="29ace-108">Remarks</span></span>  
 <span data-ttu-id="29ace-109">`RootReferences`E [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) vengono chiamati per inviare una notifica al profiler.</span><span class="sxs-lookup"><span data-stu-id="29ace-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="29ace-110">I profiler in genere implementano uno o l'altro, ma non entrambi, perché le informazioni passate `RootReferences2` sono un superset di quello passato `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="29ace-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="29ace-111">È possibile che la `rootRefIds` matrice contenga un oggetto null.</span><span class="sxs-lookup"><span data-stu-id="29ace-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="29ace-112">Ad esempio, tutti i riferimenti a oggetti dichiarati nello stack vengono considerati come radici dal Garbage Collector e verranno sempre segnalati.</span><span class="sxs-lookup"><span data-stu-id="29ace-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="29ace-113">Gli ID oggetto restituiti da `RootReferences` non sono validi durante il callback stesso, perché è possibile che il Garbage Collection stia spostando gli oggetti dagli indirizzi precedenti ai nuovi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="29ace-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="29ace-114">Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una `RootReferences` chiamata.</span><span class="sxs-lookup"><span data-stu-id="29ace-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="29ace-115">Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="29ace-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ace-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29ace-116">Requirements</span></span>  
 <span data-ttu-id="29ace-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29ace-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ace-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29ace-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29ace-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29ace-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29ace-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ace-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ace-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29ace-121">See also</span></span>

- [<span data-ttu-id="29ace-122">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="29ace-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
