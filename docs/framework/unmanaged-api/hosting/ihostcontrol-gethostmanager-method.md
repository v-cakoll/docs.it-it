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
ms.openlocfilehash: c23773dce448c8c98d4926dff3fa51100e683fd0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192044"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="c3166-102">Metodo IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="c3166-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="c3166-103">Ottiene un puntatore di interfaccia all'implementazione dell'host dell'interfaccia con la `IID`specificata.</span><span class="sxs-lookup"><span data-stu-id="c3166-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3166-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3166-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3166-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3166-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="c3166-106">in `IID` dell'interfaccia per cui viene eseguita la query per il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c3166-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c3166-107">out Puntatore all'interfaccia implementata dall'host oppure null se l'host non supporta questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c3166-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3166-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3166-108">Return Value</span></span>  
  
|<span data-ttu-id="c3166-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3166-109">HRESULT</span></span>|<span data-ttu-id="c3166-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3166-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3166-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3166-111">S_OK</span></span>|<span data-ttu-id="c3166-112">`GetHostManager` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c3166-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="c3166-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3166-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3166-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3166-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3166-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3166-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3166-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c3166-116">The call timed out.</span></span>|  
|<span data-ttu-id="c3166-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3166-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3166-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c3166-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3166-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3166-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3166-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c3166-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3166-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3166-121">E_FAIL</span></span>|<span data-ttu-id="c3166-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c3166-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3166-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c3166-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3166-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c3166-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c3166-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c3166-125">E_INVALIDARG</span></span>|<span data-ttu-id="c3166-126">Il `IID` richiesto non è valido.</span><span class="sxs-lookup"><span data-stu-id="c3166-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="c3166-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c3166-127">E_NOINTERFACE</span></span>|<span data-ttu-id="c3166-128">L'interfaccia richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="c3166-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3166-129">Note</span><span class="sxs-lookup"><span data-stu-id="c3166-129">Remarks</span></span>  
 <span data-ttu-id="c3166-130">CLR esegue una query sull'host per determinare se supporta una o più delle interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3166-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="c3166-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c3166-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="c3166-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c3166-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="c3166-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c3166-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="c3166-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c3166-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="c3166-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c3166-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="c3166-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c3166-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="c3166-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="c3166-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="c3166-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c3166-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="c3166-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c3166-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="c3166-140">Se l'host supporta l'interfaccia specificata, imposta `ppObject` alla relativa implementazione di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c3166-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="c3166-141">In caso contrario, imposta `ppObject` su null.</span><span class="sxs-lookup"><span data-stu-id="c3166-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="c3166-142">CLR non chiama `Release` nei gestori host, neanche quando viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="c3166-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3166-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3166-143">Requirements</span></span>  
 <span data-ttu-id="c3166-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3166-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3166-145">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3166-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3166-146">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c3166-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3166-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3166-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3166-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3166-148">See also</span></span>

- [<span data-ttu-id="c3166-149">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="c3166-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
