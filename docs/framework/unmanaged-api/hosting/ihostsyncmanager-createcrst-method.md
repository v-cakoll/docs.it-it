---
title: Metodo IHostSyncManager::CreateCrst
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 622b6c523adfb7bae2fc38826152ef69709568cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931069"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="9cf36-102">Metodo IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="9cf36-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="9cf36-103">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="9cf36-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cf36-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cf36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cf36-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="9cf36-106">out Puntatore all'indirizzo di un'istanza di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) implementato dall'host oppure null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="9cf36-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cf36-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9cf36-107">Return Value</span></span>  
  
|<span data-ttu-id="9cf36-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cf36-108">HRESULT</span></span>|<span data-ttu-id="9cf36-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cf36-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cf36-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cf36-110">S_OK</span></span>|<span data-ttu-id="9cf36-111">`CreateCrst`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9cf36-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="9cf36-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9cf36-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9cf36-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9cf36-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9cf36-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9cf36-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9cf36-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cf36-115">The call timed out.</span></span>|  
|<span data-ttu-id="9cf36-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9cf36-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9cf36-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9cf36-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9cf36-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9cf36-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9cf36-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9cf36-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9cf36-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9cf36-120">E_FAIL</span></span>|<span data-ttu-id="9cf36-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9cf36-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9cf36-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9cf36-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9cf36-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9cf36-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9cf36-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9cf36-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9cf36-125">Memoria insufficiente per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="9cf36-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf36-126">Note</span><span class="sxs-lookup"><span data-stu-id="9cf36-126">Remarks</span></span>  
 <span data-ttu-id="9cf36-127">Gli oggetti sezione critici forniscono una sincronizzazione simile a quella fornita da un oggetto mutex, ad eccezione del fatto che le sezioni critiche possono essere utilizzate solo dai thread di un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="9cf36-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="9cf36-128">`CreateCrst`rispecchia la funzione `InitializeCriticalSection` Win32.</span><span class="sxs-lookup"><span data-stu-id="9cf36-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf36-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cf36-129">Requirements</span></span>  
 <span data-ttu-id="9cf36-130">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf36-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf36-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9cf36-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cf36-132">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9cf36-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cf36-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf36-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf36-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cf36-134">See also</span></span>

- [<span data-ttu-id="9cf36-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9cf36-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9cf36-136">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="9cf36-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="9cf36-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9cf36-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="9cf36-138">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="9cf36-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9cf36-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="9cf36-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="9cf36-140">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="9cf36-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
