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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cb539d5b10c8a027a8c73c68ccc04aa490cb4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443167"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="f8808-102">Metodo IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="f8808-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="f8808-103">Richieste che l'host crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="f8808-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8808-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8808-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8808-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8808-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="f8808-106">[in] La dimensione richiesta, in byte, dello stack richiesto oppure 0 (zero) per la dimensione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f8808-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="f8808-107">[in] Un puntatore alla funzione l'attività è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8808-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="f8808-108">[in] Un puntatore ai dati utente deve essere passato alla funzione, o null se la funzione non accetta parametri.</span><span class="sxs-lookup"><span data-stu-id="f8808-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="f8808-109">[out] Un puntatore all'indirizzo di un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza creata da host oppure null se non è possibile creare l'attività.</span><span class="sxs-lookup"><span data-stu-id="f8808-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="f8808-110">L'attività rimane in uno stato sospeso finché non viene avviata in modo esplicito da una chiamata a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="f8808-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8808-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8808-111">Return Value</span></span>  
  
|<span data-ttu-id="f8808-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8808-112">HRESULT</span></span>|<span data-ttu-id="f8808-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8808-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8808-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8808-114">S_OK</span></span>|<span data-ttu-id="f8808-115">`CreateTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8808-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="f8808-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8808-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8808-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8808-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8808-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8808-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8808-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8808-119">The call timed out.</span></span>|  
|<span data-ttu-id="f8808-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8808-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8808-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="f8808-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8808-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8808-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8808-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f8808-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8808-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8808-124">E_FAIL</span></span>|<span data-ttu-id="f8808-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f8808-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8808-126">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f8808-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8808-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f8808-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f8808-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f8808-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f8808-129">Memoria insufficiente è disponibile per creare l'attività richiesta.</span><span class="sxs-lookup"><span data-stu-id="f8808-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8808-130">Note</span><span class="sxs-lookup"><span data-stu-id="f8808-130">Remarks</span></span>  
 <span data-ttu-id="f8808-131">CLR chiama `CreateTask` per richiedere che l'host crea una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="f8808-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="f8808-132">L'host restituisce un puntatore a interfaccia a un `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="f8808-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="f8808-133">L'attività restituita deve rimanere sospesa fino a quando non viene avviata in modo esplicito da una chiamata a `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="f8808-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8808-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8808-134">Requirements</span></span>  
 <span data-ttu-id="f8808-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8808-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8808-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f8808-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8808-137">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f8808-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8808-138">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8808-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8808-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8808-139">See Also</span></span>  
 [<span data-ttu-id="f8808-140">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f8808-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f8808-141">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f8808-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f8808-142">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f8808-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f8808-143">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f8808-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
