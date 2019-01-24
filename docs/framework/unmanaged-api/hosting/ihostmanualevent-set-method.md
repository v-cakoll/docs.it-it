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
ms.openlocfilehash: c1c40b27cd2899b5c3142364958b18144b8d4fee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709702"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="b91bd-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="b91bd-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="b91bd-103">Imposta l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="b91bd-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b91bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b91bd-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b91bd-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b91bd-105">Return Value</span></span>  
  
|<span data-ttu-id="b91bd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b91bd-106">HRESULT</span></span>|<span data-ttu-id="b91bd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b91bd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b91bd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b91bd-108">S_OK</span></span>|<span data-ttu-id="b91bd-109">`Set` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b91bd-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="b91bd-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b91bd-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b91bd-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b91bd-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b91bd-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b91bd-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b91bd-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b91bd-113">The call timed out.</span></span>|  
|<span data-ttu-id="b91bd-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b91bd-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b91bd-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b91bd-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b91bd-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b91bd-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b91bd-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b91bd-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b91bd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b91bd-118">E_FAIL</span></span>|<span data-ttu-id="b91bd-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b91bd-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b91bd-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b91bd-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b91bd-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b91bd-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b91bd-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b91bd-122">Requirements</span></span>  
 <span data-ttu-id="b91bd-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b91bd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b91bd-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b91bd-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b91bd-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b91bd-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b91bd-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b91bd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91bd-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b91bd-127">See also</span></span>
- [<span data-ttu-id="b91bd-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b91bd-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b91bd-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="b91bd-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="b91bd-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="b91bd-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="b91bd-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="b91bd-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="b91bd-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b91bd-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
