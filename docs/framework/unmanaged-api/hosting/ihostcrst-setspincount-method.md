---
title: Metodo IHostCrst::SetSpinCount
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbce5e61f2013513d2079b5a958270319d34857
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763753"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="9f652-102">Metodo IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="9f652-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="9f652-103">Imposta il conteggio della rotazione per l'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="9f652-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f652-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f652-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f652-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f652-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="9f652-106">[in] Il nuovo conteggio rotazioni corrente `IHostCrst` istanza.</span><span class="sxs-lookup"><span data-stu-id="9f652-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f652-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f652-107">Return Value</span></span>  
  
|<span data-ttu-id="9f652-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f652-108">HRESULT</span></span>|<span data-ttu-id="9f652-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f652-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f652-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f652-110">S_OK</span></span>|<span data-ttu-id="9f652-111">`SetSpinCount` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9f652-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="9f652-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f652-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f652-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f652-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f652-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f652-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f652-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f652-115">The call timed out.</span></span>|  
|<span data-ttu-id="9f652-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f652-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f652-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="9f652-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f652-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f652-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f652-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9f652-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f652-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f652-120">E_FAIL</span></span>|<span data-ttu-id="9f652-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9f652-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f652-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9f652-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f652-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9f652-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f652-124">Note</span><span class="sxs-lookup"><span data-stu-id="9f652-124">Remarks</span></span>  
 <span data-ttu-id="9f652-125">Nei sistemi multiprocessore, se la sezione critica rappresentato dall'oggetto corrente `IHostCrst` istanza non è disponibile, un thread di chiamata ruota `dwSpinCount` volte prima di chiamare [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) su un semaforo associato con la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="9f652-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="9f652-126">Se durante l'operazione di selezione non è più disponibile nella sezione critica, il thread chiamante consente di evitare l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="9f652-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="9f652-127">L'utilizzo delle `dwSpinCount` è identica per l'utilizzo del parametro con lo stesso nome in Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="9f652-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f652-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f652-128">Requirements</span></span>  
 <span data-ttu-id="9f652-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f652-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f652-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f652-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f652-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9f652-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f652-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f652-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f652-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f652-133">See also</span></span>

- [<span data-ttu-id="9f652-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9f652-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9f652-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="9f652-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="9f652-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9f652-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
