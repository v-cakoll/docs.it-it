---
title: Metodo ICLRTask::SetTaskIdentifier
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SetTaskIdentifier
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 916f4638ad8206352f3b5973bb6c8b5dab39cda4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="409e0-102">Metodo ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="409e0-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="409e0-103">Indica a common language runtime (CLR) per associare il valore dell'identificatore specificato con l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="409e0-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="409e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="409e0-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="409e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="409e0-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="409e0-106">[in] Identificatore univoco per common language runtime associare l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="409e0-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="409e0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="409e0-107">Return Value</span></span>  
  
|<span data-ttu-id="409e0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="409e0-108">HRESULT</span></span>|<span data-ttu-id="409e0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="409e0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="409e0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="409e0-110">S_OK</span></span>|<span data-ttu-id="409e0-111">`SetTaskIdentifier`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="409e0-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="409e0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="409e0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="409e0-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="409e0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="409e0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="409e0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="409e0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="409e0-115">The call timed out.</span></span>|  
|<span data-ttu-id="409e0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="409e0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="409e0-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="409e0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="409e0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="409e0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="409e0-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="409e0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="409e0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="409e0-120">E_FAIL</span></span>|<span data-ttu-id="409e0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="409e0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="409e0-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="409e0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="409e0-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="409e0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="409e0-124">Note</span><span class="sxs-lookup"><span data-stu-id="409e0-124">Remarks</span></span>  
 <span data-ttu-id="409e0-125">L'host è possibile associare un'attività per consentire l'integrazione CLR e l'host in un ambiente di debug di un identificatore.</span><span class="sxs-lookup"><span data-stu-id="409e0-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="409e0-126">L'identificatore non ha significato per CLR.</span><span class="sxs-lookup"><span data-stu-id="409e0-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="409e0-127">CLR passa insieme a un'applicazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="409e0-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="409e0-128">Il debugger può utilizzare questo identificatore per associare uno stack di chiamate CLR a uno stack di chiamate di host e abilitare le rispettive informazioni di analisi unificazione quando viene visualizzato nell'interfaccia utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="409e0-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="409e0-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="409e0-129">Requirements</span></span>  
 <span data-ttu-id="409e0-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="409e0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="409e0-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="409e0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="409e0-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="409e0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="409e0-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="409e0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="409e0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="409e0-134">See Also</span></span>  
 [<span data-ttu-id="409e0-135">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="409e0-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="409e0-136">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="409e0-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="409e0-137">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="409e0-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="409e0-138">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="409e0-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
