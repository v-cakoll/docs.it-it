---
title: Metodo IHostGCManager::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf915af48262a0f48e85623de95b76ad94d860b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573296"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="350e0-102">Metodo IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="350e0-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="350e0-103">Notifica all'host che common language runtime (CLR) viene ripresa l'esecuzione delle attività nei thread che erano stati sospesi per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="350e0-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="350e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="350e0-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="350e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="350e0-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="350e0-106">[in] La generazione di garbage collection che è appena terminata, da cui sta riprendendo il thread.</span><span class="sxs-lookup"><span data-stu-id="350e0-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="350e0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="350e0-107">Return Value</span></span>  
  
|<span data-ttu-id="350e0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="350e0-108">HRESULT</span></span>|<span data-ttu-id="350e0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="350e0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="350e0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="350e0-110">S_OK</span></span>|<span data-ttu-id="350e0-111">`SuspensionEnding` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="350e0-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="350e0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="350e0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="350e0-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="350e0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="350e0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="350e0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="350e0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="350e0-115">The call timed out.</span></span>|  
|<span data-ttu-id="350e0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="350e0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="350e0-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="350e0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="350e0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="350e0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="350e0-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="350e0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="350e0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="350e0-120">E_FAIL</span></span>|<span data-ttu-id="350e0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="350e0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="350e0-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="350e0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="350e0-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="350e0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="350e0-124">Note</span><span class="sxs-lookup"><span data-stu-id="350e0-124">Remarks</span></span>  
 <span data-ttu-id="350e0-125">CLR chiama `SuspensionEnding` dopo l'esecuzione di una garbage collection, per notificare all'host che il thread viene ripresa l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="350e0-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="350e0-126">Ripianificare il thread che ha effettuata la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="350e0-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="350e0-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="350e0-127">Requirements</span></span>  
 <span data-ttu-id="350e0-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="350e0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="350e0-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="350e0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="350e0-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="350e0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="350e0-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="350e0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350e0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="350e0-132">See also</span></span>
- [<span data-ttu-id="350e0-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="350e0-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="350e0-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="350e0-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="350e0-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="350e0-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="350e0-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="350e0-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="350e0-137">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="350e0-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
