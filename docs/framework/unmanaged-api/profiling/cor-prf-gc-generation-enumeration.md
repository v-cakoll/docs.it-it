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
ms.openlocfilehash: 0eb1f57e3505f9ce5bb8b831d30c3891e51097c3
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158567"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="71bff-102">Enumerazione COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="71bff-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="71bff-103">Identifica una generazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71bff-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71bff-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="71bff-105">Members</span><span class="sxs-lookup"><span data-stu-id="71bff-105">Members</span></span>  
  
|<span data-ttu-id="71bff-106">Membro</span><span class="sxs-lookup"><span data-stu-id="71bff-106">Member</span></span>|<span data-ttu-id="71bff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71bff-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="71bff-108">L'oggetto viene archiviato come generazione 0.</span><span class="sxs-lookup"><span data-stu-id="71bff-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="71bff-109">L'oggetto viene archiviato come generazione 1.</span><span class="sxs-lookup"><span data-stu-id="71bff-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="71bff-110">L'oggetto viene archiviato come generazione 2.</span><span class="sxs-lookup"><span data-stu-id="71bff-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="71bff-111">L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="71bff-111">The object is stored in the large-object heap.</span></span>|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|<span data-ttu-id="71bff-112">L'oggetto viene archiviato nell'heap degli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="71bff-112">The object is stored in the pinned-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71bff-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="71bff-113">Remarks</span></span>  
 <span data-ttu-id="71bff-114">Il Garbage Collector migliora le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età.</span><span class="sxs-lookup"><span data-stu-id="71bff-114">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="71bff-115">Il Garbage Collector utilizza attualmente tre generazioni, numerate 0, 1 e 2, e due segmenti di heap speciali, uno per oggetti di grandi dimensioni e uno per gli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="71bff-115">The garbage collector currently uses three generations, numbered 0, 1, and 2, and two special heap segments, one for large objects and one for pinned objects.</span></span>
  
 <span data-ttu-id="71bff-116">Gli oggetti la cui dimensione è maggiore di un valore soglia vengono archiviati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="71bff-116">Objects whose size is larger than a threshold value are stored in the large-object heap.</span></span> <span data-ttu-id="71bff-117">Gli oggetti bloccati possono essere allocati all'heap degli oggetti bloccati per evitare il costo delle prestazioni di allocazione di tali oggetti negli heap normali.</span><span class="sxs-lookup"><span data-stu-id="71bff-117">Pinned objects can be allocated to the pinned-object heap to avoid the performance cost of allocating them on the normal heaps.</span></span> <span data-ttu-id="71bff-118">Altri oggetti allocati iniziano a appartenere alla generazione 0.</span><span class="sxs-lookup"><span data-stu-id="71bff-118">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="71bff-119">Tutti gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 0 vengono promossi alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="71bff-119">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="71bff-120">Gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 1 passano alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="71bff-120">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="71bff-121">L'uso di generazioni significa che il Garbage Collector deve lavorare solo con un subset degli oggetti allocati in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="71bff-121">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="71bff-122">L' `COR_PRF_GC_GENERATION` enumerazione viene utilizzata dalla struttura [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="71bff-122">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71bff-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71bff-123">Requirements</span></span>  
 <span data-ttu-id="71bff-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71bff-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bff-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71bff-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71bff-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71bff-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71bff-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bff-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bff-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="71bff-128">See also</span></span>

- [<span data-ttu-id="71bff-129">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="71bff-129">Profiling Enumerations</span></span>](profiling-enumerations.md)
