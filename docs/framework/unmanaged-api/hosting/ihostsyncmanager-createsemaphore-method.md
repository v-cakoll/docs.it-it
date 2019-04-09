---
title: Metodo IHostSyncManager::CreateSemaphore
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef9a5896c2ecc54b7fd48670f751d193ac74554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138619"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="d58be-102">Metodo IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="d58be-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="d58be-103">Crea un' [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per common language runtime (CLR) da utilizzare come un semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="d58be-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d58be-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d58be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d58be-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="d58be-106">[in] Il numero iniziale per `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="d58be-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="d58be-107">[in] Il numero massimo per `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="d58be-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="d58be-108">[out] Un puntatore all'indirizzo di un `IHostSemaphore` istanza oppure null se non è stato possibile creare il semaforo.</span><span class="sxs-lookup"><span data-stu-id="d58be-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d58be-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d58be-109">Return Value</span></span>  
  
|<span data-ttu-id="d58be-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d58be-110">HRESULT</span></span>|<span data-ttu-id="d58be-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d58be-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d58be-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d58be-112">S_OK</span></span>|`CreateSemaphore` <span data-ttu-id="d58be-113">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d58be-113">returned successfully.</span></span>|  
|<span data-ttu-id="d58be-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d58be-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d58be-115">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d58be-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d58be-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d58be-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d58be-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d58be-117">The call timed out.</span></span>|  
|<span data-ttu-id="d58be-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d58be-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d58be-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d58be-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d58be-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d58be-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d58be-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d58be-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d58be-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d58be-122">E_FAIL</span></span>|<span data-ttu-id="d58be-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d58be-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d58be-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d58be-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d58be-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d58be-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d58be-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d58be-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d58be-127">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="d58be-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d58be-128">Note</span><span class="sxs-lookup"><span data-stu-id="d58be-128">Remarks</span></span>  
 `CreateSemaphore` <span data-ttu-id="d58be-129">rispecchia la funzione Win32 con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="d58be-129">mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="d58be-130">Il `dwInitial` e `dwMax` i parametri utilizzano la stessa semantica per il conteggio del semaforo Win32 `lInitialCount` e `lMaximumCount` parametri, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d58be-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> `dwInitial` <span data-ttu-id="d58be-131">deve essere compreso tra zero e `dwMax`, inclusivo.</span><span class="sxs-lookup"><span data-stu-id="d58be-131">must be between zero and `dwMax`, inclusive.</span></span> `dwMax` <span data-ttu-id="d58be-132">Deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="d58be-132">must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58be-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d58be-133">Requirements</span></span>  
 <span data-ttu-id="d58be-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d58be-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58be-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d58be-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d58be-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d58be-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d58be-137">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d58be-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d58be-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58be-138">See also</span></span>

- [<span data-ttu-id="d58be-139">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d58be-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d58be-140">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="d58be-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="d58be-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d58be-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
