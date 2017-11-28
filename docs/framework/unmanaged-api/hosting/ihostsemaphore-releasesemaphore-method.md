---
title: Metodo IHostSemaphore::ReleaseSemaphore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.ReleaseSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06765d019d5443730656e7f4d6745bd8ad39ee00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="82621-102">Metodo IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="82621-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="82621-103">Aumenta il numero di corrente [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) istanza del valore specificato.</span><span class="sxs-lookup"><span data-stu-id="82621-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82621-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82621-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82621-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82621-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="82621-106">[in] Quantità in base alla quale incrementare il conteggio corrente `IHostSemaphore` istanza.</span><span class="sxs-lookup"><span data-stu-id="82621-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="82621-107">Questa quantità deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="82621-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="82621-108">[out] Puntatore al numero precedente oppure null se il chiamante non richiede il conteggio precedente.</span><span class="sxs-lookup"><span data-stu-id="82621-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82621-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82621-109">Return Value</span></span>  
  
|<span data-ttu-id="82621-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82621-110">HRESULT</span></span>|<span data-ttu-id="82621-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82621-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82621-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="82621-112">S_OK</span></span>|<span data-ttu-id="82621-113">`ReleaseSemaphore`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="82621-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="82621-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82621-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82621-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="82621-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82621-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82621-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82621-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="82621-117">The call timed out.</span></span>|  
|<span data-ttu-id="82621-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82621-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82621-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="82621-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82621-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82621-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82621-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="82621-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82621-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82621-122">E_FAIL</span></span>|<span data-ttu-id="82621-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="82621-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82621-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="82621-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82621-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82621-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82621-126">Note</span><span class="sxs-lookup"><span data-stu-id="82621-126">Remarks</span></span>  
 <span data-ttu-id="82621-127">CLR chiama in genere `ReleaseSemaphore` per notificare all'host che ha terminato l'utilizzo di una risorsa, passando il valore 1 per il `lReleaseCount` parametro.</span><span class="sxs-lookup"><span data-stu-id="82621-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82621-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82621-128">Requirements</span></span>  
 <span data-ttu-id="82621-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82621-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82621-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="82621-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82621-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82621-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82621-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82621-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82621-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82621-133">See Also</span></span>  
 [<span data-ttu-id="82621-134">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="82621-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="82621-135">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="82621-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="82621-136">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="82621-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="82621-137">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="82621-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="82621-138">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="82621-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
