---
title: Struttura COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178272"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="ef6d3-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="ef6d3-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="ef6d3-103">Contiene statistiche per thread relative alla procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ef6d3-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef6d3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="ef6d3-105">Members</span><span class="sxs-lookup"><span data-stu-id="ef6d3-105">Members</span></span>  
  
|<span data-ttu-id="ef6d3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ef6d3-106">Member</span></span>|<span data-ttu-id="ef6d3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef6d3-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="ef6d3-108">Numero di byte di memoria allocati nel `COR_GC_THREAD_STATS` thread associato all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="ef6d3-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="ef6d3-109">Questo numero viene cancellato a zero ogni volta che si verifica un'operazione di Garbage Collection di generazione zero.</span><span class="sxs-lookup"><span data-stu-id="ef6d3-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="ef6d3-110">Numero di byte promossi a una generazione superiore durante l'operazione di Garbage Collection più recente.</span><span class="sxs-lookup"><span data-stu-id="ef6d3-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef6d3-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef6d3-111">Remarks</span></span>  
 <span data-ttu-id="ef6d3-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="ef6d3-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6d3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef6d3-113">Requirements</span></span>  
 <span data-ttu-id="ef6d3-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef6d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6d3-115">**Intestazione:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="ef6d3-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="ef6d3-116">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef6d3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef6d3-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6d3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6d3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef6d3-118">See also</span></span>

- [<span data-ttu-id="ef6d3-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="ef6d3-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="ef6d3-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="ef6d3-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
