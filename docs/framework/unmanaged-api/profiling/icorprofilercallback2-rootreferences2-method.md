---
title: Metodo ICorProfilerCallback2::RootReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: a9ce9a7a56847efcadf09924ffc56c41f20a1c58
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865727"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="ae4d6-102">Metodo ICorProfilerCallback2::RootReferences2</span><span class="sxs-lookup"><span data-stu-id="ae4d6-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="ae4d6-103">Notifica al profiler i riferimenti radice dopo che si è verificato un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="ae4d6-104">Questo metodo è un'estensione del metodo [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ae4d6-104">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae4d6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae4d6-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae4d6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae4d6-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="ae4d6-107">in Il numero di elementi nelle matrici `rootRefIds`, `rootKinds`, `rootFlags`e `rootIds`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="ae4d6-108">in Matrice di ID oggetto, ognuno dei quali fa riferimento a un oggetto statico o a un oggetto nello stack.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="ae4d6-109">Gli elementi nella matrice di `rootKinds` forniscono informazioni per classificare gli elementi corrispondenti nella matrice di `rootRefIds`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="ae4d6-110">in Matrice di valori di [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) che indicano il tipo di Garbage Collection radice.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-110">[in] An array of [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="ae4d6-111">in Matrice di valori [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) che descrivono le proprietà di un Garbage Collection radice.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="ae4d6-112">in Matrice di valori di UINT_PTR che punta a un Integer che contiene informazioni aggiuntive sulla radice Garbage Collection, a seconda del valore del parametro `rootKinds`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="ae4d6-113">Se il tipo della radice è uno stack, l'ID radice è per la funzione che contiene la variabile.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="ae4d6-114">Se l'ID radice è 0, la funzione è una funzione senza nome che è interna a CLR.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="ae4d6-115">Se il tipo della radice è un handle, l'ID radice è per il Garbage Collection handle.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="ae4d6-116">Per gli altri tipi radice, l'ID è un valore opaco e deve essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae4d6-117">Note</span><span class="sxs-lookup"><span data-stu-id="ae4d6-117">Remarks</span></span>  
 <span data-ttu-id="ae4d6-118">Le matrici `rootRefIds`, `rootKinds`, `rootFlags`e `rootIds` sono matrici parallele.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="ae4d6-119">Ovvero `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`e `rootIds[i]` tutti riguardano la stessa radice.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="ae4d6-120">Per notificare al profiler vengono chiamati sia `RootReferences` che `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="ae4d6-121">I profiler in genere implementano un metodo o l'altro, ma non entrambi, perché le informazioni passate in `RootReferences2` sono un superset di passato in `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="ae4d6-122">È possibile che le voci in `rootRefIds` siano pari a zero, il che significa che il riferimento radice corrispondente è null e non fa riferimento a un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="ae4d6-123">Gli ID oggetto restituiti da `RootReferences2` non sono validi durante il callback stesso, perché è possibile che il Garbage Collection stia spostando gli oggetti dagli indirizzi precedenti ai nuovi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="ae4d6-124">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="ae4d6-125">Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="ae4d6-125">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae4d6-126">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ae4d6-126">Requirements</span></span>  
 <span data-ttu-id="ae4d6-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae4d6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae4d6-128">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae4d6-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae4d6-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae4d6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae4d6-130">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae4d6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4d6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae4d6-131">See also</span></span>

- [<span data-ttu-id="ae4d6-132">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ae4d6-132">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ae4d6-133">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="ae4d6-133">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
