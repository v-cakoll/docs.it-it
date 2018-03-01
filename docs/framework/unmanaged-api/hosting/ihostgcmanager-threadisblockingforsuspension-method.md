---
title: Metodo IHostGCManager::ThreadIsBlockingForSuspension
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93f17e687ebc3d121db36d8fce8b6bd514867a91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="8e3c1-102">Metodo IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="8e3c1-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="8e3c1-103">Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo per essere bloccato per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e3c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e3c1-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e3c1-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8e3c1-105">Return Value</span></span>  
  
|<span data-ttu-id="8e3c1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e3c1-106">HRESULT</span></span>|<span data-ttu-id="8e3c1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e3c1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e3c1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e3c1-108">S_OK</span></span>|<span data-ttu-id="8e3c1-109">`ThreadIsBlockingForSuspension`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="8e3c1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e3c1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e3c1-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e3c1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e3c1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e3c1-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-113">The call timed out.</span></span>|  
|<span data-ttu-id="8e3c1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e3c1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e3c1-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e3c1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e3c1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e3c1-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e3c1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e3c1-118">E_FAIL</span></span>|<span data-ttu-id="8e3c1-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e3c1-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e3c1-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e3c1-122">Note</span><span class="sxs-lookup"><span data-stu-id="8e3c1-122">Remarks</span></span>  
 <span data-ttu-id="8e3c1-123">CLR chiama in genere il `ThreadIsBlockForSuspension` metodo in preparazione per una garbage collection, per consentire all'host di ripianificare il thread per le attività non gestite.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e3c1-124">L'host può ripianificazione delle attività solo dopo una chiamata a `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="8e3c1-125">Dopo il runtime chiama [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), l'host non è necessario ripianificare un'attività.</span><span class="sxs-lookup"><span data-stu-id="8e3c1-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e3c1-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e3c1-126">Requirements</span></span>  
 <span data-ttu-id="8e3c1-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e3c1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e3c1-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8e3c1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e3c1-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e3c1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e3c1-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e3c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3c1-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e3c1-131">See Also</span></span>  
 [<span data-ttu-id="8e3c1-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8e3c1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8e3c1-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8e3c1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8e3c1-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8e3c1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8e3c1-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8e3c1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="8e3c1-136">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="8e3c1-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
