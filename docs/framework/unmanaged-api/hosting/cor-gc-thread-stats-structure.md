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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177736"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="c512a-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="c512a-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="c512a-103">Contiene le statistiche per ogni thread relative alla garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c512a-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c512a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c512a-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="c512a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c512a-105">Members</span></span>  
  
|<span data-ttu-id="c512a-106">Member</span><span class="sxs-lookup"><span data-stu-id="c512a-106">Member</span></span>|<span data-ttu-id="c512a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c512a-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="c512a-108">Il numero di byte di memoria allocata nel thread in cui è associato all'oggetto corrente `COR_GC_THREAD_STATS` istanza.</span><span class="sxs-lookup"><span data-stu-id="c512a-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="c512a-109">Questo numero viene impostato su zero ogni volta che si verifica una da zero la generazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c512a-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="c512a-110">Il numero di byte promossi a una generazione superiore le più recenti di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c512a-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c512a-111">Note</span><span class="sxs-lookup"><span data-stu-id="c512a-111">Remarks</span></span>  
 <span data-ttu-id="c512a-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="c512a-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c512a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c512a-113">Requirements</span></span>  
 <span data-ttu-id="c512a-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c512a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c512a-115">**Intestazione:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="c512a-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="c512a-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c512a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c512a-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c512a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c512a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c512a-118">See also</span></span>

- [<span data-ttu-id="c512a-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="c512a-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="c512a-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c512a-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
