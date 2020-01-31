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
ms.openlocfilehash: 3cdc185408576f5679daacef4dde438d66e490ff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862750"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="3be5a-102">Metodo ICorProfilerInfo2::GetGenerationBounds</span><span class="sxs-lookup"><span data-stu-id="3be5a-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="3be5a-103">Ottiene le aree di memoria, ovvero i segmenti dell'heap, che costituiscono le diverse generazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3be5a-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3be5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3be5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3be5a-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="3be5a-106">[in] Numero di elementi allocati dal chiamante per la matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="3be5a-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="3be5a-107">[out] Puntatore a un intero che specifica il numero complessivo di intervalli restituiti, interamente o in parte, nella matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="3be5a-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="3be5a-108">out Matrice di strutture di [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , ognuna delle quali descrive un intervallo, ovvero un blocco, della memoria all'interno della generazione che è in fase di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3be5a-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3be5a-109">Note</span><span class="sxs-lookup"><span data-stu-id="3be5a-109">Remarks</span></span>  
 <span data-ttu-id="3be5a-110">Il metodo `GetGenerationBounds` può essere chiamato da qualsiasi callback del profiler, purché non sia in corso un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3be5a-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="3be5a-111">La maggior parte delle modifiche di generazione si verifica durante le operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3be5a-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="3be5a-112">Le generazioni possono aumentare tra un'operazione di Garbage Collection e l'altra, ma in genere non si spostano.</span><span class="sxs-lookup"><span data-stu-id="3be5a-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="3be5a-113">I punti più interessanti in cui chiamare `GetGenerationBounds` sono quindi `ICorProfilerCallback2::GarbageCollectionStarted` e `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="3be5a-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="3be5a-114">Durante l'avvio del programma, alcuni oggetti vengono allocati direttamente da Common Language Runtime, di solito nelle generazioni 3 e 0.</span><span class="sxs-lookup"><span data-stu-id="3be5a-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="3be5a-115">In questo modo, prima che inizi l'esecuzione del codice gestito, queste generazioni conterranno già oggetti.</span><span class="sxs-lookup"><span data-stu-id="3be5a-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="3be5a-116">Le generazioni 1 e 2 in genere restano vuote, a eccezione degli oggetti fittizi generati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="3be5a-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="3be5a-117">(La dimensione degli oggetti fittizi è 12 byte nelle implementazioni a 32 bit di CLR; le dimensioni sono maggiori nelle implementazioni a 64 bit). È anche possibile vedere gli intervalli di generazione 2 che si trovano all'interno dei moduli prodotti dal generatore di immagini native (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="3be5a-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="3be5a-118">In questo caso, gli oggetti della generazione 2 sono *oggetti bloccati*, che vengono allocati quando viene eseguito Ngen. exe anziché dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="3be5a-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="3be5a-119">Questa funzione usa buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3be5a-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be5a-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3be5a-120">Requirements</span></span>  
 <span data-ttu-id="3be5a-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3be5a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3be5a-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3be5a-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3be5a-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3be5a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3be5a-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3be5a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be5a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3be5a-125">See also</span></span>

- [<span data-ttu-id="3be5a-126">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3be5a-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3be5a-127">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="3be5a-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="3be5a-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3be5a-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3be5a-129">Profilatura</span><span class="sxs-lookup"><span data-stu-id="3be5a-129">Profiling</span></span>](index.md)
