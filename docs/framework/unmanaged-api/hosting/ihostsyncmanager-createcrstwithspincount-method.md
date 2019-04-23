---
title: Metodo IHostSyncManager::CreateCrstWithSpinCount
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a288edc89029804de277484741c1895af7859b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081528"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="a981f-102">Metodo IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="a981f-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="a981f-103">Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="a981f-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a981f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a981f-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a981f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a981f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="a981f-106">[in] Specifica il conteggio della rotazione per l'oggetto sezione critica.</span><span class="sxs-lookup"><span data-stu-id="a981f-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="a981f-107">[out] Un puntatore all'indirizzo di un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza oppure null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="a981f-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a981f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a981f-108">Return Value</span></span>  
  
|<span data-ttu-id="a981f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a981f-109">HRESULT</span></span>|<span data-ttu-id="a981f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a981f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a981f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a981f-111">S_OK</span></span>|<span data-ttu-id="a981f-112">`CreateCrstWithSpinCount` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a981f-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="a981f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a981f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a981f-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a981f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a981f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a981f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a981f-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a981f-116">The call timed out.</span></span>|  
|<span data-ttu-id="a981f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a981f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a981f-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="a981f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a981f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a981f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a981f-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a981f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a981f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a981f-121">E_FAIL</span></span>|<span data-ttu-id="a981f-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a981f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a981f-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a981f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a981f-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a981f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a981f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a981f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a981f-126">Memoria insufficiente era disponibile per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="a981f-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a981f-127">Note</span><span class="sxs-lookup"><span data-stu-id="a981f-127">Remarks</span></span>  
 <span data-ttu-id="a981f-128">Il numero spin viene utilizzato solo in un sistema multiprocessore.</span><span class="sxs-lookup"><span data-stu-id="a981f-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="a981f-129">Il numero spin specifica il numero di volte in cui che un thread di chiamata è necessario attivare prima di eseguire un'operazione di attesa su un semaforo associata a una sezione critica non disponibile.</span><span class="sxs-lookup"><span data-stu-id="a981f-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="a981f-130">Se durante l'operazione di selezione non è più disponibile nella sezione critica, il thread chiamante consente di evitare l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="a981f-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="a981f-131">`CreateCrstWithSpinCount` rispecchia Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="a981f-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a981f-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a981f-132">Requirements</span></span>  
 <span data-ttu-id="a981f-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a981f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a981f-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a981f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a981f-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a981f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a981f-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a981f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a981f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a981f-137">See also</span></span>

- [<span data-ttu-id="a981f-138">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a981f-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a981f-139">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a981f-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="a981f-140">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a981f-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
