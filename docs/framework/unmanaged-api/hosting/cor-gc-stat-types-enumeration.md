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
ms.openlocfilehash: 9e228cfbdade420c4d5248ffd417c6131083ee74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697277"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="d90c8-102">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="d90c8-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="d90c8-103">Specifica le statistiche devono essere registrati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d90c8-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d90c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d90c8-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d90c8-105">Note</span><span class="sxs-lookup"><span data-stu-id="d90c8-105">Remarks</span></span>  
 <span data-ttu-id="d90c8-106">Questa enumerazione specifica le statistiche nella [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) devono essere impostate struttura [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d90c8-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="d90c8-107">Membri</span><span class="sxs-lookup"><span data-stu-id="d90c8-107">Members</span></span>  
  
|<span data-ttu-id="d90c8-108">Member</span><span class="sxs-lookup"><span data-stu-id="d90c8-108">Member</span></span>|<span data-ttu-id="d90c8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d90c8-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="d90c8-110">Registra il numero di operazioni di garbage collection eseguite per ogni generazione.</span><span class="sxs-lookup"><span data-stu-id="d90c8-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="d90c8-111">I record memoria utilizzo e la garbage collection statistiche sulle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d90c8-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d90c8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d90c8-112">Requirements</span></span>  
 <span data-ttu-id="d90c8-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d90c8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d90c8-114">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="d90c8-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d90c8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d90c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90c8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d90c8-116">See also</span></span>

- [<span data-ttu-id="d90c8-117">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="d90c8-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="d90c8-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d90c8-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
