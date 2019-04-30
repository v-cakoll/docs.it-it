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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948551"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="cb1e9-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="cb1e9-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="cb1e9-103">Consente all'host per segnalare le condizioni di pressione della memoria con un approccio simile a quella di Win32 `CreateMemoryResourceNotification` (funzione).</span><span class="sxs-lookup"><span data-stu-id="cb1e9-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb1e9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb1e9-104">Methods</span></span>  
  
|<span data-ttu-id="cb1e9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb1e9-105">Method</span></span>|<span data-ttu-id="cb1e9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb1e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb1e9-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="cb1e9-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="cb1e9-108">Invia una notifica di common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="cb1e9-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb1e9-109">Note</span><span class="sxs-lookup"><span data-stu-id="cb1e9-109">Remarks</span></span>  
 <span data-ttu-id="cb1e9-110">L'host usa la `ICLRMemoryNotificationCallback` interfaccia per richiedere a CLR di liberare le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="cb1e9-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1e9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb1e9-111">Requirements</span></span>  
 <span data-ttu-id="cb1e9-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1e9-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb1e9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb1e9-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cb1e9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb1e9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1e9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb1e9-116">See also</span></span>

- [<span data-ttu-id="cb1e9-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="cb1e9-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="cb1e9-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="cb1e9-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
