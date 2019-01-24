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
ms.openlocfilehash: 3f453867f6b46265fdbf567b4374ddc64b4efe84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563896"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="92b32-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="92b32-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="92b32-103">Contiene le statistiche per ogni thread relative alla garbage collection.</span><span class="sxs-lookup"><span data-stu-id="92b32-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92b32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92b32-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="92b32-105">Membri</span><span class="sxs-lookup"><span data-stu-id="92b32-105">Members</span></span>  
  
|<span data-ttu-id="92b32-106">Membro</span><span class="sxs-lookup"><span data-stu-id="92b32-106">Member</span></span>|<span data-ttu-id="92b32-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92b32-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="92b32-108">Il numero di byte di memoria allocata nel thread in cui è associato all'oggetto corrente `COR_GC_THREAD_STATS` istanza.</span><span class="sxs-lookup"><span data-stu-id="92b32-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="92b32-109">Questo numero viene impostato su zero ogni volta che si verifica una da zero la generazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="92b32-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="92b32-110">Il numero di byte promossi a una generazione superiore le più recenti di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="92b32-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92b32-111">Note</span><span class="sxs-lookup"><span data-stu-id="92b32-111">Remarks</span></span>  
 <span data-ttu-id="92b32-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="92b32-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92b32-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92b32-113">Requirements</span></span>  
 <span data-ttu-id="92b32-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92b32-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92b32-115">**Intestazione:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="92b32-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="92b32-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="92b32-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92b32-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92b32-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b32-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92b32-118">See also</span></span>
- [<span data-ttu-id="92b32-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="92b32-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="92b32-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="92b32-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
