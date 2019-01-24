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
ms.openlocfilehash: 4bd12feb47352d9bb78aa8ef056072f9bdc6fba3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710326"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="e8bc5-102">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="e8bc5-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="e8bc5-103">Specifica le statistiche devono essere registrati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e8bc5-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8bc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8bc5-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8bc5-105">Note</span><span class="sxs-lookup"><span data-stu-id="e8bc5-105">Remarks</span></span>  
 <span data-ttu-id="e8bc5-106">Questa enumerazione specifica le statistiche nella [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) devono essere impostate struttura [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e8bc5-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="e8bc5-107">Membri</span><span class="sxs-lookup"><span data-stu-id="e8bc5-107">Members</span></span>  
  
|<span data-ttu-id="e8bc5-108">Membro</span><span class="sxs-lookup"><span data-stu-id="e8bc5-108">Member</span></span>|<span data-ttu-id="e8bc5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8bc5-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="e8bc5-110">Registra il numero di operazioni di garbage collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="e8bc5-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="e8bc5-111">I record memoria utilizzo e la garbage collection statistiche sulle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e8bc5-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8bc5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8bc5-112">Requirements</span></span>  
 <span data-ttu-id="e8bc5-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8bc5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8bc5-114">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e8bc5-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e8bc5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8bc5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bc5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8bc5-116">See also</span></span>
- [<span data-ttu-id="e8bc5-117">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="e8bc5-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="e8bc5-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="e8bc5-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
