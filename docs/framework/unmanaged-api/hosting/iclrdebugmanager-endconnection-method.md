---
title: Metodo ICLRDebugManager::EndConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.EndConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 114f2217d22fc270b03d271db4acc44f0edbcca8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="35821-102">Metodo ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="35821-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="35821-103">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="35821-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35821-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35821-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35821-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35821-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="35821-106">[in] L'identificatore di specifica dell'host per la connessione e l'elenco attività di common language runtime (CLR) associato.</span><span class="sxs-lookup"><span data-stu-id="35821-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35821-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35821-107">Return Value</span></span>  
  
|<span data-ttu-id="35821-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35821-108">HRESULT</span></span>|<span data-ttu-id="35821-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35821-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35821-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="35821-110">S_OK</span></span>|<span data-ttu-id="35821-111">`EndConnection`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="35821-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="35821-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35821-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35821-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35821-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35821-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35821-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35821-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="35821-115">The call timed out.</span></span>|  
|<span data-ttu-id="35821-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35821-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35821-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="35821-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35821-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35821-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35821-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="35821-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35821-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35821-120">E_FAIL</span></span>|<span data-ttu-id="35821-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="35821-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35821-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="35821-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35821-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="35821-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="35821-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="35821-124">E_INVALIDARG</span></span>|<span data-ttu-id="35821-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) non è mai stato chiamato tramite `dwConnectionId`, o `dwConnectionId` è zero.</span><span class="sxs-lookup"><span data-stu-id="35821-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35821-126">Note</span><span class="sxs-lookup"><span data-stu-id="35821-126">Remarks</span></span>  
 <span data-ttu-id="35821-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), e `EndConnection`, per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="35821-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35821-128">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="35821-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="35821-129">`BeginConnection`viene chiamato prima di tutto per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="35821-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="35821-130">`SetConnectionTasks`viene chiamato per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="35821-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="35821-131">`EndConnection`Infine viene chiamato per rimuovere l'associazione tra l'elenco di attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="35821-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35821-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35821-132">Requirements</span></span>  
 <span data-ttu-id="35821-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35821-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35821-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="35821-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35821-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35821-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35821-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35821-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35821-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35821-137">See Also</span></span>  
 [<span data-ttu-id="35821-138">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35821-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="35821-139">ICLRDebugManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35821-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="35821-140">BeginConnection (metodo)</span><span class="sxs-lookup"><span data-stu-id="35821-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="35821-141">SetConnectionTasks (metodo)</span><span class="sxs-lookup"><span data-stu-id="35821-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="35821-142">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="35821-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
