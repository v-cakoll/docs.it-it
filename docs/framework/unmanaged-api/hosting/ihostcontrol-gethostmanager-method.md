---
title: Metodo IHostControl::GetHostManager
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 459691354ec12f61c7ab321fe832d8fc802a36d9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494298"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="3aa6d-102">Metodo IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="3aa6d-103">Ottiene un puntatore a interfaccia per l'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID`.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aa6d-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aa6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3aa6d-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="3aa6d-106">[in] Il `IID` dell'interfaccia che common language runtime (CLR) sta eseguendo una query per.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3aa6d-107">[out] Un puntatore di interfaccia implementato dall'host, o null se l'host non supporta questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3aa6d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3aa6d-108">Return Value</span></span>  
  
|<span data-ttu-id="3aa6d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3aa6d-109">HRESULT</span></span>|<span data-ttu-id="3aa6d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa6d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3aa6d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3aa6d-111">S_OK</span></span>|<span data-ttu-id="3aa6d-112">`GetHostManager` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="3aa6d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3aa6d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3aa6d-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3aa6d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3aa6d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3aa6d-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-116">The call timed out.</span></span>|  
|<span data-ttu-id="3aa6d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3aa6d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3aa6d-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3aa6d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3aa6d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3aa6d-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3aa6d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3aa6d-121">E_FAIL</span></span>|<span data-ttu-id="3aa6d-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3aa6d-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3aa6d-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3aa6d-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3aa6d-125">E_INVALIDARG</span></span>|<span data-ttu-id="3aa6d-126">La richiesta `IID` non è valido.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="3aa6d-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="3aa6d-127">E_NOINTERFACE</span></span>|<span data-ttu-id="3aa6d-128">L'interfaccia richiesta non è supportato.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aa6d-129">Note</span><span class="sxs-lookup"><span data-stu-id="3aa6d-129">Remarks</span></span>  
 <span data-ttu-id="3aa6d-130">CLR esegue query sull'host per determinare se supporta uno o più delle interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aa6d-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="3aa6d-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="3aa6d-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="3aa6d-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="3aa6d-140">Se l'host supporta l'interfaccia specificata, il sistema imposta `ppObject` alla relativa implementazione di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="3aa6d-141">In caso contrario, imposta `ppObject` su null.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="3aa6d-142">CLR non chiama `Release` sugli amministratori dell'host, anche quando si arresta.</span><span class="sxs-lookup"><span data-stu-id="3aa6d-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa6d-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aa6d-143">Requirements</span></span>  
 <span data-ttu-id="3aa6d-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa6d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa6d-145">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3aa6d-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3aa6d-146">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3aa6d-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3aa6d-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa6d-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa6d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aa6d-148">See also</span></span>
- [<span data-ttu-id="3aa6d-149">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="3aa6d-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
