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
ms.openlocfilehash: d01b864be231e5b0a3fd72dc2f3636a87c8cae83
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448636"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="28816-102">Enumerazione COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="28816-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="28816-103">Identifica una generazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="28816-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28816-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28816-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="28816-105">Members</span><span class="sxs-lookup"><span data-stu-id="28816-105">Members</span></span>  
  
|<span data-ttu-id="28816-106">Membro</span><span class="sxs-lookup"><span data-stu-id="28816-106">Member</span></span>|<span data-ttu-id="28816-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28816-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="28816-108">L'oggetto viene archiviato come generazione 0.</span><span class="sxs-lookup"><span data-stu-id="28816-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="28816-109">L'oggetto viene archiviato come generazione 1.</span><span class="sxs-lookup"><span data-stu-id="28816-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="28816-110">L'oggetto viene archiviato come generazione 2.</span><span class="sxs-lookup"><span data-stu-id="28816-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="28816-111">L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="28816-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28816-112">Note</span><span class="sxs-lookup"><span data-stu-id="28816-112">Remarks</span></span>  
 <span data-ttu-id="28816-113">Il Garbage Collector migliora le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età.</span><span class="sxs-lookup"><span data-stu-id="28816-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="28816-114">Il Garbage Collector utilizza attualmente tre generazioni, numerate 0, 1 e 2, più uno speciale segmento di heap utilizzato per oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="28816-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="28816-115">Gli oggetti la cui dimensione è maggiore di un determinato valore vengono archiviati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="28816-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="28816-116">Altri oggetti allocati iniziano a appartenere alla generazione 0.</span><span class="sxs-lookup"><span data-stu-id="28816-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="28816-117">Tutti gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 0 vengono promossi alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="28816-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="28816-118">Gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 1 passano alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="28816-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="28816-119">L'uso di generazioni significa che il Garbage Collector deve lavorare solo con un subset degli oggetti allocati in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="28816-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="28816-120">L'enumerazione `COR_PRF_GC_GENERATION` viene utilizzata dalla struttura di [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="28816-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28816-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28816-121">Requirements</span></span>  
 <span data-ttu-id="28816-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28816-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28816-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28816-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28816-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28816-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28816-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28816-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28816-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28816-126">See also</span></span>

- [<span data-ttu-id="28816-127">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="28816-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
