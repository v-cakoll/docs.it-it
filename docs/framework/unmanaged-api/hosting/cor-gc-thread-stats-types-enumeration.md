---
title: Enumerazione COR_GC_THREAD_STATS_TYPES
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1967f13037be597288b48cbbdf001cad5d6b8e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="57d69-102">Enumerazione COR_GC_THREAD_STATS_TYPES</span><span class="sxs-lookup"><span data-stu-id="57d69-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="57d69-103">Indica le statistiche per un thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="57d69-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57d69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57d69-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="57d69-105">Membri</span><span class="sxs-lookup"><span data-stu-id="57d69-105">Members</span></span>  
  
|<span data-ttu-id="57d69-106">Membro</span><span class="sxs-lookup"><span data-stu-id="57d69-106">Member</span></span>|<span data-ttu-id="57d69-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57d69-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="57d69-108">Il thread di byte che sono state alzate di livello nell'ultima garbage collection.</span><span class="sxs-lookup"><span data-stu-id="57d69-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57d69-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57d69-109">Requirements</span></span>  
 <span data-ttu-id="57d69-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57d69-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57d69-111">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="57d69-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="57d69-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57d69-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57d69-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57d69-113">See Also</span></span>  
 [<span data-ttu-id="57d69-114">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="57d69-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
