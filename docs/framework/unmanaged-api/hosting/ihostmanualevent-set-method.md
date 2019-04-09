---
title: Metodo IHostManualEvent::Set
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 674745636033f42eb8fb67babf6f5a3f013491c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093501"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="aa106-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="aa106-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="aa106-103">Imposta l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="aa106-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa106-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa106-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aa106-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aa106-105">Return Value</span></span>  
  
|<span data-ttu-id="aa106-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa106-106">HRESULT</span></span>|<span data-ttu-id="aa106-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa106-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa106-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa106-108">S_OK</span></span>|`Set` <span data-ttu-id="aa106-109">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="aa106-109">returned successfully.</span></span>|  
|<span data-ttu-id="aa106-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa106-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa106-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aa106-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa106-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa106-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa106-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="aa106-113">The call timed out.</span></span>|  
|<span data-ttu-id="aa106-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa106-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa106-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="aa106-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa106-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa106-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa106-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="aa106-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa106-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa106-118">E_FAIL</span></span>|<span data-ttu-id="aa106-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="aa106-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa106-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="aa106-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa106-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa106-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa106-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa106-122">Requirements</span></span>  
 <span data-ttu-id="aa106-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa106-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa106-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aa106-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa106-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aa106-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="aa106-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aa106-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa106-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa106-127">See also</span></span>

- [<span data-ttu-id="aa106-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="aa106-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="aa106-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="aa106-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="aa106-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="aa106-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="aa106-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="aa106-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="aa106-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="aa106-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
