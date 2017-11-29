---
title: Metodo IHostGCManager::SuspensionEnding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9952e62d4979efa0d07b19f183ca71adcc643365
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="3c75d-102">Metodo IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="3c75d-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="3c75d-103">Notifica all'host che common language runtime (CLR) viene ripresa l'esecuzione delle attività nel thread che era stato sospeso per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3c75d-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c75d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c75d-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c75d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c75d-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="3c75d-106">[in] La generazione di garbage collection appena terminata, da cui il thread viene ripresa.</span><span class="sxs-lookup"><span data-stu-id="3c75d-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c75d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c75d-107">Return Value</span></span>  
  
|<span data-ttu-id="3c75d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c75d-108">HRESULT</span></span>|<span data-ttu-id="3c75d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c75d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c75d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c75d-110">S_OK</span></span>|<span data-ttu-id="3c75d-111">`SuspensionEnding`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c75d-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="3c75d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c75d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c75d-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c75d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c75d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c75d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c75d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c75d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3c75d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c75d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c75d-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3c75d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c75d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c75d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c75d-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3c75d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c75d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c75d-120">E_FAIL</span></span>|<span data-ttu-id="3c75d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3c75d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c75d-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3c75d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c75d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c75d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c75d-124">Note</span><span class="sxs-lookup"><span data-stu-id="3c75d-124">Remarks</span></span>  
 <span data-ttu-id="3c75d-125">CLR chiama `SuspensionEnding` dopo l'esecuzione di una garbage collection, per informare l'host che il thread è ripresa dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c75d-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c75d-126">Ripianificare il thread che ha effettuata la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="3c75d-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c75d-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c75d-127">Requirements</span></span>  
 <span data-ttu-id="3c75d-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c75d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c75d-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3c75d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c75d-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c75d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c75d-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c75d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c75d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c75d-132">See Also</span></span>  
 [<span data-ttu-id="3c75d-133">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c75d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3c75d-134">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c75d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3c75d-135">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c75d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3c75d-136">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c75d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3c75d-137">IHostGCManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c75d-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
