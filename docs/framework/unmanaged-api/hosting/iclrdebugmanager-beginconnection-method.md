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
ms.openlocfilehash: 98e4efe149cab1b822c9993e4df28806f773c61d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504251"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="59608-102">Metodo ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="59608-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="59608-103">Stabilisce una nuova connessione tra l'host e il debugger per associare un elenco di attività con un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="59608-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59608-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59608-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59608-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59608-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="59608-106">in Identificatore da associare all'elenco di attività di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="59608-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="59608-107">in Nome descrittivo da associare all'elenco delle attività CLR.</span><span class="sxs-lookup"><span data-stu-id="59608-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59608-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59608-108">Return Value</span></span>  
  
|<span data-ttu-id="59608-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59608-109">HRESULT</span></span>|<span data-ttu-id="59608-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59608-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59608-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="59608-111">S_OK</span></span>|<span data-ttu-id="59608-112">`BeginConnection`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="59608-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="59608-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59608-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59608-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="59608-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="59608-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59608-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59608-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="59608-116">The call timed out.</span></span>|  
|<span data-ttu-id="59608-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59608-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59608-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="59608-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59608-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59608-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59608-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="59608-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59608-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59608-121">E_FAIL</span></span>|<span data-ttu-id="59608-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="59608-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59608-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="59608-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59608-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="59608-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="59608-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="59608-125">E_INVALIDARG</span></span>|<span data-ttu-id="59608-126">`dwConnectionId`è zero oppure `BeginConnection` è già stato chiamato usando questo `dwConnectionId` valore o `szConnectionName` è null.</span><span class="sxs-lookup"><span data-stu-id="59608-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="59608-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="59608-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="59608-128">Impossibile allocare memoria sufficiente per contenere l'elenco delle attività associate a questa connessione.</span><span class="sxs-lookup"><span data-stu-id="59608-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59608-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="59608-129">Remarks</span></span>  
 <span data-ttu-id="59608-130">[ICLRDebugManager](iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)e [EndConnection](iclrdebugmanager-endconnection-method.md), per associare elenchi di attività con identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="59608-130">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="59608-131">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="59608-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="59608-132">`BeginConnection`viene chiamato per primo per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="59608-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="59608-133">`SetConnectionTasks`viene chiamato Next per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="59608-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="59608-134">`EndConnection`viene chiamato per ultimo per rimuovere l'associazione tra l'elenco attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate per connessioni diverse possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="59608-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59608-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59608-135">Requirements</span></span>  
 <span data-ttu-id="59608-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59608-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59608-137">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="59608-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59608-138">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="59608-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59608-139">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59608-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59608-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59608-140">See also</span></span>

- [<span data-ttu-id="59608-141">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="59608-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="59608-142">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="59608-142">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="59608-143">Metodo EndConnection</span><span class="sxs-lookup"><span data-stu-id="59608-143">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="59608-144">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="59608-144">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="59608-145">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="59608-145">IHostControl Interface</span></span>](ihostcontrol-interface.md)
