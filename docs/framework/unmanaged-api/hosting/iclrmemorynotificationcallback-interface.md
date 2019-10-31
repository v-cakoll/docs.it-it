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
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140997"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="f4907-102">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="f4907-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="f4907-103">Consente all'host di segnalare le condizioni di utilizzo della memoria utilizzando un approccio simile a quello della funzione Win32 `CreateMemoryResourceNotification`.</span><span class="sxs-lookup"><span data-stu-id="f4907-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4907-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f4907-104">Methods</span></span>  
  
|<span data-ttu-id="f4907-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f4907-105">Method</span></span>|<span data-ttu-id="f4907-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4907-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4907-107">Metodo OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="f4907-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="f4907-108">Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="f4907-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4907-109">Note</span><span class="sxs-lookup"><span data-stu-id="f4907-109">Remarks</span></span>  
 <span data-ttu-id="f4907-110">L'host utilizza l'interfaccia `ICLRMemoryNotificationCallback` per richiedere che le risorse di memoria di CLR siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="f4907-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4907-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4907-111">Requirements</span></span>  
 <span data-ttu-id="f4907-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4907-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4907-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4907-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4907-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4907-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4907-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4907-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4907-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4907-116">See also</span></span>

- [<span data-ttu-id="f4907-117">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f4907-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="f4907-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f4907-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
