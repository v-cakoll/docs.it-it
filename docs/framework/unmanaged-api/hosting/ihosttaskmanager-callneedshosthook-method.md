---
title: Metodo IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adc270be51988cba78c6e522b16b480baef725c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139230"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="2c2fe-102">Metodo IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="2c2fe-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="2c2fe-103">Consente all'host specificare se common language runtime (CLR) è possibile incorporare la chiamata a una funzione non gestita specificata.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c2fe-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c2fe-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="2c2fe-106">[in] L'indirizzo all'interno del file mappato eseguibile portabile (PE) della funzione non gestito che deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="2c2fe-107">[out] Un puntatore a un valore booleano che indica se l'host richiede la chiamata a eseguire l'hook.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c2fe-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c2fe-108">Return Value</span></span>  
  
|<span data-ttu-id="2c2fe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c2fe-109">HRESULT</span></span>|<span data-ttu-id="2c2fe-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c2fe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c2fe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c2fe-111">S_OK</span></span>|<span data-ttu-id="2c2fe-112">`CallNeedsHostHook` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="2c2fe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c2fe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c2fe-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c2fe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c2fe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c2fe-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-116">The call timed out.</span></span>|  
|<span data-ttu-id="2c2fe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c2fe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c2fe-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c2fe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c2fe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c2fe-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c2fe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c2fe-121">E_FAIL</span></span>|<span data-ttu-id="2c2fe-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="2c2fe-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c2fe-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c2fe-125">Note</span><span class="sxs-lookup"><span data-stu-id="2c2fe-125">Remarks</span></span>  
 <span data-ttu-id="2c2fe-126">Per ottimizzare l'esecuzione di codice, CLR esegue un'analisi di ogni piattaforma chiamata invoke durante la compilazione per determinare se la chiamata può essere impostato come inline.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="2c2fe-127">`CallNeedsHostHook` consente all'host eseguire l'override di questa decisione, richiedendo l'hook una chiamata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="2c2fe-128">Se l'host necessita di una funzione hook, il runtime non rende inline della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="2c2fe-129">L'host in genere richiederebbe un hook di quando è necessario modificare uno stato a virgola mobile, o dopo aver ricevuto la notifica che una chiamata sta entrando in uno stato in cui l'host non è possibile tenere traccia richieste del runtime per la memoria o di eventuali blocchi acquisiti.</span><span class="sxs-lookup"><span data-stu-id="2c2fe-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="2c2fe-130">Quando l'host richiede che la chiamata di hook, il runtime di notifica all'host di transizioni da e verso il codice gestito tramite le chiamate a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), e [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="2c2fe-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2fe-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c2fe-131">Requirements</span></span>  
 <span data-ttu-id="2c2fe-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2fe-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2fe-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c2fe-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c2fe-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2c2fe-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2fe-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2fe-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2fe-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c2fe-136">See also</span></span>

- [<span data-ttu-id="2c2fe-137">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2c2fe-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2c2fe-138">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2c2fe-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2c2fe-139">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="2c2fe-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2c2fe-140">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2c2fe-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
