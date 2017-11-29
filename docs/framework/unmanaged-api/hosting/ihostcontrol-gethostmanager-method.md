---
title: Metodo IHostControl::GetHostManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl.GetHostManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c711fb2ddf5d21cd8e122a35ebd0b8a5ce0e752f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="935aa-102">Metodo IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="935aa-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="935aa-103">Ottiene un puntatore a interfaccia per l'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID`.</span><span class="sxs-lookup"><span data-stu-id="935aa-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="935aa-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="935aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="935aa-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="935aa-106">[in] Il `IID` dell'interfaccia che sta eseguendo una query per common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="935aa-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="935aa-107">[out] Puntatore a interfaccia implementata host oppure null se l'host non supporta questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="935aa-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="935aa-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="935aa-108">Return Value</span></span>  
  
|<span data-ttu-id="935aa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="935aa-109">HRESULT</span></span>|<span data-ttu-id="935aa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="935aa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="935aa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="935aa-111">S_OK</span></span>|<span data-ttu-id="935aa-112">`GetHostManager`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="935aa-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="935aa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="935aa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="935aa-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="935aa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="935aa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="935aa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="935aa-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="935aa-116">The call timed out.</span></span>|  
|<span data-ttu-id="935aa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="935aa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="935aa-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="935aa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="935aa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="935aa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="935aa-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="935aa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="935aa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="935aa-121">E_FAIL</span></span>|<span data-ttu-id="935aa-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="935aa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="935aa-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="935aa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="935aa-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="935aa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="935aa-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="935aa-125">E_INVALIDARG</span></span>|<span data-ttu-id="935aa-126">La richiesta `IID` non è valido.</span><span class="sxs-lookup"><span data-stu-id="935aa-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="935aa-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="935aa-127">E_NOINTERFACE</span></span>|<span data-ttu-id="935aa-128">L'interfaccia richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="935aa-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="935aa-129">Note</span><span class="sxs-lookup"><span data-stu-id="935aa-129">Remarks</span></span>  
 <span data-ttu-id="935aa-130">Common Language Runtime esegue la query per determinare se supporta uno o più delle interfacce seguenti host:</span><span class="sxs-lookup"><span data-stu-id="935aa-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="935aa-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="935aa-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="935aa-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="935aa-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="935aa-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="935aa-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="935aa-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="935aa-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="935aa-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="935aa-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="935aa-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="935aa-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="935aa-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="935aa-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="935aa-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="935aa-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="935aa-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="935aa-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="935aa-140">Se l'host supporta l'interfaccia specificata, imposta `ppObject` alla relativa implementazione di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="935aa-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="935aa-141">In caso contrario, imposta `ppObject` su null.</span><span class="sxs-lookup"><span data-stu-id="935aa-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="935aa-142">CLR non chiama `Release` sui gestori di host, anche quando si arresta.</span><span class="sxs-lookup"><span data-stu-id="935aa-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935aa-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="935aa-143">Requirements</span></span>  
 <span data-ttu-id="935aa-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="935aa-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935aa-145">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="935aa-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="935aa-146">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="935aa-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="935aa-147">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="935aa-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935aa-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="935aa-148">See Also</span></span>  
 [<span data-ttu-id="935aa-149">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="935aa-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
