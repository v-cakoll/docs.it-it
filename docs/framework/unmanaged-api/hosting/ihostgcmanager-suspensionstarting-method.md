---
title: Metodo IHostGCManager::SuspensionStarting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="6d315-102">Metodo IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="6d315-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="6d315-103">Notifica all'host che common language runtime (CLR) sta sospendendo l'esecuzione delle attività, per eseguire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6d315-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d315-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d315-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6d315-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6d315-105">Return Value</span></span>  
  
|<span data-ttu-id="6d315-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d315-106">HRESULT</span></span>|<span data-ttu-id="6d315-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d315-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d315-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d315-108">S_OK</span></span>|<span data-ttu-id="6d315-109">`SuspensionStarting`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6d315-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="6d315-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d315-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d315-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6d315-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d315-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d315-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d315-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6d315-113">The call timed out.</span></span>|  
|<span data-ttu-id="6d315-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d315-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d315-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="6d315-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d315-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d315-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d315-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6d315-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d315-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d315-118">E_FAIL</span></span>|<span data-ttu-id="6d315-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6d315-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d315-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6d315-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d315-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6d315-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d315-122">Note</span><span class="sxs-lookup"><span data-stu-id="6d315-122">Remarks</span></span>  
 <span data-ttu-id="6d315-123">CLR chiama `SuspensionStarting` per notificare all'host che l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6d315-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d315-124">Ripianificare l'attività.</span><span class="sxs-lookup"><span data-stu-id="6d315-124">Do not reschedule this task.</span></span> <span data-ttu-id="6d315-125">L'host deve modificare la pianificazione di un'attività quando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6d315-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d315-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d315-126">Requirements</span></span>  
 <span data-ttu-id="6d315-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d315-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d315-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6d315-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d315-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d315-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d315-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d315-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d315-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d315-131">See Also</span></span>  
 [<span data-ttu-id="6d315-132">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d315-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6d315-133">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d315-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6d315-134">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d315-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6d315-135">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d315-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="6d315-136">IHostGCManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d315-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
