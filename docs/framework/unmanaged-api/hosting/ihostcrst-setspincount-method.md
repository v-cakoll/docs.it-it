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
ms.openlocfilehash: 3ca17a6814b56c0fe781cfb28a35a576f02f1943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090576"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="107c9-102">Metodo IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="107c9-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="107c9-103">Imposta il conteggio della rotazione per l'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="107c9-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="107c9-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="107c9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="107c9-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="107c9-106">[in] Il nuovo conteggio rotazioni corrente `IHostCrst` istanza.</span><span class="sxs-lookup"><span data-stu-id="107c9-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="107c9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="107c9-107">Return Value</span></span>  
  
|<span data-ttu-id="107c9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="107c9-108">HRESULT</span></span>|<span data-ttu-id="107c9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107c9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="107c9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="107c9-110">S_OK</span></span>|`SetSpinCount` <span data-ttu-id="107c9-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="107c9-111">returned successfully.</span></span>|  
|<span data-ttu-id="107c9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="107c9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="107c9-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="107c9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="107c9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="107c9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="107c9-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="107c9-115">The call timed out.</span></span>|  
|<span data-ttu-id="107c9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="107c9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="107c9-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="107c9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="107c9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="107c9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="107c9-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="107c9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="107c9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="107c9-120">E_FAIL</span></span>|<span data-ttu-id="107c9-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="107c9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="107c9-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="107c9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="107c9-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="107c9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="107c9-124">Note</span><span class="sxs-lookup"><span data-stu-id="107c9-124">Remarks</span></span>  
 <span data-ttu-id="107c9-125">Nei sistemi multiprocessore, se la sezione critica rappresentato dall'oggetto corrente `IHostCrst` istanza non è disponibile, un thread di chiamata ruota `dwSpinCount` volte prima di chiamare [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) su un semaforo associato con la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="107c9-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="107c9-126">Se durante l'operazione di selezione non è più disponibile nella sezione critica, il thread chiamante consente di evitare l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="107c9-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="107c9-127">L'utilizzo delle `dwSpinCount` è identica per l'utilizzo del parametro con lo stesso nome in Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="107c9-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="107c9-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="107c9-128">Requirements</span></span>  
 <span data-ttu-id="107c9-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="107c9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107c9-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="107c9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="107c9-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="107c9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="107c9-132">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="107c9-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="107c9-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="107c9-133">See also</span></span>

- [<span data-ttu-id="107c9-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="107c9-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="107c9-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="107c9-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="107c9-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="107c9-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
