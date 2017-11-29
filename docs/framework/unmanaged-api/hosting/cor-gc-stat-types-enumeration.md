---
title: Enumerazione COR_GC_STAT_TYPES
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STAT_TYPES
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STAT_TYPES
helpviewer_keywords: COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4cf66026ecf92d0158a1010e82c078478c280f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="d08e8-102">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="d08e8-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="d08e8-103">Specifica le statistiche devono essere registrati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d08e8-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08e8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d08e8-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d08e8-105">Note</span><span class="sxs-lookup"><span data-stu-id="d08e8-105">Remarks</span></span>  
 <span data-ttu-id="d08e8-106">Questa enumerazione specifica le statistiche nella [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura devono essere impostate [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="d08e8-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="d08e8-107">Membri</span><span class="sxs-lookup"><span data-stu-id="d08e8-107">Members</span></span>  
  
|<span data-ttu-id="d08e8-108">Membro</span><span class="sxs-lookup"><span data-stu-id="d08e8-108">Member</span></span>|<span data-ttu-id="d08e8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d08e8-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="d08e8-110">Registra il numero di operazioni di garbage collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="d08e8-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="d08e8-111">Record utilizzo e garbage collection dimensioni le statistiche di memoria.</span><span class="sxs-lookup"><span data-stu-id="d08e8-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d08e8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d08e8-112">Requirements</span></span>  
 <span data-ttu-id="d08e8-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d08e8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d08e8-114">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="d08e8-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d08e8-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d08e8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08e8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d08e8-116">See Also</span></span>  
 [<span data-ttu-id="d08e8-117">COR_GC_STATS (struttura)</span><span class="sxs-lookup"><span data-stu-id="d08e8-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="d08e8-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d08e8-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
