---
title: Enumerazione COR_PRF_GC_GENERATION
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215898"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="45857-102">Enumerazione COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="45857-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="45857-103">Identifica una generazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="45857-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45857-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45857-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="45857-105">Membri</span><span class="sxs-lookup"><span data-stu-id="45857-105">Members</span></span>  
  
|<span data-ttu-id="45857-106">Member</span><span class="sxs-lookup"><span data-stu-id="45857-106">Member</span></span>|<span data-ttu-id="45857-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45857-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="45857-108">L'oggetto viene archiviato come generazione 0.</span><span class="sxs-lookup"><span data-stu-id="45857-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="45857-109">L'oggetto viene archiviato come generazione 1.</span><span class="sxs-lookup"><span data-stu-id="45857-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="45857-110">L'oggetto viene archiviato come generazione 2.</span><span class="sxs-lookup"><span data-stu-id="45857-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="45857-111">L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="45857-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45857-112">Note</span><span class="sxs-lookup"><span data-stu-id="45857-112">Remarks</span></span>  
 <span data-ttu-id="45857-113">Il garbage collector consente di migliorare le prestazioni di gestione della memoria suddividendo gli oggetti in base all'età generazioni.</span><span class="sxs-lookup"><span data-stu-id="45857-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="45857-114">Attualmente, il garbage collector Usa tre generazioni, numerate 0, 1 e 2, oltre a un segmento dell'heap speciale che viene utilizzato per oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="45857-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="45857-115">Gli oggetti la cui dimensione è maggiore di un particolare valore vengono archiviati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="45857-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="45857-116">Gli altri oggetti allocati iniziano appartengono alla generazione 0.</span><span class="sxs-lookup"><span data-stu-id="45857-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="45857-117">Tutti gli oggetti esistenti dopo la garbage collection nella generazione 0 vengono promossi alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="45857-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="45857-118">Gli oggetti che esistono dopo la garbage collection nella generazione 1 promossi alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="45857-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="45857-119">L'uso di generazioni significa che il garbage collector deve usare solo un subset degli oggetti allocati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="45857-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="45857-120">Il `COR_PRF_GC_GENERATION` enumerazione viene utilizzata per il [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="45857-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45857-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45857-121">Requirements</span></span>  
 <span data-ttu-id="45857-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45857-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45857-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45857-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45857-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45857-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="45857-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="45857-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45857-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45857-126">See also</span></span>

- [<span data-ttu-id="45857-127">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="45857-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
