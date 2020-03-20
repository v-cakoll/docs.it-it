---
title: Struttura COR_GC_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176526"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="f161b-102">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="f161b-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="f161b-103">Fornisce statistiche sul meccanismo di Garbage Collection di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f161b-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f161b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f161b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="f161b-105">Members</span><span class="sxs-lookup"><span data-stu-id="f161b-105">Members</span></span>  
  
|<span data-ttu-id="f161b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f161b-106">Member</span></span>|<span data-ttu-id="f161b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f161b-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="f161b-108">Indica quali valori di campo devono essere calcolati e restituiti.</span><span class="sxs-lookup"><span data-stu-id="f161b-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="f161b-109">Indica il numero di operazioni di Garbage Collection forzate dalla richiesta esterna.</span><span class="sxs-lookup"><span data-stu-id="f161b-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="f161b-110">Indica il numero di operazioni di Garbage Collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="f161b-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="f161b-111">Numero totale di kilobyte di cui è stato eseguito il commit in tutti gli heap.</span><span class="sxs-lookup"><span data-stu-id="f161b-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="f161b-112">Numero totale di kilobyte riservati in tutti gli heap.</span><span class="sxs-lookup"><span data-stu-id="f161b-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="f161b-113">Dimensione, in kilobyte, dell'heap di generazione zero.</span><span class="sxs-lookup"><span data-stu-id="f161b-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="f161b-114">Dimensione, in kilobyte, dell'heap di generazione uno.</span><span class="sxs-lookup"><span data-stu-id="f161b-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="f161b-115">Dimensione, in kilobyte, dell'heap di generazione due.</span><span class="sxs-lookup"><span data-stu-id="f161b-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="f161b-116">Dimensione, in kilobyte, dell'heap oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="f161b-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="f161b-117">Dimensioni, in kilobyte, degli oggetti promossi dalla generazione zero alla generazione uno.</span><span class="sxs-lookup"><span data-stu-id="f161b-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="f161b-118">Dimensioni, in kilobyte, degli oggetti promossi dalla generazione uno alla generazione due.</span><span class="sxs-lookup"><span data-stu-id="f161b-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f161b-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f161b-119">Remarks</span></span>  
 <span data-ttu-id="f161b-120">Il metodo [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) richiede che il `Flags` campo della `COR_GC_STATS` struttura sia impostato su uno o più valori dell'enumerazione [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) per specificare quali statistiche devono essere impostate.</span><span class="sxs-lookup"><span data-stu-id="f161b-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="f161b-121">Nella tabella seguente le statistiche fornite da questa struttura `COR_GC_COUNTS` `COR_GC_MEMORYUSAGE`vengono mappate ai due valori di enumerazione [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) e .</span><span class="sxs-lookup"><span data-stu-id="f161b-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="f161b-122">Specificato da COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="f161b-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="f161b-123">Specificato da COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="f161b-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="f161b-124">Di seguito è riportato un esempio di utilizzo:An example of the usage is as follows:</span><span class="sxs-lookup"><span data-stu-id="f161b-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f161b-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f161b-125">Requirements</span></span>  
 <span data-ttu-id="f161b-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f161b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f161b-127">**Intestazione:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="f161b-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="f161b-128">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f161b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f161b-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f161b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f161b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f161b-130">See also</span></span>

- [<span data-ttu-id="f161b-131">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="f161b-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="f161b-132">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="f161b-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="f161b-133">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="f161b-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
