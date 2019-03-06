---
title: Metodo ICLRTask::GetMemStats
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86aa020b2fac6d1405d8f24488184f3f7dd618a1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471563"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="52d8d-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="52d8d-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="52d8d-103">Ottiene informazioni sull'utilizzo di memoria statistiche correlate all'attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza rappresenta.</span><span class="sxs-lookup"><span data-stu-id="52d8d-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52d8d-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52d8d-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="52d8d-106">[out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) istanza che contiene i dettagli relativi all'utilizzo di memoria dell'attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="52d8d-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52d8d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52d8d-107">Return Value</span></span>  
  
|<span data-ttu-id="52d8d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52d8d-108">HRESULT</span></span>|<span data-ttu-id="52d8d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52d8d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52d8d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52d8d-110">S_OK</span></span>|<span data-ttu-id="52d8d-111">`GetMemStats` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="52d8d-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="52d8d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52d8d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52d8d-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="52d8d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52d8d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52d8d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52d8d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="52d8d-115">The call timed out.</span></span>|  
|<span data-ttu-id="52d8d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52d8d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52d8d-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="52d8d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52d8d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52d8d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52d8d-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="52d8d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52d8d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52d8d-120">E_FAIL</span></span>|<span data-ttu-id="52d8d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="52d8d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52d8d-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="52d8d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52d8d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52d8d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52d8d-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52d8d-124">Requirements</span></span>  
 <span data-ttu-id="52d8d-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d8d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d8d-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52d8d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52d8d-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="52d8d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52d8d-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d8d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d8d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52d8d-129">See also</span></span>
- [<span data-ttu-id="52d8d-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="52d8d-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="52d8d-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="52d8d-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="52d8d-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="52d8d-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="52d8d-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="52d8d-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
