---
title: Interfaccia ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212154"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="5555f-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="5555f-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="5555f-103">Consente all'host per segnalare le condizioni di pressione della memoria con un approccio simile a quella di Win32 `CreateMemoryResourceNotification` (funzione).</span><span class="sxs-lookup"><span data-stu-id="5555f-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5555f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5555f-104">Methods</span></span>  
  
|<span data-ttu-id="5555f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5555f-105">Method</span></span>|<span data-ttu-id="5555f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5555f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5555f-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="5555f-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="5555f-108">Invia una notifica di common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="5555f-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5555f-109">Note</span><span class="sxs-lookup"><span data-stu-id="5555f-109">Remarks</span></span>  
 <span data-ttu-id="5555f-110">L'host usa la `ICLRMemoryNotificationCallback` interfaccia per richiedere a CLR di liberare le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="5555f-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5555f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5555f-111">Requirements</span></span>  
 <span data-ttu-id="5555f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5555f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5555f-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5555f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5555f-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5555f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5555f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5555f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5555f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5555f-116">See also</span></span>

- [<span data-ttu-id="5555f-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5555f-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="5555f-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5555f-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
