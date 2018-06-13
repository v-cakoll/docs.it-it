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
ms.openlocfilehash: 2c5cf7e17989f3c083c7c4e52fa8cfc09c00bc7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431519"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="de573-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="de573-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="de573-103">Consente all'host per segnalare le condizioni di pressione della memoria con un approccio simile a quello di Win32 `CreateMemoryResourceNotification` (funzione).</span><span class="sxs-lookup"><span data-stu-id="de573-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de573-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="de573-104">Methods</span></span>  
  
|<span data-ttu-id="de573-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="de573-105">Method</span></span>|<span data-ttu-id="de573-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de573-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de573-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="de573-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="de573-108">Notifica a common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="de573-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de573-109">Note</span><span class="sxs-lookup"><span data-stu-id="de573-109">Remarks</span></span>  
 <span data-ttu-id="de573-110">L'host usa il `ICLRMemoryNotificationCallback` interfaccia per richiedere a CLR di liberare risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="de573-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de573-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de573-111">Requirements</span></span>  
 <span data-ttu-id="de573-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de573-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de573-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="de573-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de573-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="de573-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de573-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de573-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de573-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de573-116">See Also</span></span>  
 [<span data-ttu-id="de573-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="de573-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="de573-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="de573-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
