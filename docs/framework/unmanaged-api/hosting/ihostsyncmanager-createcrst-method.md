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
ms.openlocfilehash: 88b7b2093ecb2c601e57eca32e25c21e91641281
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753479"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="44c60-102">Metodo IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="44c60-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="44c60-103">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="44c60-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44c60-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44c60-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="44c60-106">[out] Un puntatore all'indirizzo di un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza implementata dall'host, o null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="44c60-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44c60-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="44c60-107">Return Value</span></span>  
  
|<span data-ttu-id="44c60-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44c60-108">HRESULT</span></span>|<span data-ttu-id="44c60-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44c60-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44c60-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="44c60-110">S_OK</span></span>|<span data-ttu-id="44c60-111">`CreateCrst` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="44c60-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="44c60-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="44c60-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="44c60-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="44c60-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="44c60-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="44c60-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="44c60-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="44c60-115">The call timed out.</span></span>|  
|<span data-ttu-id="44c60-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="44c60-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="44c60-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="44c60-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="44c60-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="44c60-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="44c60-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="44c60-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="44c60-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="44c60-120">E_FAIL</span></span>|<span data-ttu-id="44c60-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="44c60-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="44c60-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="44c60-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="44c60-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="44c60-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="44c60-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="44c60-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="44c60-125">Memoria insufficiente era disponibile per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="44c60-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44c60-126">Note</span><span class="sxs-lookup"><span data-stu-id="44c60-126">Remarks</span></span>  
 <span data-ttu-id="44c60-127">Gli oggetti sezione critica consentono la sincronizzazione simile a quello fornito da un oggetto mutex, ad eccezione del fatto che le sezioni critiche possono essere usate solo dai thread di un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="44c60-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="44c60-128">`CreateCrst` rispecchia Win32 `InitializeCriticalSection` (funzione).</span><span class="sxs-lookup"><span data-stu-id="44c60-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c60-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44c60-129">Requirements</span></span>  
 <span data-ttu-id="44c60-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c60-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c60-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="44c60-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44c60-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="44c60-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44c60-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c60-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c60-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44c60-134">See also</span></span>

- [<span data-ttu-id="44c60-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="44c60-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="44c60-136">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="44c60-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="44c60-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="44c60-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="44c60-138">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="44c60-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="44c60-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="44c60-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="44c60-140">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="44c60-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
