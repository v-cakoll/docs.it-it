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
ms.openlocfilehash: 632b8d43ed459d489825dc796d39864e2ed15ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139419"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="40cc8-102">Metodo IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="40cc8-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="40cc8-103">Crea un oggetto sezione critico con il numero di spin per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="40cc8-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40cc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40cc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40cc8-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="40cc8-106">in Specifica il numero di spin per l'oggetto sezione critica.</span><span class="sxs-lookup"><span data-stu-id="40cc8-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="40cc8-107">out Puntatore all'indirizzo di un'istanza di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) o null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="40cc8-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40cc8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="40cc8-108">Return Value</span></span>  
  
|<span data-ttu-id="40cc8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40cc8-109">HRESULT</span></span>|<span data-ttu-id="40cc8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40cc8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40cc8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="40cc8-111">S_OK</span></span>|<span data-ttu-id="40cc8-112">`CreateCrstWithSpinCount` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="40cc8-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="40cc8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40cc8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40cc8-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="40cc8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40cc8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40cc8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40cc8-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="40cc8-116">The call timed out.</span></span>|  
|<span data-ttu-id="40cc8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40cc8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40cc8-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="40cc8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40cc8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40cc8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40cc8-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="40cc8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40cc8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40cc8-121">E_FAIL</span></span>|<span data-ttu-id="40cc8-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="40cc8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40cc8-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="40cc8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40cc8-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40cc8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="40cc8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="40cc8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="40cc8-126">Memoria insufficiente per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="40cc8-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40cc8-127">Note</span><span class="sxs-lookup"><span data-stu-id="40cc8-127">Remarks</span></span>  
 <span data-ttu-id="40cc8-128">Un numero di spin viene usato solo in un sistema a più processori.</span><span class="sxs-lookup"><span data-stu-id="40cc8-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="40cc8-129">Il numero di spin specifica il numero di volte in cui un thread chiamante deve girare prima di eseguire un'operazione di attesa su un semaforo associato a una sezione critica non disponibile.</span><span class="sxs-lookup"><span data-stu-id="40cc8-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="40cc8-130">Se la sezione critica diventa disponibile durante l'operazione di rotazione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="40cc8-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="40cc8-131">`CreateCrstWithSpinCount` rispecchia la funzione di `InitializeCriticalSectionAndSpinCount` Win32.</span><span class="sxs-lookup"><span data-stu-id="40cc8-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40cc8-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40cc8-132">Requirements</span></span>  
 <span data-ttu-id="40cc8-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40cc8-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40cc8-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40cc8-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40cc8-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40cc8-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40cc8-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40cc8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cc8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40cc8-137">See also</span></span>

- [<span data-ttu-id="40cc8-138">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="40cc8-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="40cc8-139">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="40cc8-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="40cc8-140">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="40cc8-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
