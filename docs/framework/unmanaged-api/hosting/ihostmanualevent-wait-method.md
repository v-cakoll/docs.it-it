---
title: Metodo IHostManualEvent::Wait
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2bd584e1ada69adca7f8ef77f98533ef7a1ba16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="35fb0-102">Metodo IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="35fb0-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="35fb0-103">Fa sì che l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) in attesa fino a quando non è di proprietà istanza o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="35fb0-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35fb0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35fb0-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35fb0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35fb0-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="35fb0-106">[in] Il numero di millisecondi di attesa prima della restituzione, se l'oggetto corrente `IHostManualEvent` istanza non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="35fb0-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="35fb0-107">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="35fb0-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35fb0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35fb0-108">Return Value</span></span>  
  
|<span data-ttu-id="35fb0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35fb0-109">HRESULT</span></span>|<span data-ttu-id="35fb0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35fb0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35fb0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="35fb0-111">S_OK</span></span>|<span data-ttu-id="35fb0-112">`Wait`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="35fb0-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="35fb0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35fb0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35fb0-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35fb0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35fb0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35fb0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35fb0-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="35fb0-116">The call timed out.</span></span>|  
|<span data-ttu-id="35fb0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35fb0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35fb0-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="35fb0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35fb0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35fb0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35fb0-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="35fb0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35fb0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35fb0-121">E_FAIL</span></span>|<span data-ttu-id="35fb0-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="35fb0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35fb0-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="35fb0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35fb0-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="35fb0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="35fb0-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="35fb0-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="35fb0-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e sceglie corrente `IHostManualEvent` istanza come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="35fb0-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35fb0-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35fb0-127">Requirements</span></span>  
 <span data-ttu-id="35fb0-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35fb0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35fb0-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="35fb0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35fb0-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35fb0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35fb0-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35fb0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35fb0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35fb0-132">See Also</span></span>  
 [<span data-ttu-id="35fb0-133">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35fb0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="35fb0-134">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35fb0-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="35fb0-135">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35fb0-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="35fb0-136">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35fb0-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="35fb0-137">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35fb0-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
