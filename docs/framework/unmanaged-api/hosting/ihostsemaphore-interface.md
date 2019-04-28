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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696680"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="38371-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="38371-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="38371-103">Rappresenta l'implementazione dell'host di un semaforo per il threading.</span><span class="sxs-lookup"><span data-stu-id="38371-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38371-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="38371-104">Methods</span></span>  
  
|<span data-ttu-id="38371-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="38371-105">Method</span></span>|<span data-ttu-id="38371-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38371-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38371-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="38371-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="38371-108">Aumenta il numero di corrente `IHostSemaphore` istanza base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="38371-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="38371-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="38371-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="38371-110">Fa sì che l'oggetto corrente `IHostSemaphore` istanza in attesa fino a quando non è di proprietà o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="38371-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38371-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38371-111">Requirements</span></span>  
 <span data-ttu-id="38371-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38371-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38371-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38371-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38371-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="38371-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38371-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38371-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38371-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38371-116">See also</span></span>

- [<span data-ttu-id="38371-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="38371-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="38371-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="38371-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="38371-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="38371-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="38371-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="38371-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="38371-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="38371-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
