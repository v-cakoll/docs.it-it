---
title: Struttura COR_PRF_GC_GENERATION_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: 682aac9729519e0861ae6e6f60df78a30063c278
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867209"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="a2b95-102">Struttura COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="a2b95-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="a2b95-103">Descrive un intervallo, ovvero un blocco, di memoria sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2b95-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2b95-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="a2b95-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a2b95-105">Members</span></span>  
  
|<span data-ttu-id="a2b95-106">Member</span><span class="sxs-lookup"><span data-stu-id="a2b95-106">Member</span></span>|<span data-ttu-id="a2b95-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2b95-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="a2b95-108">Valore dell'enumerazione [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) che specifica la generazione a cui appartiene il blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="a2b95-108">A value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="a2b95-109">ID di un oggetto che specifica la posizione iniziale del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="a2b95-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="a2b95-110">Puntatore a un intero che specifica la dimensione della parte utilizzata del blocco di memoria, ovvero la quantità di memoria utilizzata nel blocco.</span><span class="sxs-lookup"><span data-stu-id="a2b95-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="a2b95-111">Puntatore a un intero che specifica la dimensione del blocco di memoria, ovvero la quantità di memoria riservata per il blocco.</span><span class="sxs-lookup"><span data-stu-id="a2b95-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2b95-112">Note</span><span class="sxs-lookup"><span data-stu-id="a2b95-112">Remarks</span></span>  
 <span data-ttu-id="a2b95-113">Il valore `rangeLength` garantisce la precisione solo se [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) o [Icorprofilerinfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), che usano entrambi la struttura `COR_PRF_GC_GENERATION_RANGE`, viene chiamato dal metodo [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) o [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a2b95-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b95-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a2b95-114">Requirements</span></span>  
 <span data-ttu-id="a2b95-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2b95-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2b95-116">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="a2b95-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a2b95-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2b95-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2b95-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2b95-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b95-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b95-119">See also</span></span>

- [<span data-ttu-id="a2b95-120">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="a2b95-120">Profiling Structures</span></span>](profiling-structures.md)
