---
title: Metodo IHostSyncManager::CreateSemaphore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c7e33e4f178a4fd51ae27912959d0e4edf30ecb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="2652f-102">Metodo IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="2652f-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="2652f-103">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per common language runtime (CLR) da utilizzare come un semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="2652f-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2652f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2652f-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2652f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2652f-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="2652f-106">[in] Il numero iniziale per `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="2652f-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="2652f-107">[in] Il numero massimo di `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="2652f-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="2652f-108">[out] Un puntatore all'indirizzo di un `IHostSemaphore` istanza oppure null se non è stato possibile creare il semaforo.</span><span class="sxs-lookup"><span data-stu-id="2652f-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2652f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2652f-109">Return Value</span></span>  
  
|<span data-ttu-id="2652f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2652f-110">HRESULT</span></span>|<span data-ttu-id="2652f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2652f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2652f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2652f-112">S_OK</span></span>|<span data-ttu-id="2652f-113">`CreateSemaphore`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2652f-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="2652f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2652f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2652f-115">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2652f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2652f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2652f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2652f-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2652f-117">The call timed out.</span></span>|  
|<span data-ttu-id="2652f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2652f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2652f-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="2652f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2652f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2652f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2652f-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2652f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2652f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2652f-122">E_FAIL</span></span>|<span data-ttu-id="2652f-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2652f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2652f-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2652f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2652f-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2652f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2652f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2652f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2652f-127">È disponibile per creare l'oggetto evento richiesto non è sufficiente memoria.</span><span class="sxs-lookup"><span data-stu-id="2652f-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2652f-128">Note</span><span class="sxs-lookup"><span data-stu-id="2652f-128">Remarks</span></span>  
 <span data-ttu-id="2652f-129">`CreateSemaphore`rispecchia la funzione Win32 con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2652f-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="2652f-130">Il `dwInitial` e `dwMax` parametri utilizzano la stessa semantica per il conteggio del semaforo Win32 `lInitialCount` e `lMaximumCount` parametri, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="2652f-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="2652f-131">`dwInitial`deve essere compreso tra zero e `dwMax`, inclusivo.</span><span class="sxs-lookup"><span data-stu-id="2652f-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="2652f-132">`dwMax`deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="2652f-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2652f-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2652f-133">Requirements</span></span>  
 <span data-ttu-id="2652f-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2652f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2652f-135">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2652f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2652f-136">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2652f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2652f-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2652f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2652f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2652f-138">See Also</span></span>  
 [<span data-ttu-id="2652f-139">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2652f-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="2652f-140">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2652f-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="2652f-141">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2652f-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
