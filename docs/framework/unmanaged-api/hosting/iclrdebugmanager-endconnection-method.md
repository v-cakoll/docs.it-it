---
title: Metodo ICLRDebugManager::EndConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc9d32f83b4b6384e28f012b9329ea18913a1218
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773155"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="8964c-102">Metodo ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="8964c-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="8964c-103">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="8964c-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8964c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8964c-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8964c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8964c-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="8964c-106">[in] L'identificatore di specifica dell'host per la connessione e l'elenco attività di common language runtime (CLR) associato.</span><span class="sxs-lookup"><span data-stu-id="8964c-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8964c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8964c-107">Return Value</span></span>  
  
|<span data-ttu-id="8964c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8964c-108">HRESULT</span></span>|<span data-ttu-id="8964c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8964c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8964c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8964c-110">S_OK</span></span>|<span data-ttu-id="8964c-111">`EndConnection` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8964c-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="8964c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8964c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8964c-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8964c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8964c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8964c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8964c-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8964c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8964c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8964c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8964c-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8964c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8964c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8964c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8964c-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8964c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8964c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8964c-120">E_FAIL</span></span>|<span data-ttu-id="8964c-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8964c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8964c-122">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8964c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8964c-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8964c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8964c-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8964c-124">E_INVALIDARG</span></span>|<span data-ttu-id="8964c-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) non è mai stato chiamato tramite `dwConnectionId`, o `dwConnectionId` è zero.</span><span class="sxs-lookup"><span data-stu-id="8964c-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8964c-126">Note</span><span class="sxs-lookup"><span data-stu-id="8964c-126">Remarks</span></span>  
 <span data-ttu-id="8964c-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), e `EndConnection`, per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="8964c-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8964c-128">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="8964c-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="8964c-129">`BeginConnection` viene chiamato prima di tutto per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="8964c-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="8964c-130">`SetConnectionTasks` viene chiamato per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="8964c-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="8964c-131">`EndConnection` viene chiamato per ultimo per rimuovere l'associazione tra l'elenco di attività e identificatore o nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="8964c-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8964c-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8964c-132">Requirements</span></span>  
 <span data-ttu-id="8964c-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8964c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8964c-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8964c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8964c-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8964c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8964c-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8964c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8964c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8964c-137">See also</span></span>

- [<span data-ttu-id="8964c-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8964c-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8964c-139">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="8964c-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="8964c-140">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="8964c-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="8964c-141">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="8964c-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="8964c-142">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="8964c-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
