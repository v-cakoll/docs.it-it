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
ms.openlocfilehash: 6a6383761b878c7e916064f9a046641d00a1c6ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734267"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="98849-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="98849-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="98849-103">Ottiene informazioni sull'utilizzo di memoria statistiche correlate all'attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza rappresenta.</span><span class="sxs-lookup"><span data-stu-id="98849-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98849-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98849-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98849-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98849-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="98849-106">[out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) istanza che contiene i dettagli relativi all'utilizzo di memoria dell'attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="98849-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98849-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98849-107">Return Value</span></span>  
  
|<span data-ttu-id="98849-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98849-108">HRESULT</span></span>|<span data-ttu-id="98849-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98849-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98849-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="98849-110">S_OK</span></span>|<span data-ttu-id="98849-111">`GetMemStats` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="98849-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="98849-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98849-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98849-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="98849-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98849-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98849-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98849-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="98849-115">The call timed out.</span></span>|  
|<span data-ttu-id="98849-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98849-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98849-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="98849-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98849-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98849-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98849-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="98849-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98849-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98849-120">E_FAIL</span></span>|<span data-ttu-id="98849-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="98849-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98849-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="98849-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98849-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="98849-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98849-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98849-124">Requirements</span></span>  
 <span data-ttu-id="98849-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98849-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98849-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98849-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98849-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="98849-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98849-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98849-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98849-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98849-129">See also</span></span>
- [<span data-ttu-id="98849-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="98849-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="98849-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="98849-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="98849-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="98849-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="98849-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="98849-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
