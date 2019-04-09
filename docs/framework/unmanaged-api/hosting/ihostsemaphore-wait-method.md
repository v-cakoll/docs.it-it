---
title: Metodo IHostSemaphore::Wait
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9fcbca92b1615679be57fb4c9b872339fef8a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118218"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="1d864-102">Metodo IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="1d864-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="1d864-103">Fa sì che l'oggetto corrente [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) istanza in attesa fino a quando non è di proprietà o il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1d864-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d864-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d864-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d864-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d864-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="1d864-106">[in] Il numero di millisecondi di attesa prima della restituzione, se l'oggetto corrente `IHostSemaphore` istanza non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d864-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="1d864-107">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che specifica l'azione che l'host deve intraprendere se questa operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="1d864-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d864-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1d864-108">Return Value</span></span>  
  
|<span data-ttu-id="1d864-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d864-109">HRESULT</span></span>|<span data-ttu-id="1d864-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d864-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d864-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d864-111">S_OK</span></span>|`Wait` <span data-ttu-id="1d864-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1d864-112">returned successfully.</span></span>|  
|<span data-ttu-id="1d864-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d864-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d864-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d864-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d864-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d864-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d864-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d864-116">The call timed out.</span></span>|  
|<span data-ttu-id="1d864-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d864-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d864-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="1d864-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d864-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d864-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d864-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1d864-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d864-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d864-121">E_FAIL</span></span>|<span data-ttu-id="1d864-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1d864-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d864-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1d864-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d864-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d864-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1d864-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="1d864-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="1d864-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e sceglie corrente `IHostSemaphore` istanza come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="1d864-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d864-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d864-127">Requirements</span></span>  
 <span data-ttu-id="1d864-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d864-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d864-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d864-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d864-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1d864-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1d864-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1d864-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d864-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d864-132">See also</span></span>

- [<span data-ttu-id="1d864-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1d864-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1d864-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="1d864-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1d864-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="1d864-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1d864-136">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="1d864-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1d864-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="1d864-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
