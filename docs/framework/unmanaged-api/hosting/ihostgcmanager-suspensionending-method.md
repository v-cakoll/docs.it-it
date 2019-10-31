---
title: Metodo IHostGCManager::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
ms.openlocfilehash: 6ef04799c0062c40f1671cbe6d897a148e1b93bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130477"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="dc0e2-102">Metodo IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="dc0e2-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="dc0e2-103">Notifica all'host che la Common Language Runtime (CLR) sta riprendendo l'esecuzione delle attività nei thread che sono stati sospesi per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc0e2-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc0e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc0e2-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="dc0e2-106">in La generazione del Garbage Collection appena terminata, da cui il thread riprende.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc0e2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dc0e2-107">Return Value</span></span>  
  
|<span data-ttu-id="dc0e2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc0e2-108">HRESULT</span></span>|<span data-ttu-id="dc0e2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc0e2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc0e2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc0e2-110">S_OK</span></span>|<span data-ttu-id="dc0e2-111">`SuspensionEnding` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="dc0e2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc0e2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc0e2-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc0e2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc0e2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc0e2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-115">The call timed out.</span></span>|  
|<span data-ttu-id="dc0e2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc0e2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc0e2-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc0e2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc0e2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc0e2-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc0e2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc0e2-120">E_FAIL</span></span>|<span data-ttu-id="dc0e2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc0e2-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc0e2-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc0e2-124">Note</span><span class="sxs-lookup"><span data-stu-id="dc0e2-124">Remarks</span></span>  
 <span data-ttu-id="dc0e2-125">CLR chiama `SuspensionEnding` dopo aver eseguito un Garbage Collection per informare l'host che il thread sta riprendendo l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dc0e2-126">Non ripianificare il thread da cui è stata effettuata la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="dc0e2-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0e2-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc0e2-127">Requirements</span></span>  
 <span data-ttu-id="dc0e2-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc0e2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc0e2-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc0e2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc0e2-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc0e2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc0e2-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc0e2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0e2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc0e2-132">See also</span></span>

- [<span data-ttu-id="dc0e2-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dc0e2-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dc0e2-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dc0e2-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dc0e2-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="dc0e2-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dc0e2-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dc0e2-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="dc0e2-137">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="dc0e2-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
