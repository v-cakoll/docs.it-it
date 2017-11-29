---
title: Metodo IHostCrst::SetSpinCount
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.SetSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19172c6d498e5066c102c642105d78d10b26212c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="8d591-102">Metodo IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="8d591-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="8d591-103">Imposta il conteggio di selezione per l'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="8d591-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d591-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d591-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d591-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d591-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="8d591-106">[in] Nuovo numero di selezione per corrente `IHostCrst` istanza.</span><span class="sxs-lookup"><span data-stu-id="8d591-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d591-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d591-107">Return Value</span></span>  
  
|<span data-ttu-id="8d591-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d591-108">HRESULT</span></span>|<span data-ttu-id="8d591-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d591-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d591-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d591-110">S_OK</span></span>|<span data-ttu-id="8d591-111">`SetSpinCount`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d591-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="8d591-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d591-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d591-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d591-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d591-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d591-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d591-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d591-115">The call timed out.</span></span>|  
|<span data-ttu-id="8d591-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d591-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d591-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="8d591-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d591-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d591-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d591-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8d591-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d591-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d591-120">E_FAIL</span></span>|<span data-ttu-id="8d591-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8d591-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d591-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8d591-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d591-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8d591-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d591-124">Note</span><span class="sxs-lookup"><span data-stu-id="8d591-124">Remarks</span></span>  
 <span data-ttu-id="8d591-125">Nei sistemi multiprocessore, se la sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza non è disponibile, un thread chiamante esegue `dwSpinCount` volte prima di chiamare [IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) su un semaforo associato con la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="8d591-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="8d591-126">Se la sezione critica diventa disponibile durante l'operazione di selezione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="8d591-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="8d591-127">L'utilizzo di `dwSpinCount` è identico a quello del parametro con lo stesso nome in Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8d591-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d591-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d591-128">Requirements</span></span>  
 <span data-ttu-id="8d591-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d591-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d591-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8d591-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d591-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d591-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d591-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d591-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d591-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d591-133">See Also</span></span>  
 [<span data-ttu-id="8d591-134">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8d591-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8d591-135">IHostCrst (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8d591-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="8d591-136">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8d591-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
