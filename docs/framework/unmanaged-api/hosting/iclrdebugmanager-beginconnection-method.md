---
title: Metodo ICLRDebugManager::BeginConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133991"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="16598-102">Metodo ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="16598-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="16598-103">Stabilisce una nuova connessione tra l'host e il debugger per associare un elenco di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="16598-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16598-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16598-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16598-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16598-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="16598-106">[in] Un identificatore per associare l'elenco attività di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="16598-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="16598-107">[in] Nome descrittivo per associare l'elenco di attività CLR.</span><span class="sxs-lookup"><span data-stu-id="16598-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16598-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="16598-108">Return Value</span></span>  
  
|<span data-ttu-id="16598-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16598-109">HRESULT</span></span>|<span data-ttu-id="16598-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16598-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16598-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="16598-111">S_OK</span></span>|`BeginConnection` <span data-ttu-id="16598-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="16598-112">returned successfully.</span></span>|  
|<span data-ttu-id="16598-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16598-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16598-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="16598-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16598-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16598-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16598-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="16598-116">The call timed out.</span></span>|  
|<span data-ttu-id="16598-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16598-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16598-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="16598-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16598-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16598-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16598-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="16598-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16598-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16598-121">E_FAIL</span></span>|<span data-ttu-id="16598-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="16598-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16598-123">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="16598-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16598-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="16598-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16598-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="16598-125">E_INVALIDARG</span></span>|`dwConnectionId` <span data-ttu-id="16598-126">è uguale a zero, oppure `BeginConnection` è già stato chiamato usando questo `dwConnectionId` valore, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="16598-126">was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="16598-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="16598-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="16598-128">Impossibile allocare memoria non sufficiente per contenere l'elenco di attività associato a questa connessione.</span><span class="sxs-lookup"><span data-stu-id="16598-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16598-129">Note</span><span class="sxs-lookup"><span data-stu-id="16598-129">Remarks</span></span>  
 <span data-ttu-id="16598-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), e [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="16598-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16598-131">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="16598-131">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="16598-132">viene chiamato prima di tutto per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="16598-132">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="16598-133">viene chiamato per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="16598-133">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="16598-134">viene chiamato per ultimo per rimuovere l'associazione tra l'elenco di attività e identificatore o nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="16598-134">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16598-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16598-135">Requirements</span></span>  
 <span data-ttu-id="16598-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16598-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16598-137">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16598-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16598-138">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="16598-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="16598-139">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="16598-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16598-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16598-140">See also</span></span>

- [<span data-ttu-id="16598-141">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="16598-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="16598-142">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="16598-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="16598-143">Metodo EndConnection</span><span class="sxs-lookup"><span data-stu-id="16598-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="16598-144">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="16598-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="16598-145">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="16598-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
