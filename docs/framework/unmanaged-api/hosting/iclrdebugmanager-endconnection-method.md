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
ms.openlocfilehash: d3d081e389e29833f24063ba75289f3db8c5504a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504277"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="f0492-102">Metodo ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="f0492-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="f0492-103">Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="f0492-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0492-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0492-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0492-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0492-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="f0492-106">in Identificatore specifico dell'host per la connessione e l'elenco associato di attività di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f0492-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0492-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f0492-107">Return Value</span></span>  
  
|<span data-ttu-id="f0492-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0492-108">HRESULT</span></span>|<span data-ttu-id="f0492-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0492-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0492-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0492-110">S_OK</span></span>|<span data-ttu-id="f0492-111">`EndConnection`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f0492-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="f0492-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0492-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0492-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0492-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0492-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0492-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0492-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f0492-115">The call timed out.</span></span>|  
|<span data-ttu-id="f0492-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0492-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0492-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f0492-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0492-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0492-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0492-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f0492-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0492-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0492-120">E_FAIL</span></span>|<span data-ttu-id="f0492-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f0492-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0492-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f0492-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0492-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f0492-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f0492-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f0492-124">E_INVALIDARG</span></span>|<span data-ttu-id="f0492-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) non è mai stato chiamato con `dwConnectionId` o `dwConnectionId` è zero.</span><span class="sxs-lookup"><span data-stu-id="f0492-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0492-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f0492-126">Remarks</span></span>  
 <span data-ttu-id="f0492-127">[ICLRDebugManager](iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)e `EndConnection` , per l'associazione di elenchi di attività con identificatori e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="f0492-127">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f0492-128">Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività.</span><span class="sxs-lookup"><span data-stu-id="f0492-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="f0492-129">`BeginConnection`viene chiamato per primo per stabilire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="f0492-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="f0492-130">`SetConnectionTasks`viene chiamato Next per fornire il set di attività da associare a tale connessione.</span><span class="sxs-lookup"><span data-stu-id="f0492-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="f0492-131">`EndConnection`viene chiamato per ultimo per rimuovere l'associazione tra l'elenco attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate per connessioni diverse possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="f0492-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0492-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0492-132">Requirements</span></span>  
 <span data-ttu-id="f0492-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0492-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0492-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0492-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0492-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f0492-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0492-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0492-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0492-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0492-137">See also</span></span>

- [<span data-ttu-id="f0492-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f0492-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f0492-139">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="f0492-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="f0492-140">Metodo BeginConnection</span><span class="sxs-lookup"><span data-stu-id="f0492-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="f0492-141">Metodo SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="f0492-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="f0492-142">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="f0492-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
