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
ms.openlocfilehash: 2cf490bcd167b7a498ae21f479f616694ccb5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139473"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="7f17b-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="7f17b-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="7f17b-103">Rappresenta l'implementazione dell'host di un semaforo per il Threading.</span><span class="sxs-lookup"><span data-stu-id="7f17b-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f17b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7f17b-104">Methods</span></span>  
  
|<span data-ttu-id="7f17b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7f17b-105">Method</span></span>|<span data-ttu-id="7f17b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f17b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f17b-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="7f17b-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="7f17b-108">Aumenta il numero dell'istanza di `IHostSemaphore` corrente in base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="7f17b-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="7f17b-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="7f17b-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="7f17b-110">Fa in modo che l'istanza corrente di `IHostSemaphore` attenda finché non è di proprietà o la quantità di tempo specificata scade.</span><span class="sxs-lookup"><span data-stu-id="7f17b-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f17b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f17b-111">Requirements</span></span>  
 <span data-ttu-id="7f17b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f17b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f17b-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7f17b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f17b-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7f17b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f17b-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f17b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f17b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f17b-116">See also</span></span>

- [<span data-ttu-id="7f17b-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7f17b-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7f17b-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="7f17b-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="7f17b-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7f17b-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7f17b-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7f17b-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="7f17b-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7f17b-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
