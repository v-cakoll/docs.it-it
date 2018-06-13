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
ms.openlocfilehash: 4d90bce1f693f571a5d5c5d5dca981d09bce59b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438847"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="7ae79-102">Metodo IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="7ae79-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="7ae79-103">Imposta il conteggio di selezione per l'oggetto corrente [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="7ae79-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ae79-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ae79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ae79-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="7ae79-106">[in] Nuovo numero di selezione per corrente `IHostCrst` istanza.</span><span class="sxs-lookup"><span data-stu-id="7ae79-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ae79-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7ae79-107">Return Value</span></span>  
  
|<span data-ttu-id="7ae79-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ae79-108">HRESULT</span></span>|<span data-ttu-id="7ae79-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ae79-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ae79-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ae79-110">S_OK</span></span>|<span data-ttu-id="7ae79-111">`SetSpinCount` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7ae79-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="7ae79-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ae79-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ae79-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ae79-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ae79-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ae79-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ae79-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ae79-115">The call timed out.</span></span>|  
|<span data-ttu-id="7ae79-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ae79-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ae79-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7ae79-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ae79-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ae79-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ae79-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7ae79-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ae79-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ae79-120">E_FAIL</span></span>|<span data-ttu-id="7ae79-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7ae79-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ae79-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7ae79-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ae79-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7ae79-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ae79-124">Note</span><span class="sxs-lookup"><span data-stu-id="7ae79-124">Remarks</span></span>  
 <span data-ttu-id="7ae79-125">Nei sistemi multiprocessore, se la sezione critica rappresentata dall'oggetto corrente `IHostCrst` istanza non è disponibile, un thread chiamante esegue `dwSpinCount` volte prima di chiamare [IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) su un semaforo associato con la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="7ae79-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="7ae79-126">Se la sezione critica diventa disponibile durante l'operazione di selezione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="7ae79-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="7ae79-127">L'utilizzo di `dwSpinCount` è identico a quello del parametro con lo stesso nome in Win32 `InitializeCriticalSectionAndSpinCount` (funzione).</span><span class="sxs-lookup"><span data-stu-id="7ae79-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae79-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ae79-128">Requirements</span></span>  
 <span data-ttu-id="7ae79-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae79-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae79-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7ae79-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ae79-131">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ae79-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ae79-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae79-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae79-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae79-133">See Also</span></span>  
 [<span data-ttu-id="7ae79-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7ae79-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7ae79-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="7ae79-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="7ae79-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7ae79-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
