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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eac378a48900d5820ad35587a6d269648ef99a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428899"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="a0074-102">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="a0074-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="a0074-103">Specifica le statistiche devono essere registrati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a0074-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0074-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0074-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="a0074-105">Note</span><span class="sxs-lookup"><span data-stu-id="a0074-105">Remarks</span></span>  
 <span data-ttu-id="a0074-106">Questa enumerazione specifica le statistiche nella [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura devono essere impostate [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="a0074-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="a0074-107">Membri</span><span class="sxs-lookup"><span data-stu-id="a0074-107">Members</span></span>  
  
|<span data-ttu-id="a0074-108">Membro</span><span class="sxs-lookup"><span data-stu-id="a0074-108">Member</span></span>|<span data-ttu-id="a0074-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0074-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="a0074-110">Registra il numero di operazioni di garbage collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="a0074-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="a0074-111">Record utilizzo e garbage collection dimensioni le statistiche di memoria.</span><span class="sxs-lookup"><span data-stu-id="a0074-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0074-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0074-112">Requirements</span></span>  
 <span data-ttu-id="a0074-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0074-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0074-114">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="a0074-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a0074-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0074-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0074-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0074-116">See Also</span></span>  
 [<span data-ttu-id="a0074-117">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="a0074-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="a0074-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a0074-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
