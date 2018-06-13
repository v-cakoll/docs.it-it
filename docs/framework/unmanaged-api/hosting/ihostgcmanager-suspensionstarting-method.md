---
title: Metodo IHostGCManager::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a84da2a337554873e94b47eb51916088edbb5a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439033"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="e69a5-102">Metodo IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="e69a5-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="e69a5-103">Notifica all'host che common language runtime (CLR) sta sospendendo l'esecuzione delle attività, per eseguire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e69a5-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e69a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e69a5-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e69a5-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e69a5-105">Return Value</span></span>  
  
|<span data-ttu-id="e69a5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e69a5-106">HRESULT</span></span>|<span data-ttu-id="e69a5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e69a5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e69a5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e69a5-108">S_OK</span></span>|<span data-ttu-id="e69a5-109">`SuspensionStarting` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e69a5-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="e69a5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e69a5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e69a5-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e69a5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e69a5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e69a5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e69a5-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e69a5-113">The call timed out.</span></span>|  
|<span data-ttu-id="e69a5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e69a5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e69a5-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="e69a5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e69a5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e69a5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e69a5-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e69a5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e69a5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e69a5-118">E_FAIL</span></span>|<span data-ttu-id="e69a5-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e69a5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e69a5-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e69a5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e69a5-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e69a5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e69a5-122">Note</span><span class="sxs-lookup"><span data-stu-id="e69a5-122">Remarks</span></span>  
 <span data-ttu-id="e69a5-123">CLR chiama `SuspensionStarting` per notificare all'host che l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e69a5-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e69a5-124">Ripianificare l'attività.</span><span class="sxs-lookup"><span data-stu-id="e69a5-124">Do not reschedule this task.</span></span> <span data-ttu-id="e69a5-125">L'host deve modificare la pianificazione di un'attività quando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="e69a5-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e69a5-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e69a5-126">Requirements</span></span>  
 <span data-ttu-id="e69a5-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e69a5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e69a5-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e69a5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e69a5-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e69a5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e69a5-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e69a5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69a5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e69a5-131">See Also</span></span>  
 [<span data-ttu-id="e69a5-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e69a5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e69a5-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e69a5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e69a5-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="e69a5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e69a5-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e69a5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="e69a5-136">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="e69a5-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
