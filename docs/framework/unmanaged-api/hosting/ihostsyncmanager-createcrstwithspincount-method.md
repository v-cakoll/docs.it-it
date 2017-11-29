---
title: Metodo IHostSyncManager::CreateCrstWithSpinCount
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41031a5e3d423f0c1d7459250073634592e0291e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="09a69-102">Metodo IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="09a69-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="09a69-103">Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="09a69-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09a69-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09a69-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09a69-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="09a69-106">[in] Specifica il numero di selezione per l'oggetto sezione critica.</span><span class="sxs-lookup"><span data-stu-id="09a69-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="09a69-107">[out] Un puntatore all'indirizzo di un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) oppure null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="09a69-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09a69-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09a69-108">Return Value</span></span>  
  
|<span data-ttu-id="09a69-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09a69-109">HRESULT</span></span>|<span data-ttu-id="09a69-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09a69-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09a69-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="09a69-111">S_OK</span></span>|<span data-ttu-id="09a69-112">`CreateCrstWithSpinCount`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="09a69-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="09a69-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09a69-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09a69-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="09a69-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09a69-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09a69-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09a69-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="09a69-116">The call timed out.</span></span>|  
|<span data-ttu-id="09a69-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09a69-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09a69-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="09a69-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09a69-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09a69-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09a69-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="09a69-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09a69-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09a69-121">E_FAIL</span></span>|<span data-ttu-id="09a69-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="09a69-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09a69-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="09a69-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09a69-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="09a69-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09a69-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="09a69-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="09a69-126">Memoria insufficiente è disponibile per creare la richiesta sezione critica.</span><span class="sxs-lookup"><span data-stu-id="09a69-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09a69-127">Note</span><span class="sxs-lookup"><span data-stu-id="09a69-127">Remarks</span></span>  
 <span data-ttu-id="09a69-128">Il numero di selezione viene utilizzato solo in un sistema multiprocessore.</span><span class="sxs-lookup"><span data-stu-id="09a69-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="09a69-129">Il conteggio di selezione specifica il numero di volte in cui che un thread chiamante è necessario attivare prima di eseguire un'operazione di attesa su un semaforo per cui è associata a una sezione critica non disponibile.</span><span class="sxs-lookup"><span data-stu-id="09a69-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="09a69-130">Se la sezione critica diventa disponibile durante l'operazione di selezione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="09a69-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="09a69-131">`CreateCrstWithSpinCount`rispecchia Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="09a69-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a69-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09a69-132">Requirements</span></span>  
 <span data-ttu-id="09a69-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09a69-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a69-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="09a69-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09a69-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09a69-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09a69-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a69-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a69-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09a69-137">See Also</span></span>  
 [<span data-ttu-id="09a69-138">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="09a69-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="09a69-139">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="09a69-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="09a69-140">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="09a69-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
