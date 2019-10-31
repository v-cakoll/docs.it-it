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
ms.openlocfilehash: bf1b830f55110c00356527bc9caa41dfd94ae377
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130461"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="3e36e-102">Metodo IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="3e36e-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="3e36e-103">Notifica all'host che la Common Language Runtime (CLR) sospende l'esecuzione delle attività, per eseguire una Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3e36e-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e36e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e36e-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3e36e-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e36e-105">Return Value</span></span>  
  
|<span data-ttu-id="3e36e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e36e-106">HRESULT</span></span>|<span data-ttu-id="3e36e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e36e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e36e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e36e-108">S_OK</span></span>|<span data-ttu-id="3e36e-109">`SuspensionStarting` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3e36e-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="3e36e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e36e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e36e-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e36e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e36e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e36e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e36e-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e36e-113">The call timed out.</span></span>|  
|<span data-ttu-id="3e36e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e36e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e36e-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="3e36e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e36e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e36e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e36e-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e36e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e36e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e36e-118">E_FAIL</span></span>|<span data-ttu-id="3e36e-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3e36e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e36e-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3e36e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e36e-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e36e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e36e-122">Note</span><span class="sxs-lookup"><span data-stu-id="3e36e-122">Remarks</span></span>  
 <span data-ttu-id="3e36e-123">CLR chiama `SuspensionStarting` per informare l'host che Garbage Collection si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="3e36e-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3e36e-124">Non ripianificare questa attività.</span><span class="sxs-lookup"><span data-stu-id="3e36e-124">Do not reschedule this task.</span></span> <span data-ttu-id="3e36e-125">L'host deve ripianificare un'attività quando viene chiamato [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3e36e-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e36e-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e36e-126">Requirements</span></span>  
 <span data-ttu-id="3e36e-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e36e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e36e-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e36e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e36e-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e36e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e36e-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e36e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e36e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e36e-131">See also</span></span>

- [<span data-ttu-id="3e36e-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3e36e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3e36e-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3e36e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3e36e-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3e36e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3e36e-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3e36e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3e36e-136">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="3e36e-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
