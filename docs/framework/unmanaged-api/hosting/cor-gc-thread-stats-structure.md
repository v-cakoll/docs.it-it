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
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616697"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="2ab30-102">Struttura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="2ab30-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="2ab30-103">Contiene statistiche per thread che riguardano Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2ab30-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ab30-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="2ab30-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2ab30-105">Members</span></span>  
  
|<span data-ttu-id="2ab30-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2ab30-106">Member</span></span>|<span data-ttu-id="2ab30-107">Description</span><span class="sxs-lookup"><span data-stu-id="2ab30-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="2ab30-108">Numero di byte di memoria allocata nel thread associato all' `COR_GC_THREAD_STATS` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="2ab30-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="2ab30-109">Questo numero viene cancellato a zero ogni volta che viene generato un Garbage Collection di generazione zero.</span><span class="sxs-lookup"><span data-stu-id="2ab30-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="2ab30-110">Numero di byte promossi a una generazione più elevata nel Garbage Collection più recente.</span><span class="sxs-lookup"><span data-stu-id="2ab30-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab30-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2ab30-111">Remarks</span></span>  
 <span data-ttu-id="2ab30-112">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="2ab30-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab30-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ab30-113">Requirements</span></span>  
 <span data-ttu-id="2ab30-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab30-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab30-115">**Intestazione:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="2ab30-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="2ab30-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ab30-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab30-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab30-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ab30-118">See also</span></span>

- [<span data-ttu-id="2ab30-119">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="2ab30-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="2ab30-120">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="2ab30-120">IHostTask Interface</span></span>](ihosttask-interface.md)
