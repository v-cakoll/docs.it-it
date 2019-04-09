---
title: Interfaccia IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182286"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="c0106-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="c0106-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="c0106-103">Rappresenta l'implementazione dell'host di un semaforo per il threading.</span><span class="sxs-lookup"><span data-stu-id="c0106-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0106-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c0106-104">Methods</span></span>  
  
|<span data-ttu-id="c0106-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c0106-105">Method</span></span>|<span data-ttu-id="c0106-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0106-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0106-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="c0106-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="c0106-108">Aumenta il numero di corrente `IHostSemaphore` istanza base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="c0106-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="c0106-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="c0106-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="c0106-110">Fa sì che l'oggetto corrente `IHostSemaphore` istanza in attesa fino a quando non è di proprietà o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="c0106-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0106-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0106-111">Requirements</span></span>  
 <span data-ttu-id="c0106-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0106-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0106-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0106-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0106-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c0106-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c0106-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c0106-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0106-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0106-116">See also</span></span>

- [<span data-ttu-id="c0106-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c0106-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c0106-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="c0106-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c0106-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="c0106-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c0106-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c0106-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="c0106-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c0106-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
