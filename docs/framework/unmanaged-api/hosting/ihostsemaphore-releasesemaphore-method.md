---
title: Metodo IHostSemaphore::ReleaseSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ec56345a5b48540d2451769f739a236a85e47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100613"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="0e5b5-102">Metodo IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="0e5b5-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="0e5b5-103">Aumenta il numero dell'oggetto corrente [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) istanza base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e5b5-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e5b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e5b5-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="0e5b5-106">[in] La quantità di cui aumentare il numero dell'oggetto corrente `IHostSemaphore` istanza.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="0e5b5-107">Questo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="0e5b5-108">[out] Puntatore al numero di transazioni precedente oppure null se il chiamante non richiede il conteggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e5b5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0e5b5-109">Return Value</span></span>  
  
|<span data-ttu-id="0e5b5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e5b5-110">HRESULT</span></span>|<span data-ttu-id="0e5b5-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e5b5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e5b5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e5b5-112">S_OK</span></span>|`ReleaseSemaphore` <span data-ttu-id="0e5b5-113">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-113">returned successfully.</span></span>|  
|<span data-ttu-id="0e5b5-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e5b5-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e5b5-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e5b5-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e5b5-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e5b5-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-117">The call timed out.</span></span>|  
|<span data-ttu-id="0e5b5-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e5b5-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e5b5-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e5b5-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e5b5-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e5b5-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e5b5-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e5b5-122">E_FAIL</span></span>|<span data-ttu-id="0e5b5-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e5b5-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e5b5-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e5b5-126">Note</span><span class="sxs-lookup"><span data-stu-id="0e5b5-126">Remarks</span></span>  
 <span data-ttu-id="0e5b5-127">CLR chiama in genere `ReleaseSemaphore` per notificare all'host che ha terminato l'utilizzo di una risorsa, passando il valore 1 per il `lReleaseCount` parametro.</span><span class="sxs-lookup"><span data-stu-id="0e5b5-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e5b5-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e5b5-128">Requirements</span></span>  
 <span data-ttu-id="0e5b5-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e5b5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e5b5-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e5b5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e5b5-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0e5b5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0e5b5-132">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0e5b5-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0e5b5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e5b5-133">See also</span></span>

- [<span data-ttu-id="0e5b5-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0e5b5-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0e5b5-135">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0e5b5-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="0e5b5-136">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0e5b5-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="0e5b5-137">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="0e5b5-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="0e5b5-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0e5b5-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
