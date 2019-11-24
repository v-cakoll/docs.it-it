---
title: Metodo ICorProfilerInfo2::GetGenerationBounds
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 11157bca2d0f0be2b9b9bc36c382188a43db22a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433121"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="c1606-102">Metodo ICorProfilerInfo2::GetGenerationBounds</span><span class="sxs-lookup"><span data-stu-id="c1606-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="c1606-103">Ottiene le aree di memoria, ovvero i segmenti dell'heap, che costituiscono le diverse generazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c1606-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1606-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1606-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1606-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1606-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="c1606-106">[in] Numero di elementi allocati dal chiamante per la matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="c1606-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="c1606-107">[out] Puntatore a un intero che specifica il numero complessivo di intervalli restituiti, interamente o in parte, nella matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="c1606-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="c1606-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c1606-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1606-109">Note</span><span class="sxs-lookup"><span data-stu-id="c1606-109">Remarks</span></span>  
 <span data-ttu-id="c1606-110">Il metodo `GetGenerationBounds` può essere chiamato da qualsiasi callback del profiler, purché non sia in corso un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c1606-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="c1606-111">La maggior parte delle modifiche di generazione si verifica durante le operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c1606-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="c1606-112">Le generazioni possono aumentare tra un'operazione di Garbage Collection e l'altra, ma in genere non si spostano.</span><span class="sxs-lookup"><span data-stu-id="c1606-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="c1606-113">I punti più interessanti in cui chiamare `GetGenerationBounds` sono quindi `ICorProfilerCallback2::GarbageCollectionStarted` e `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="c1606-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="c1606-114">Durante l'avvio del programma, alcuni oggetti vengono allocati direttamente da Common Language Runtime, di solito nelle generazioni 3 e 0.</span><span class="sxs-lookup"><span data-stu-id="c1606-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="c1606-115">In questo modo, prima che inizi l'esecuzione del codice gestito, queste generazioni conterranno già oggetti.</span><span class="sxs-lookup"><span data-stu-id="c1606-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="c1606-116">Le generazioni 1 e 2 in genere restano vuote, a eccezione degli oggetti fittizi generati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="c1606-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="c1606-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="c1606-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="c1606-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span><span class="sxs-lookup"><span data-stu-id="c1606-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="c1606-119">Questa funzione usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="c1606-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1606-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1606-120">Requirements</span></span>  
 <span data-ttu-id="c1606-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1606-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1606-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1606-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1606-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1606-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1606-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1606-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1606-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1606-125">See also</span></span>

- [<span data-ttu-id="c1606-126">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c1606-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c1606-127">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c1606-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="c1606-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c1606-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c1606-129">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c1606-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
