---
title: Metodo ICLRDebugManager::BeginConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.BeginConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 302b2abfdde7bbccbef51de21233948d042420be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="0eec0-102">Metodo ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="0eec0-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="0eec0-103">Stabilisce una nuova connessione tra l'host e il debugger per associare un elenco di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="0eec0-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eec0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0eec0-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0eec0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0eec0-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="0eec0-106">[in] Identificatore da associare all'elenco attività di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0eec0-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="0eec0-107">[in] Un nome descrittivo per associare l'elenco di attività CLR.</span><span class="sxs-lookup"><span data-stu-id="0eec0-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eec0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0eec0-108">Return Value</span></span>  
  
|<span data-ttu-id="0eec0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0eec0-109">HRESULT</span></span>|<span data-ttu-id="0eec0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0eec0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0eec0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0eec0-111">S_OK</span></span>|<span data-ttu-id="0eec0-112">`BeginConnection`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0eec0-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="0eec0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0eec0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0eec0-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0eec0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0eec0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0eec0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0eec0-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0eec0-116">The call timed out.</span></span>|  
|<span data-ttu-id="0eec0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0eec0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0eec0-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="0eec0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0eec0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0eec0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0eec0-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0eec0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0eec0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0eec0-121">E_FAIL</span></span>|<span data-ttu-id="0eec0-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0eec0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0eec0-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0eec0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0eec0-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0eec0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0eec0-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0eec0-125">E_INVALIDARG</span></span>|<span data-ttu-id="0eec0-126">`dwConnectionId`è zero o `BeginConnection` è già stato chiamato utilizzando questo `dwConnectionId` valore, o `szConnectionName` è null.</span><span class="sxs-lookup"><span data-stu-id="0eec0-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="0eec0-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0eec0-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0eec0-128">Impossibile allocare memoria insufficiente per contenere l'elenco di attività associata alla connessione.</span><span class="sxs-lookup"><span data-stu-id="0eec0-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eec0-129">Note</span><span class="sxs-lookup"><span data-stu-id="0eec0-129">Remarks</span></span>  
 <span data-ttu-id="0eec0-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), e [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="0eec0-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0eec0-131">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="0eec0-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="0eec0-132">`BeginConnection`viene chiamato prima di tutto per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="0eec0-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="0eec0-133">`SetConnectionTasks`viene chiamato per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="0eec0-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="0eec0-134">`EndConnection`Infine viene chiamato per rimuovere l'associazione tra l'elenco di attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="0eec0-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eec0-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0eec0-135">Requirements</span></span>  
 <span data-ttu-id="0eec0-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eec0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eec0-137">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0eec0-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0eec0-138">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0eec0-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0eec0-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eec0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eec0-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eec0-140">See Also</span></span>  
 [<span data-ttu-id="0eec0-141">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0eec0-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0eec0-142">ICLRDebugManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0eec0-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="0eec0-143">EndConnection (metodo)</span><span class="sxs-lookup"><span data-stu-id="0eec0-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="0eec0-144">SetConnectionTasks (metodo)</span><span class="sxs-lookup"><span data-stu-id="0eec0-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="0eec0-145">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0eec0-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
