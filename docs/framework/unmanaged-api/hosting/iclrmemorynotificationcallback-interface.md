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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212154"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="692fc-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="692fc-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="692fc-103">Consente all'host per segnalare le condizioni di pressione della memoria con un approccio simile a quella di Win32 `CreateMemoryResourceNotification` (funzione).</span><span class="sxs-lookup"><span data-stu-id="692fc-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="692fc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="692fc-104">Methods</span></span>  
  
|<span data-ttu-id="692fc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="692fc-105">Method</span></span>|<span data-ttu-id="692fc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="692fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="692fc-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="692fc-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="692fc-108">Invia una notifica di common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="692fc-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="692fc-109">Note</span><span class="sxs-lookup"><span data-stu-id="692fc-109">Remarks</span></span>  
 <span data-ttu-id="692fc-110">L'host usa la `ICLRMemoryNotificationCallback` interfaccia per richiedere a CLR di liberare le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="692fc-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692fc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="692fc-111">Requirements</span></span>  
 <span data-ttu-id="692fc-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="692fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692fc-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="692fc-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="692fc-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="692fc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="692fc-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="692fc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="692fc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="692fc-116">See also</span></span>

- [<span data-ttu-id="692fc-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="692fc-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="692fc-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="692fc-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
