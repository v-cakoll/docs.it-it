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
ms.openlocfilehash: 33c2a244622f562c074808a78f7c57134d5a9202
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689065"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="9911d-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="9911d-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="9911d-103">Rappresenta l'implementazione dell'host di un semaforo per il threading.</span><span class="sxs-lookup"><span data-stu-id="9911d-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9911d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9911d-104">Methods</span></span>  
  
|<span data-ttu-id="9911d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9911d-105">Method</span></span>|<span data-ttu-id="9911d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9911d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9911d-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="9911d-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="9911d-108">Aumenta il numero di corrente `IHostSemaphore` istanza base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="9911d-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="9911d-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="9911d-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="9911d-110">Fa sì che l'oggetto corrente `IHostSemaphore` istanza in attesa fino a quando non è di proprietà o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="9911d-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9911d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9911d-111">Requirements</span></span>  
 <span data-ttu-id="9911d-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9911d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9911d-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9911d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9911d-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9911d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9911d-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9911d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9911d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9911d-116">See also</span></span>
- [<span data-ttu-id="9911d-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9911d-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9911d-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="9911d-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="9911d-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="9911d-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="9911d-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9911d-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="9911d-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9911d-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
