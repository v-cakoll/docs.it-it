---
title: Enumerazione COR_GC_THREAD_STATS_TYPES
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a984e8645bec0f58d8a31965b762e0a3a190ba59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768025"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="31783-102">Enumerazione COR_GC_THREAD_STATS_TYPES</span><span class="sxs-lookup"><span data-stu-id="31783-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="31783-103">Indica le statistiche per un thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="31783-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31783-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31783-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="31783-105">Membri</span><span class="sxs-lookup"><span data-stu-id="31783-105">Members</span></span>  
  
|<span data-ttu-id="31783-106">Member</span><span class="sxs-lookup"><span data-stu-id="31783-106">Member</span></span>|<span data-ttu-id="31783-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31783-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="31783-108">Il thread di byte che sono state alzate di livello il più recente operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="31783-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31783-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31783-109">Requirements</span></span>  
 <span data-ttu-id="31783-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31783-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31783-111">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="31783-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="31783-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31783-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31783-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31783-113">See also</span></span>

- [<span data-ttu-id="31783-114">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="31783-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
