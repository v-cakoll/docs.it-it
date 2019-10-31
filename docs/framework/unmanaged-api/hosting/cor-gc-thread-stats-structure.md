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
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136979"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="249e2-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="249e2-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="249e2-103">Contiene statistiche per thread che riguardano Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="249e2-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="249e2-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="249e2-105">Members</span><span class="sxs-lookup"><span data-stu-id="249e2-105">Members</span></span>  
  
|<span data-ttu-id="249e2-106">Member</span><span class="sxs-lookup"><span data-stu-id="249e2-106">Member</span></span>|<span data-ttu-id="249e2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="249e2-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="249e2-108">Numero di byte di memoria allocata nel thread associato all'istanza di `COR_GC_THREAD_STATS` corrente.</span><span class="sxs-lookup"><span data-stu-id="249e2-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="249e2-109">Questo numero viene cancellato a zero ogni volta che viene generato un Garbage Collection di generazione zero.</span><span class="sxs-lookup"><span data-stu-id="249e2-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="249e2-110">Numero di byte promossi a una generazione più elevata nel Garbage Collection più recente.</span><span class="sxs-lookup"><span data-stu-id="249e2-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="249e2-111">Note</span><span class="sxs-lookup"><span data-stu-id="249e2-111">Remarks</span></span>  
 <span data-ttu-id="249e2-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="249e2-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249e2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="249e2-113">Requirements</span></span>  
 <span data-ttu-id="249e2-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="249e2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249e2-115">**Intestazione:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="249e2-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="249e2-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="249e2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="249e2-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249e2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="249e2-118">See also</span></span>

- [<span data-ttu-id="249e2-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="249e2-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="249e2-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="249e2-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
