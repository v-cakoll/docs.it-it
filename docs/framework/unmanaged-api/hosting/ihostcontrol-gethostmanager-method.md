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
ms.openlocfilehash: 25e931ec17cad3508d548fb4ca7e53b0ade3f119
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804959"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="a907c-102">Metodo IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="a907c-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="a907c-103">Ottiene un puntatore di interfaccia all'implementazione dell'host dell'interfaccia con l'oggetto specificato `IID` .</span><span class="sxs-lookup"><span data-stu-id="a907c-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a907c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a907c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a907c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a907c-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="a907c-106">in Oggetto `IID` dell'interfaccia per cui viene eseguita la query del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a907c-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a907c-107">out Puntatore all'interfaccia implementata dall'host oppure null se l'host non supporta questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a907c-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a907c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a907c-108">Return Value</span></span>  
  
|<span data-ttu-id="a907c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a907c-109">HRESULT</span></span>|<span data-ttu-id="a907c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a907c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a907c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a907c-111">S_OK</span></span>|<span data-ttu-id="a907c-112">`GetHostManager`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a907c-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="a907c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a907c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a907c-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a907c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a907c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a907c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a907c-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a907c-116">The call timed out.</span></span>|  
|<span data-ttu-id="a907c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a907c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a907c-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a907c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a907c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a907c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a907c-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a907c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a907c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a907c-121">E_FAIL</span></span>|<span data-ttu-id="a907c-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a907c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a907c-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a907c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a907c-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a907c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a907c-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a907c-125">E_INVALIDARG</span></span>|<span data-ttu-id="a907c-126">La richiesta `IID` non è valida.</span><span class="sxs-lookup"><span data-stu-id="a907c-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="a907c-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a907c-127">E_NOINTERFACE</span></span>|<span data-ttu-id="a907c-128">L'interfaccia richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="a907c-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a907c-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a907c-129">Remarks</span></span>  
 <span data-ttu-id="a907c-130">CLR esegue una query sull'host per determinare se supporta una o più delle interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="a907c-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="a907c-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a907c-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="a907c-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a907c-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="a907c-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a907c-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="a907c-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a907c-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="a907c-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a907c-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="a907c-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="a907c-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="a907c-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="a907c-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="a907c-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a907c-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="a907c-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a907c-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="a907c-140">Se l'host supporta l'interfaccia specificata, imposta sulla `ppObject` relativa implementazione di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a907c-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="a907c-141">In caso contrario, viene impostato `ppObject` su null.</span><span class="sxs-lookup"><span data-stu-id="a907c-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="a907c-142">CLR non chiama `Release` sui gestori host, neanche quando viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="a907c-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a907c-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a907c-143">Requirements</span></span>  
 <span data-ttu-id="a907c-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a907c-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a907c-145">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a907c-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a907c-146">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a907c-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a907c-147">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a907c-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a907c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a907c-148">See also</span></span>

- [<span data-ttu-id="a907c-149">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="a907c-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
