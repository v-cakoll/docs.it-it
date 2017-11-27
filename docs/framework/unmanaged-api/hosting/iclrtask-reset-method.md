---
title: Metodo ICLRTask::Reset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c50dc4770665e2b049f41a105b58231221b8e9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="7ef90-102">Metodo ICLRTask::Reset</span><span class="sxs-lookup"><span data-stu-id="7ef90-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="7ef90-103">Informa common language runtime (CLR), l'host ha completato un'attività che consente di Riutilizzare corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza per rappresentare un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="7ef90-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ef90-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ef90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ef90-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="7ef90-106">[in] `true`, se il runtime deve reimpostare tutti i valori statici relativi ai thread oltre alle informazioni di sicurezza e le impostazioni locali relative all'oggetto corrente `ICLRTask` dell'istanza; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7ef90-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="7ef90-107">Se il valore è `true`, il runtime Reimposta i dati archiviati utilizzando <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ef90-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ef90-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7ef90-108">Return Value</span></span>  
  
|<span data-ttu-id="7ef90-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ef90-109">HRESULT</span></span>|<span data-ttu-id="7ef90-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ef90-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ef90-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ef90-111">S_OK</span></span>|<span data-ttu-id="7ef90-112">`Reset`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7ef90-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="7ef90-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ef90-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ef90-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ef90-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="7ef90-115">correttamente</span><span class="sxs-lookup"><span data-stu-id="7ef90-115">successfully</span></span>|  
|<span data-ttu-id="7ef90-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ef90-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ef90-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ef90-117">The call timed out.</span></span>|  
|<span data-ttu-id="7ef90-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ef90-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ef90-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7ef90-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ef90-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ef90-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ef90-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7ef90-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ef90-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ef90-122">E_FAIL</span></span>|<span data-ttu-id="7ef90-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7ef90-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ef90-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7ef90-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ef90-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7ef90-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ef90-126">Note</span><span class="sxs-lookup"><span data-stu-id="7ef90-126">Remarks</span></span>  
 <span data-ttu-id="7ef90-127">CLR possono essere riciclati creato in precedenza `ICLRTask` istanze per evitare il sovraccarico di più volte la creazione di nuove istanze ogni volta che è necessaria una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="7ef90-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="7ef90-128">L'host abilita questa funzionalità chiamando `ICLRTask::Reset` anziché [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) quando un'attività è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7ef90-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="7ef90-129">L'elenco seguente riepiloga il normale ciclo di vita di un `ICLRTask` istanza:</span><span class="sxs-lookup"><span data-stu-id="7ef90-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="7ef90-130">Il runtime crea un nuovo `ICLRTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="7ef90-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="7ef90-131">Il runtime chiama [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) per ottenere un riferimento all'attività corrente di host.</span><span class="sxs-lookup"><span data-stu-id="7ef90-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="7ef90-132">Il runtime chiama [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) per associare la nuova istanza di attività dell'host.</span><span class="sxs-lookup"><span data-stu-id="7ef90-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="7ef90-133">L'attività viene eseguita e completata.</span><span class="sxs-lookup"><span data-stu-id="7ef90-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="7ef90-134">L'host elimina l'attività mediante una chiamata `ICLRTask::ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="7ef90-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="7ef90-135">`Reset`modifica di questo scenario in due modi.</span><span class="sxs-lookup"><span data-stu-id="7ef90-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="7ef90-136">Nel passaggio 5, l'host chiama `Reset` per reimpostare l'attività lo stato originario, quindi separa il `ICLRTask` istanza da associato [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="7ef90-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="7ef90-137">Se si desidera, l'host può inoltre memorizzare nella cache il `IHostTask` istanza per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="7ef90-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="7ef90-138">Nel passaggio 1, il ricicla `ICLRTask` dalla cache anziché creare una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="7ef90-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="7ef90-139">Questo approccio funziona bene quando l'host dispone anche di un pool di attività di lavoro riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="7ef90-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="7ef90-140">Quando l'host elimina uno dei relativi `IHostTask` istanze, vengono eliminati definitivamente corrispondente `ICLRTask` chiamando `ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="7ef90-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef90-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ef90-141">Requirements</span></span>  
 <span data-ttu-id="7ef90-142">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef90-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef90-143">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7ef90-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ef90-144">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ef90-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ef90-145">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef90-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef90-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef90-146">See Also</span></span>  
 [<span data-ttu-id="7ef90-147">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7ef90-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7ef90-148">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7ef90-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7ef90-149">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7ef90-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7ef90-150">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7ef90-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
