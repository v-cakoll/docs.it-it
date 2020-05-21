---
title: Metodo ICLRTask::Reset
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762968"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="c628f-102">Metodo ICLRTask::Reset</span><span class="sxs-lookup"><span data-stu-id="c628f-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="c628f-103">Informa il Common Language Runtime (CLR) che l'host ha completato un'attività e consente a CLR di riutilizzare l'istanza di [ICLRTask](iclrtask-interface.md) corrente per rappresentare un'altra attività.</span><span class="sxs-lookup"><span data-stu-id="c628f-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c628f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c628f-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c628f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c628f-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="c628f-106">[in] `true` , se il runtime deve reimpostare tutti i valori statici correlati ai thread oltre alle informazioni sulla sicurezza e sulle impostazioni locali correlate all' `ICLRTask` istanza corrente; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="c628f-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="c628f-107">Se il valore è `true` , il Runtime reimposta i dati archiviati usando <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="c628f-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c628f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c628f-108">Return Value</span></span>  
  
|<span data-ttu-id="c628f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c628f-109">HRESULT</span></span>|<span data-ttu-id="c628f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c628f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c628f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c628f-111">S_OK</span></span>|<span data-ttu-id="c628f-112">`Reset`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c628f-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="c628f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c628f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c628f-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c628f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="c628f-115">correttamente</span><span class="sxs-lookup"><span data-stu-id="c628f-115">successfully</span></span>|  
|<span data-ttu-id="c628f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c628f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c628f-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c628f-117">The call timed out.</span></span>|  
|<span data-ttu-id="c628f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c628f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c628f-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c628f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c628f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c628f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c628f-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c628f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c628f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c628f-122">E_FAIL</span></span>|<span data-ttu-id="c628f-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c628f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c628f-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c628f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c628f-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c628f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c628f-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c628f-126">Remarks</span></span>  
 <span data-ttu-id="c628f-127">CLR può riciclare le istanze precedentemente create `ICLRTask` per evitare il sovraccarico dovuto alla creazione ripetuta di nuove istanze ogni volta che è necessaria una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="c628f-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="c628f-128">L'host abilita questa funzionalità chiamando `ICLRTask::Reset` anziché [ICLRTask:: ExitTask](iclrtask-exittask-method.md) al termine di un'attività.</span><span class="sxs-lookup"><span data-stu-id="c628f-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="c628f-129">Nell'elenco seguente viene riepilogato il normale ciclo di vita di un' `ICLRTask` istanza:</span><span class="sxs-lookup"><span data-stu-id="c628f-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="c628f-130">Il runtime crea una nuova `ICLRTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="c628f-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="c628f-131">Il runtime chiama [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) per ottenere un riferimento all'attività host corrente.</span><span class="sxs-lookup"><span data-stu-id="c628f-131">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="c628f-132">Il runtime chiama [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) per associare la nuova istanza all'attività host.</span><span class="sxs-lookup"><span data-stu-id="c628f-132">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="c628f-133">L'attività viene eseguita e completata.</span><span class="sxs-lookup"><span data-stu-id="c628f-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="c628f-134">L'host elimina l'attività chiamando `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="c628f-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="c628f-135">`Reset`modifica questo scenario in due modi.</span><span class="sxs-lookup"><span data-stu-id="c628f-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="c628f-136">Nel passaggio 5 precedente, l'host chiama `Reset` per reimpostare l'attività su uno stato pulito, quindi separa l' `ICLRTask` istanza dalla relativa istanza di [IHostTask](ihosttask-interface.md) associata.</span><span class="sxs-lookup"><span data-stu-id="c628f-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="c628f-137">Se lo si desidera, l'host può anche memorizzare nella cache l' `IHostTask` istanza per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="c628f-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="c628f-138">Nel passaggio 1, il runtime estrae un oggetto riciclato `ICLRTask` dalla cache anziché creare una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="c628f-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="c628f-139">Questo approccio funziona bene quando l'host dispone anche di un pool di attività di lavoro riutilizzabili.</span><span class="sxs-lookup"><span data-stu-id="c628f-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="c628f-140">Quando l'host elimina una delle `IHostTask` istanze, Elimina la corrispondente chiamando `ICLRTask` `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="c628f-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c628f-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c628f-141">Requirements</span></span>  
 <span data-ttu-id="c628f-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c628f-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c628f-143">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c628f-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c628f-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c628f-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c628f-145">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c628f-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c628f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c628f-146">See also</span></span>

- [<span data-ttu-id="c628f-147">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c628f-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c628f-148">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c628f-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c628f-149">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c628f-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c628f-150">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c628f-150">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
