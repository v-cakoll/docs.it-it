---
title: Metodo IHostTaskManager::CallNeedsHostHook
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CallNeedsHostHook
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0daa122b3576c1a6e6e192a4992549e704721bb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="29809-102">Metodo IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="29809-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="29809-103">Consente all'host di specificare se common language runtime (CLR) può rendere inline la chiamata a una funzione non gestita specificata.</span><span class="sxs-lookup"><span data-stu-id="29809-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29809-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29809-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29809-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29809-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="29809-106">[in] L'indirizzo all'interno del file mappato eseguibile portabile (PE) della funzione non gestita che deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="29809-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="29809-107">[out] Un puntatore a un valore booleano che indica se l'host richiede che la chiamata a essere associata.</span><span class="sxs-lookup"><span data-stu-id="29809-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29809-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="29809-108">Return Value</span></span>  
  
|<span data-ttu-id="29809-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29809-109">HRESULT</span></span>|<span data-ttu-id="29809-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29809-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29809-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="29809-111">S_OK</span></span>|<span data-ttu-id="29809-112">`CallNeedsHostHook`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="29809-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="29809-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29809-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29809-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29809-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29809-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29809-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29809-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="29809-116">The call timed out.</span></span>|  
|<span data-ttu-id="29809-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29809-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29809-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="29809-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29809-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29809-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29809-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="29809-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29809-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29809-121">E_FAIL</span></span>|<span data-ttu-id="29809-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="29809-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="29809-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="29809-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29809-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="29809-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29809-125">Note</span><span class="sxs-lookup"><span data-stu-id="29809-125">Remarks</span></span>  
 <span data-ttu-id="29809-126">Per ottimizzare l'esecuzione di codice, CLR esegue un'analisi di ogni piattaforma richiamo durante la compilazione per determinare se la chiamata può essere resa inline.</span><span class="sxs-lookup"><span data-stu-id="29809-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="29809-127">`CallNeedsHostHook`consente all'host di eseguire l'override di tale decisione richiedendo l'hook una chiamata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="29809-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="29809-128">Se l'host richiede una funzione hook, il runtime non rende inline la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29809-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="29809-129">L'host in genere richiederebbe un hook quando è necessario modificare uno stato a virgola mobile o alla ricezione di notifica che una chiamata sta entrando in uno stato in cui l'host non è possibile tenere delle richieste traccia di memoria e di eventuali blocchi acquisiti.</span><span class="sxs-lookup"><span data-stu-id="29809-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="29809-130">Quando l'host richiede l'hook di chiamata, il runtime notifica all'host le transizioni da e verso codice gestito mediante chiamate al [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), e [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="29809-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29809-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29809-131">Requirements</span></span>  
 <span data-ttu-id="29809-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29809-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29809-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="29809-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29809-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29809-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29809-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29809-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29809-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29809-136">See Also</span></span>  
 [<span data-ttu-id="29809-137">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="29809-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="29809-138">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="29809-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="29809-139">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="29809-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="29809-140">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="29809-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
