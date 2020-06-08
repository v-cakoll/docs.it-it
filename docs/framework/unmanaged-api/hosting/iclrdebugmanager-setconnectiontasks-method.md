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
ms.openlocfilehash: f63b761497b3e9a19a9b939b45acf60d5a7d37b0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504238"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="086cb-102">Metodo ICLRDebugManager::SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="086cb-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="086cb-103">Associa un elenco di istanze di [ICLRTask](iclrtask-interface.md) a un identificatore e a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="086cb-103">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="086cb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="086cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="086cb-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="086cb-106">in Identificatore specifico dell'host per la connessione a cui associare la `ppCLRTask` matrice.</span><span class="sxs-lookup"><span data-stu-id="086cb-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="086cb-107">in Numero di membri di `ppCLRTask` .</span><span class="sxs-lookup"><span data-stu-id="086cb-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="086cb-108">Questo numero deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="086cb-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="086cb-109">in Matrice di `ICLRTask` puntatori da associare alla connessione identificata da `id` .</span><span class="sxs-lookup"><span data-stu-id="086cb-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="086cb-110">Questa matrice deve contenere almeno un membro.</span><span class="sxs-lookup"><span data-stu-id="086cb-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="086cb-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="086cb-111">Return Value</span></span>  
  
|<span data-ttu-id="086cb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="086cb-112">HRESULT</span></span>|<span data-ttu-id="086cb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="086cb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="086cb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="086cb-114">S_OK</span></span>|<span data-ttu-id="086cb-115">`SetConnectionTasks`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="086cb-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="086cb-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="086cb-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="086cb-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="086cb-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="086cb-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="086cb-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="086cb-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="086cb-119">The call timed out.</span></span>|  
|<span data-ttu-id="086cb-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="086cb-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="086cb-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="086cb-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="086cb-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="086cb-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="086cb-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="086cb-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="086cb-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="086cb-124">E_FAIL</span></span>|<span data-ttu-id="086cb-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="086cb-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="086cb-126">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="086cb-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="086cb-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="086cb-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="086cb-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="086cb-128">E_INVALIDARG</span></span>|<span data-ttu-id="086cb-129">[BeginConnection](iclrdebugmanager-beginconnection-method.md) non è stato chiamato utilizzando questo valore di `id` , oppure `dwCount` o `id` è zero oppure uno degli elementi di `ppCLRTask` è null.</span><span class="sxs-lookup"><span data-stu-id="086cb-129">[BeginConnection](iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="086cb-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="086cb-130">Remarks</span></span>  
 <span data-ttu-id="086cb-131">[ICLRDebugManager](iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection` , `SetConnectionTasks` e [EndConnection](iclrdebugmanager-endconnection-method.md), per l'associazione di elenchi di attività con identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="086cb-131">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="086cb-132">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="086cb-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="086cb-133">`BeginConnection`viene chiamato per primo per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="086cb-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="086cb-134">`SetConnectionTasks`viene chiamato Next per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="086cb-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="086cb-135">`EndConnection`viene chiamato per ultimo per rimuovere l'associazione tra l'elenco attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate per connessioni diverse possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="086cb-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="086cb-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="086cb-136">Requirements</span></span>  
 <span data-ttu-id="086cb-137">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="086cb-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="086cb-138">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="086cb-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="086cb-139">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="086cb-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="086cb-140">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086cb-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086cb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="086cb-141">See also</span></span>

- [<span data-ttu-id="086cb-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="086cb-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="086cb-143">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="086cb-143">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="086cb-144">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="086cb-144">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="086cb-145">Metodo EndConnection</span><span class="sxs-lookup"><span data-stu-id="086cb-145">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="086cb-146">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="086cb-146">IHostControl Interface</span></span>](ihostcontrol-interface.md)
