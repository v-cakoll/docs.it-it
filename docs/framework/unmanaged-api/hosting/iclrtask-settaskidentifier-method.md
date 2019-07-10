---
title: Metodo ICLRTask::SetTaskIdentifier
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fe678dbf47141c31fb0870f1364983bc2ad69fc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770416"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="6e09a-102">Metodo ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="6e09a-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="6e09a-103">Indica a common language runtime (CLR) per associare il valore dell'identificatore specificato con l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="6e09a-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e09a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e09a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e09a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e09a-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="6e09a-106">[in] L'identificatore univoco per il common language runtime associare l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="6e09a-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e09a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6e09a-107">Return Value</span></span>  
  
|<span data-ttu-id="6e09a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e09a-108">HRESULT</span></span>|<span data-ttu-id="6e09a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e09a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e09a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e09a-110">S_OK</span></span>|<span data-ttu-id="6e09a-111">`SetTaskIdentifier` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6e09a-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="6e09a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6e09a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6e09a-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e09a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6e09a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6e09a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6e09a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e09a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6e09a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6e09a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6e09a-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6e09a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6e09a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6e09a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6e09a-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6e09a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6e09a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6e09a-120">E_FAIL</span></span>|<span data-ttu-id="6e09a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6e09a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6e09a-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6e09a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6e09a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6e09a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e09a-124">Note</span><span class="sxs-lookup"><span data-stu-id="6e09a-124">Remarks</span></span>  
 <span data-ttu-id="6e09a-125">L'host è possibile associare un'attività per semplificare l'integrazione CLR e l'host in un ambiente di debug di un identificatore.</span><span class="sxs-lookup"><span data-stu-id="6e09a-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="6e09a-126">L'identificatore non ha significato per CLR.</span><span class="sxs-lookup"><span data-stu-id="6e09a-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="6e09a-127">Common Language Runtime li passa a un'applicazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="6e09a-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="6e09a-128">Il debugger può usare questo identificatore per associare uno stack di chiamate CLR a uno stack di chiamate di host e abilitare le rispettive informazioni di analisi unificati quando viene visualizzato nell'interfaccia utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="6e09a-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e09a-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e09a-129">Requirements</span></span>  
 <span data-ttu-id="6e09a-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e09a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e09a-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e09a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e09a-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6e09a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e09a-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e09a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e09a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e09a-134">See also</span></span>

- [<span data-ttu-id="6e09a-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="6e09a-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6e09a-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6e09a-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6e09a-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6e09a-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6e09a-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6e09a-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
