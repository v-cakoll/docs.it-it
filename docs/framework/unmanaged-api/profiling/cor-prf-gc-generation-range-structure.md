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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 646c4e37a7fab503a26557f9fdfc926b1186b17b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775046"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="c3e8a-102">Struttura COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="c3e8a-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="c3e8a-103">Descrive un intervallo, ovvero un blocco, di memoria sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3e8a-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="c3e8a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c3e8a-105">Members</span></span>  
  
|<span data-ttu-id="c3e8a-106">Member</span><span class="sxs-lookup"><span data-stu-id="c3e8a-106">Member</span></span>|<span data-ttu-id="c3e8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3e8a-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="c3e8a-108">Valore di [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumerazione che specifica la generazione in cui il blocco di memoria a cui appartiene.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="c3e8a-109">ID dell'oggetto che specifica la posizione iniziale del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="c3e8a-110">Un puntatore a un intero che specifica la dimensione alla parte usata del blocco di memoria (vale a dire, la quantità di memoria utilizzata all'interno del blocco).</span><span class="sxs-lookup"><span data-stu-id="c3e8a-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="c3e8a-111">Un puntatore a un integer che specifica la dimensione del blocco di memoria (vale a dire, la quantità di memoria riservata per il blocco).</span><span class="sxs-lookup"><span data-stu-id="c3e8a-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3e8a-112">Note</span><span class="sxs-lookup"><span data-stu-id="c3e8a-112">Remarks</span></span>  
 <span data-ttu-id="c3e8a-113">Il `rangeLength` valore è sicuramente accurata solo se [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) oppure [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), entrambi delle quali usano la `COR_PRF_GC_GENERATION_RANGE` struttura, viene chiamato dal [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) o nella [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c3e8a-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3e8a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3e8a-114">Requirements</span></span>  
 <span data-ttu-id="c3e8a-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3e8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3e8a-116">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c3e8a-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c3e8a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3e8a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3e8a-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3e8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e8a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3e8a-119">See also</span></span>

- [<span data-ttu-id="c3e8a-120">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="c3e8a-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
