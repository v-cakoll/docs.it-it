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
ms.openlocfilehash: f025f4c0bc0ec8e11decddcdf64be50f68955266
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499805"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="ddcae-102">Metodo ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="ddcae-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="ddcae-103">Notifica all'Code Profiler che Garbage Collection è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="ddcae-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddcae-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddcae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ddcae-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="ddcae-106">in Il numero totale di voci nella `generationCollected` matrice.</span><span class="sxs-lookup"><span data-stu-id="ddcae-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="ddcae-107">in Matrice di valori booleani, che è `true` se la generazione che corrisponde all'indice della matrice viene raccolta da questo Garbage Collection; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ddcae-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="ddcae-108">La matrice viene indicizzata in base a un valore dell'enumerazione [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , che indica la generazione.</span><span class="sxs-lookup"><span data-stu-id="ddcae-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="ddcae-109">in Valore dell'enumerazione [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) che indica il motivo per cui è stato indotto l'Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ddcae-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddcae-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ddcae-110">Remarks</span></span>  
 <span data-ttu-id="ddcae-111">Tutti i callback relativi a questo Garbage Collection si verificheranno tra il `GarbageCollectionStarted` callback e il callback [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ddcae-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="ddcae-112">Questi callback non devono essere eseguiti nello stesso thread.</span><span class="sxs-lookup"><span data-stu-id="ddcae-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="ddcae-113">Il profiler può ispezionare gli oggetti nei percorsi originali durante il `GarbageCollectionStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="ddcae-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="ddcae-114">Il Garbage Collector inizierà a trasferire gli oggetti dopo il ritorno da `GarbageCollectionStarted` .</span><span class="sxs-lookup"><span data-stu-id="ddcae-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="ddcae-115">Dopo che il profiler ha restituito questo callback, il profiler deve considerare tutti gli ID oggetto come non validi fino a quando non riceve un `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="ddcae-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddcae-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ddcae-116">Requirements</span></span>  
 <span data-ttu-id="ddcae-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddcae-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddcae-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ddcae-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ddcae-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddcae-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddcae-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddcae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcae-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddcae-121">See also</span></span>

- [<span data-ttu-id="ddcae-122">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ddcae-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ddcae-123">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="ddcae-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
