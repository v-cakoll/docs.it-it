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
ms.openlocfilehash: ab388459df88e91093459658ced4d4b4eb023460
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758982"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="0a4d1-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="0a4d1-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="0a4d1-103">Ottiene informazioni sull'utilizzo di memoria statistiche correlate all'attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza rappresenta.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a4d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a4d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a4d1-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="0a4d1-106">[out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) istanza che contiene i dettagli relativi all'utilizzo di memoria dell'attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a4d1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a4d1-107">Return Value</span></span>  
  
|<span data-ttu-id="0a4d1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a4d1-108">HRESULT</span></span>|<span data-ttu-id="0a4d1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a4d1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a4d1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a4d1-110">S_OK</span></span>|<span data-ttu-id="0a4d1-111">`GetMemStats` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="0a4d1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a4d1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a4d1-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a4d1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a4d1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a4d1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-115">The call timed out.</span></span>|  
|<span data-ttu-id="0a4d1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a4d1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a4d1-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a4d1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a4d1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a4d1-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a4d1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a4d1-120">E_FAIL</span></span>|<span data-ttu-id="0a4d1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a4d1-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a4d1-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a4d1-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a4d1-124">Requirements</span></span>  
 <span data-ttu-id="0a4d1-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a4d1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4d1-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a4d1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a4d1-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0a4d1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a4d1-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4d1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4d1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a4d1-129">See also</span></span>

- [<span data-ttu-id="0a4d1-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0a4d1-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0a4d1-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0a4d1-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0a4d1-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="0a4d1-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0a4d1-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0a4d1-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
