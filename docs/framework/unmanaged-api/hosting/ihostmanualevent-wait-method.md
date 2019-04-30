---
title: Metodo IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90bf2b7472af3f9125edbd29f6924ddec9c1530
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973134"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="96878-102">Metodo IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="96878-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="96878-103">Fa sì che l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza in attesa fino a quando non è di proprietà o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="96878-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96878-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96878-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96878-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96878-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="96878-106">[in] Il numero di millisecondi di attesa prima della restituzione, se l'oggetto corrente `IHostManualEvent` istanza non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="96878-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="96878-107">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione che l'host deve avere se questa operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="96878-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96878-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96878-108">Return Value</span></span>  
  
|<span data-ttu-id="96878-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96878-109">HRESULT</span></span>|<span data-ttu-id="96878-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96878-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96878-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="96878-111">S_OK</span></span>|<span data-ttu-id="96878-112">`Wait` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="96878-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="96878-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96878-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96878-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="96878-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96878-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96878-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96878-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="96878-116">The call timed out.</span></span>|  
|<span data-ttu-id="96878-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96878-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96878-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="96878-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96878-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96878-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96878-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="96878-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96878-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96878-121">E_FAIL</span></span>|<span data-ttu-id="96878-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="96878-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96878-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="96878-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96878-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="96878-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="96878-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="96878-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="96878-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e sceglie corrente `IHostManualEvent` istanza come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="96878-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96878-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96878-127">Requirements</span></span>  
 <span data-ttu-id="96878-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96878-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96878-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96878-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96878-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="96878-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96878-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96878-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96878-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96878-132">See also</span></span>

- [<span data-ttu-id="96878-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="96878-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="96878-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="96878-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="96878-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="96878-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="96878-136">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="96878-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="96878-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="96878-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
