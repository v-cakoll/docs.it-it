---
title: Metodo IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177995"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="c587c-102">Metodo IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="c587c-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="c587c-103">Richiede che l'host crei una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="c587c-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c587c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c587c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c587c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c587c-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="c587c-106">[in] Dimensione richiesta, in byte, dello stack richiesto o 0 (zero) per la dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c587c-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="c587c-107">[in] Puntatore alla funzione che l'attività deve essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="c587c-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="c587c-108">[in] Puntatore ai dati utente da passare alla funzione oppure null se la funzione non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="c587c-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="c587c-109">[fuori] Puntatore all'indirizzo di un'istanza [di IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) creata dall'host oppure null se non è possibile creare l'attività.</span><span class="sxs-lookup"><span data-stu-id="c587c-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="c587c-110">L'attività rimane in uno stato sospeso finché non viene avviata in modo esplicito da una chiamata a [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="c587c-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c587c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c587c-111">Return Value</span></span>  
  
|<span data-ttu-id="c587c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c587c-112">HRESULT</span></span>|<span data-ttu-id="c587c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c587c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c587c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c587c-114">S_OK</span></span>|<span data-ttu-id="c587c-115">`CreateTask`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="c587c-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="c587c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c587c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c587c-117">Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c587c-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c587c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c587c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c587c-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c587c-119">The call timed out.</span></span>|  
|<span data-ttu-id="c587c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c587c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c587c-121">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c587c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c587c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c587c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c587c-123">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c587c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c587c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c587c-124">E_FAIL</span></span>|<span data-ttu-id="c587c-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c587c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c587c-126">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c587c-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c587c-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c587c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c587c-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c587c-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c587c-129">Memoria insufficiente per creare l'attività richiesta.</span><span class="sxs-lookup"><span data-stu-id="c587c-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c587c-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c587c-130">Remarks</span></span>  
 <span data-ttu-id="c587c-131">CLR chiama `CreateTask` per richiedere che l'host crei una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="c587c-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="c587c-132">L'host restituisce un `IHostTask` puntatore a interfaccia a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="c587c-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="c587c-133">L'attività restituita deve rimanere sospesa fino `IHostTask::Start`a quando non viene avviata in modo esplicito da una chiamata a .</span><span class="sxs-lookup"><span data-stu-id="c587c-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c587c-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c587c-134">Requirements</span></span>  
 <span data-ttu-id="c587c-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c587c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c587c-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c587c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c587c-137">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c587c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c587c-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c587c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c587c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c587c-139">See also</span></span>

- [<span data-ttu-id="c587c-140">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c587c-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c587c-141">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c587c-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c587c-142">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c587c-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c587c-143">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c587c-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
