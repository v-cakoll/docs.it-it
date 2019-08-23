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
ms.openlocfilehash: d2af6970907eb9895750ca58065b2e0cb735cea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969400"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="2c1de-102">Metodo ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="2c1de-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="2c1de-103">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="2c1de-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c1de-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c1de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c1de-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="2c1de-106">in Identificatore specifico dell'host per la connessione e l'elenco associato di attività di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2c1de-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c1de-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c1de-107">Return Value</span></span>  
  
|<span data-ttu-id="2c1de-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c1de-108">HRESULT</span></span>|<span data-ttu-id="2c1de-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c1de-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c1de-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c1de-110">S_OK</span></span>|<span data-ttu-id="2c1de-111">`EndConnection`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2c1de-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="2c1de-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c1de-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c1de-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2c1de-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c1de-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c1de-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c1de-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c1de-115">The call timed out.</span></span>|  
|<span data-ttu-id="2c1de-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c1de-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c1de-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2c1de-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c1de-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c1de-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c1de-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2c1de-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c1de-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c1de-120">E_FAIL</span></span>|<span data-ttu-id="2c1de-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2c1de-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c1de-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2c1de-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c1de-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c1de-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c1de-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2c1de-124">E_INVALIDARG</span></span>|<span data-ttu-id="2c1de-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) non è mai stato `dwConnectionId`chiamato con `dwConnectionId` o è zero.</span><span class="sxs-lookup"><span data-stu-id="2c1de-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1de-126">Note</span><span class="sxs-lookup"><span data-stu-id="2c1de-126">Remarks</span></span>  
 <span data-ttu-id="2c1de-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)e `EndConnection`, per l'associazione di elenchi di attività con identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="2c1de-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2c1de-128">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="2c1de-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="2c1de-129">`BeginConnection`viene chiamato per primo per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="2c1de-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="2c1de-130">`SetConnectionTasks`viene chiamato Next per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="2c1de-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="2c1de-131">`EndConnection`viene chiamato per ultimo per rimuovere l'associazione tra l'elenco attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate per connessioni diverse possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="2c1de-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1de-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c1de-132">Requirements</span></span>  
 <span data-ttu-id="2c1de-133">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c1de-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1de-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2c1de-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c1de-135">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c1de-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c1de-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1de-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1de-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c1de-137">See also</span></span>

- [<span data-ttu-id="2c1de-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2c1de-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2c1de-139">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="2c1de-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="2c1de-140">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="2c1de-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="2c1de-141">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="2c1de-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="2c1de-142">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="2c1de-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
