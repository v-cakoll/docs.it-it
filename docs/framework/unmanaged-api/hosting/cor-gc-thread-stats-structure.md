---
title: Struttura COR_GC_THREAD_STATS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266352984cf50dc906e77598e8dcc9216526ce17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="77a35-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="77a35-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="77a35-103">Contiene le statistiche per ogni thread relative alla garbage collection.</span><span class="sxs-lookup"><span data-stu-id="77a35-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77a35-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="77a35-105">Membri</span><span class="sxs-lookup"><span data-stu-id="77a35-105">Members</span></span>  
  
|<span data-ttu-id="77a35-106">Membro</span><span class="sxs-lookup"><span data-stu-id="77a35-106">Member</span></span>|<span data-ttu-id="77a35-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77a35-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="77a35-108">Il numero di byte di memoria allocata nel thread in cui è associato all'oggetto corrente `COR_GC_THREAD_STATS` istanza.</span><span class="sxs-lookup"><span data-stu-id="77a35-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="77a35-109">Questo numero è impostato su zero ogni volta che si verifica una generazione 0 garbage collection.</span><span class="sxs-lookup"><span data-stu-id="77a35-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="77a35-110">Il numero di byte promossi a una generazione superiore più recente operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="77a35-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77a35-111">Note</span><span class="sxs-lookup"><span data-stu-id="77a35-111">Remarks</span></span>  
 <span data-ttu-id="77a35-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="77a35-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a35-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77a35-113">Requirements</span></span>  
 <span data-ttu-id="77a35-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77a35-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a35-115">**Intestazione:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="77a35-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="77a35-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77a35-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77a35-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a35-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77a35-118">See Also</span></span>  
 [<span data-ttu-id="77a35-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="77a35-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="77a35-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="77a35-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
