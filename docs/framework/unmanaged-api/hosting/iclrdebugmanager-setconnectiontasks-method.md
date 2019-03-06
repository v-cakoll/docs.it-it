---
title: Metodo ICLRDebugManager::SetConnectionTasks
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb4210972ba15a7ba3c7df5981e668cb5542f5c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471407"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="453ee-102">Metodo ICLRDebugManager::SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="453ee-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="453ee-103">Associa un elenco delle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanze con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="453ee-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="453ee-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="453ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="453ee-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="453ee-106">[in] L'identificatore di specifica dell'host per la connessione a cui associare il `ppCLRTask` matrice.</span><span class="sxs-lookup"><span data-stu-id="453ee-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="453ee-107">[in] Il numero di membri di `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="453ee-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="453ee-108">Questo numero deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="453ee-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="453ee-109">[in] Matrice di `ICLRTask` puntatori da associare alla connessione identificata da `id`.</span><span class="sxs-lookup"><span data-stu-id="453ee-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="453ee-110">Questa matrice deve contenere almeno un membro.</span><span class="sxs-lookup"><span data-stu-id="453ee-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="453ee-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="453ee-111">Return Value</span></span>  
  
|<span data-ttu-id="453ee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="453ee-112">HRESULT</span></span>|<span data-ttu-id="453ee-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="453ee-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="453ee-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="453ee-114">S_OK</span></span>|<span data-ttu-id="453ee-115">`SetConnectionTasks` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="453ee-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="453ee-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="453ee-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="453ee-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="453ee-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="453ee-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="453ee-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="453ee-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="453ee-119">The call timed out.</span></span>|  
|<span data-ttu-id="453ee-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="453ee-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="453ee-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="453ee-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="453ee-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="453ee-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="453ee-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="453ee-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="453ee-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="453ee-124">E_FAIL</span></span>|<span data-ttu-id="453ee-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="453ee-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="453ee-126">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="453ee-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="453ee-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="453ee-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="453ee-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="453ee-128">E_INVALIDARG</span></span>|<span data-ttu-id="453ee-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) non è stato chiamato usando questo valore di `id`, o `dwCount` oppure `id` è zero o uno degli elementi di `ppCLRTask` è null.</span><span class="sxs-lookup"><span data-stu-id="453ee-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="453ee-130">Note</span><span class="sxs-lookup"><span data-stu-id="453ee-130">Remarks</span></span>  
 <span data-ttu-id="453ee-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi `BeginConnection`, `SetConnectionTasks`, e [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="453ee-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="453ee-132">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="453ee-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="453ee-133">`BeginConnection` viene chiamato prima di tutto per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="453ee-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="453ee-134">`SetConnectionTasks` viene chiamato per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="453ee-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="453ee-135">`EndConnection` viene chiamato per ultimo per rimuovere l'associazione tra l'elenco di attività e identificatore o nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="453ee-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453ee-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="453ee-136">Requirements</span></span>  
 <span data-ttu-id="453ee-137">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453ee-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453ee-138">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="453ee-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="453ee-139">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="453ee-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="453ee-140">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453ee-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453ee-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="453ee-141">See also</span></span>
- [<span data-ttu-id="453ee-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="453ee-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="453ee-143">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="453ee-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="453ee-144">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="453ee-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="453ee-145">Metodo EndConnection</span><span class="sxs-lookup"><span data-stu-id="453ee-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="453ee-146">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="453ee-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
