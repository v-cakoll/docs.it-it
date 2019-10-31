---
title: Metodo IHostTaskManager::EndThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: c40febb78c1bc78a5a724f559eb95869e90bdad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133080"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="f52f8-102">Metodo IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f52f8-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="f52f8-103">Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere spostata in un altro thread del sistema operativo, in seguito a una precedente chiamata a [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="f52f8-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f52f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f52f8-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f52f8-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f52f8-105">Return Value</span></span>  
  
|<span data-ttu-id="f52f8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f52f8-106">HRESULT</span></span>|<span data-ttu-id="f52f8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f52f8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f52f8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f52f8-108">S_OK</span></span>|<span data-ttu-id="f52f8-109">`EndThreadAffinity` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f52f8-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="f52f8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f52f8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f52f8-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f52f8-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f52f8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f52f8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f52f8-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f52f8-113">The call timed out.</span></span>|  
|<span data-ttu-id="f52f8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f52f8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f52f8-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f52f8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f52f8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f52f8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f52f8-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f52f8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f52f8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f52f8-118">E_FAIL</span></span>|<span data-ttu-id="f52f8-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f52f8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f52f8-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f52f8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f52f8-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f52f8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f52f8-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f52f8-122">E_UNEXPECTED</span></span>|<span data-ttu-id="f52f8-123">`EndThreadAffinity` stata chiamata senza una precedente chiamata corrispondente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="f52f8-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f52f8-124">Note</span><span class="sxs-lookup"><span data-stu-id="f52f8-124">Remarks</span></span>  
 <span data-ttu-id="f52f8-125">CLR esegue una chiamata corrispondente a `BeginThreadAffinity` sull'attività corrente prima di chiamare `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="f52f8-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="f52f8-126">In assenza di una chiamata corrispondente, l'implementazione dell'host di [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED e non eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f52f8-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f52f8-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f52f8-127">Requirements</span></span>  
 <span data-ttu-id="f52f8-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f52f8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f52f8-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f52f8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f52f8-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f52f8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f52f8-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f52f8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52f8-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f52f8-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="f52f8-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f52f8-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f52f8-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f52f8-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f52f8-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f52f8-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f52f8-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f52f8-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
