---
title: Interfaccia IHostSemaphore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcc6a9a7847932e9e469cdbffc9792e1d5860570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="4095e-102">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4095e-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="4095e-103">Rappresenta l'implementazione dell'host di un semaforo di threading.</span><span class="sxs-lookup"><span data-stu-id="4095e-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4095e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4095e-104">Methods</span></span>  
  
|<span data-ttu-id="4095e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4095e-105">Method</span></span>|<span data-ttu-id="4095e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4095e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4095e-107">Metodo ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="4095e-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="4095e-108">Aumenta il numero di corrente `IHostSemaphore` istanza del valore specificato.</span><span class="sxs-lookup"><span data-stu-id="4095e-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="4095e-109">Metodo Wait</span><span class="sxs-lookup"><span data-stu-id="4095e-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="4095e-110">Fa sì che l'oggetto corrente `IHostSemaphore` in attesa fino a quando non è di proprietà istanza o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="4095e-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4095e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4095e-111">Requirements</span></span>  
 <span data-ttu-id="4095e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4095e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4095e-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4095e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4095e-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4095e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4095e-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4095e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4095e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4095e-116">See Also</span></span>  
 [<span data-ttu-id="4095e-117">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4095e-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="4095e-118">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4095e-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="4095e-119">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4095e-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="4095e-120">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4095e-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="4095e-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4095e-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
