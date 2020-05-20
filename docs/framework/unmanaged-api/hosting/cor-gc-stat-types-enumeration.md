---
title: Enumerazione COR_GC_STAT_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: cca393ae34144787ab7800baec7c58209394f30e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616716"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="b8a05-102">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="b8a05-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="b8a05-103">Specifica le statistiche da registrare per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b8a05-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8a05-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8a05-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b8a05-105">Remarks</span></span>  
 <span data-ttu-id="b8a05-106">Questa enumerazione specifica quali statistiche della struttura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) devono essere impostate dal metodo [ICLRGCManager:: GetStatistics](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a05-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="b8a05-107">Membri</span><span class="sxs-lookup"><span data-stu-id="b8a05-107">Members</span></span>  
  
|<span data-ttu-id="b8a05-108">Membro</span><span class="sxs-lookup"><span data-stu-id="b8a05-108">Member</span></span>|<span data-ttu-id="b8a05-109">Description</span><span class="sxs-lookup"><span data-stu-id="b8a05-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="b8a05-110">Registra il numero di operazioni di Garbage Collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="b8a05-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="b8a05-111">Registra l'utilizzo della memoria e le statistiche delle dimensioni del Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b8a05-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8a05-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8a05-112">Requirements</span></span>  
 <span data-ttu-id="b8a05-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a05-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a05-114">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="b8a05-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b8a05-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a05-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8a05-116">See also</span></span>

- [<span data-ttu-id="b8a05-117">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="b8a05-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="b8a05-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="b8a05-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
