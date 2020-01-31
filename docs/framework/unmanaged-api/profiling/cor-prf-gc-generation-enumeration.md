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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867211"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="a5338-102">Enumerazione COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="a5338-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="a5338-103">Identifica una generazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a5338-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5338-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5338-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="a5338-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a5338-105">Members</span></span>  
  
|<span data-ttu-id="a5338-106">Member</span><span class="sxs-lookup"><span data-stu-id="a5338-106">Member</span></span>|<span data-ttu-id="a5338-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5338-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="a5338-108">L'oggetto viene archiviato come generazione 0.</span><span class="sxs-lookup"><span data-stu-id="a5338-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="a5338-109">L'oggetto viene archiviato come generazione 1.</span><span class="sxs-lookup"><span data-stu-id="a5338-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="a5338-110">L'oggetto viene archiviato come generazione 2.</span><span class="sxs-lookup"><span data-stu-id="a5338-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="a5338-111">L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a5338-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5338-112">Note</span><span class="sxs-lookup"><span data-stu-id="a5338-112">Remarks</span></span>  
 <span data-ttu-id="a5338-113">Il Garbage Collector migliora le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età.</span><span class="sxs-lookup"><span data-stu-id="a5338-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="a5338-114">Il Garbage Collector utilizza attualmente tre generazioni, numerate 0, 1 e 2, più uno speciale segmento di heap utilizzato per oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a5338-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="a5338-115">Gli oggetti la cui dimensione è maggiore di un determinato valore vengono archiviati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a5338-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="a5338-116">Altri oggetti allocati iniziano a appartenere alla generazione 0.</span><span class="sxs-lookup"><span data-stu-id="a5338-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="a5338-117">Tutti gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 0 vengono promossi alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="a5338-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="a5338-118">Gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 1 passano alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="a5338-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="a5338-119">L'uso di generazioni significa che il Garbage Collector deve lavorare solo con un subset degli oggetti allocati in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="a5338-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="a5338-120">L'enumerazione `COR_PRF_GC_GENERATION` viene utilizzata dalla struttura di [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="a5338-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5338-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a5338-121">Requirements</span></span>  
 <span data-ttu-id="a5338-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5338-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5338-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5338-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5338-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5338-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5338-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5338-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5338-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5338-126">See also</span></span>

- [<span data-ttu-id="a5338-127">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="a5338-127">Profiling Enumerations</span></span>](profiling-enumerations.md)
