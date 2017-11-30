---
title: Metodo IHostSyncManager::CreateCrst
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b54abb60b00d071900d3bfdd01c2e5f1807998a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="36541-102">Metodo IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="36541-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="36541-103">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="36541-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36541-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36541-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36541-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36541-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="36541-106">[out] Un puntatore all'indirizzo di un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza implementata dall'host, o null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="36541-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36541-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36541-107">Return Value</span></span>  
  
|<span data-ttu-id="36541-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36541-108">HRESULT</span></span>|<span data-ttu-id="36541-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36541-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36541-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36541-110">S_OK</span></span>|<span data-ttu-id="36541-111">`CreateCrst`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="36541-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="36541-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36541-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36541-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="36541-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36541-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36541-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36541-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="36541-115">The call timed out.</span></span>|  
|<span data-ttu-id="36541-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36541-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36541-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="36541-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36541-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36541-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36541-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="36541-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36541-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36541-120">E_FAIL</span></span>|<span data-ttu-id="36541-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="36541-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36541-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="36541-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36541-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="36541-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36541-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="36541-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="36541-125">Memoria insufficiente è disponibile per creare la richiesta sezione critica.</span><span class="sxs-lookup"><span data-stu-id="36541-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36541-126">Note</span><span class="sxs-lookup"><span data-stu-id="36541-126">Remarks</span></span>  
 <span data-ttu-id="36541-127">Gli oggetti sezione critica consentono la sincronizzazione simile a quello fornito da un oggetto mutex, ad eccezione del fatto che le sezioni critiche possono essere utilizzate solo dai thread di un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="36541-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="36541-128">`CreateCrst`rispecchia Win32 `InitializeCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="36541-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36541-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36541-129">Requirements</span></span>  
 <span data-ttu-id="36541-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36541-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36541-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="36541-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36541-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36541-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36541-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36541-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36541-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36541-134">See Also</span></span>  
 [<span data-ttu-id="36541-135">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36541-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="36541-136">IHostCrst (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36541-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="36541-137">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36541-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="36541-138">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36541-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="36541-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="36541-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)  
 [<span data-ttu-id="36541-140">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="36541-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
