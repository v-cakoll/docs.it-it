---
title: Enumerazione COR_PRF_GC_GENERATION
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION
helpviewer_keywords: COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69eec0c2dfccacee4c54c9f2493da523812259aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="7d019-102">Enumerazione COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="7d019-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="7d019-103">Identifica una generazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7d019-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d019-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d019-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="7d019-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7d019-105">Members</span></span>  
  
|<span data-ttu-id="7d019-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7d019-106">Member</span></span>|<span data-ttu-id="7d019-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d019-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="7d019-108">L'oggetto viene archiviato come generazione 0.</span><span class="sxs-lookup"><span data-stu-id="7d019-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="7d019-109">L'oggetto viene archiviato come generazione 1.</span><span class="sxs-lookup"><span data-stu-id="7d019-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="7d019-110">L'oggetto viene archiviato come generazione 2.</span><span class="sxs-lookup"><span data-stu-id="7d019-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="7d019-111">L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7d019-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d019-112">Note</span><span class="sxs-lookup"><span data-stu-id="7d019-112">Remarks</span></span>  
 <span data-ttu-id="7d019-113">Il garbage collector consente di migliorare le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età.</span><span class="sxs-lookup"><span data-stu-id="7d019-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="7d019-114">Il garbage collector attualmente utilizza tre generazioni, numerate 0, 1 e 2, oltre a un segmento di un heap speciale che viene utilizzato per oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7d019-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="7d019-115">Gli oggetti la cui dimensione è maggiore di un particolare valore vengono archiviati nell'heap degli oggetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7d019-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="7d019-116">Gli altri oggetti allocati inizialmente appartengono alla generazione 0.</span><span class="sxs-lookup"><span data-stu-id="7d019-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="7d019-117">Tutti gli oggetti esistenti dopo la garbage collection nella generazione 0 vengono promossi alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="7d019-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="7d019-118">Gli oggetti che esistono dopo la garbage collection nella generazione 1 promossi alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="7d019-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="7d019-119">L'utilizzo di generazioni significa che il garbage collector deve utilizzare solo un subset degli oggetti allocati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="7d019-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="7d019-120">Il `COR_PRF_GC_GENERATION` enumerazione viene utilizzata per la [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="7d019-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d019-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d019-121">Requirements</span></span>  
 <span data-ttu-id="7d019-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d019-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d019-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d019-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d019-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d019-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d019-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d019-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d019-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d019-126">See Also</span></span>  
 [<span data-ttu-id="7d019-127">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="7d019-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
