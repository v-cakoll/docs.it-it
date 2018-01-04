---
title: Metodo ICLRTask::GetMemStats
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ad5fb2b76ef282258b9a5293b890a19420c1906
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="c8bda-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="c8bda-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="c8bda-103">Ottiene informazioni sull'utilizzo di memoria statistiche correlate all'attività che corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="c8bda-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8bda-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8bda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8bda-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="c8bda-106">[out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) istanza che contiene dettagli sull'utilizzo della memoria di attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="c8bda-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8bda-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8bda-107">Return Value</span></span>  
  
|<span data-ttu-id="c8bda-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8bda-108">HRESULT</span></span>|<span data-ttu-id="c8bda-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8bda-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8bda-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8bda-110">S_OK</span></span>|<span data-ttu-id="c8bda-111">`GetMemStats`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8bda-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="c8bda-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8bda-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8bda-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8bda-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8bda-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8bda-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8bda-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8bda-115">The call timed out.</span></span>|  
|<span data-ttu-id="c8bda-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8bda-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8bda-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="c8bda-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8bda-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8bda-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8bda-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c8bda-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8bda-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8bda-120">E_FAIL</span></span>|<span data-ttu-id="c8bda-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c8bda-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8bda-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c8bda-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8bda-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c8bda-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8bda-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8bda-124">Requirements</span></span>  
 <span data-ttu-id="c8bda-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8bda-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8bda-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c8bda-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8bda-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8bda-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8bda-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8bda-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bda-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8bda-129">See Also</span></span>  
 [<span data-ttu-id="c8bda-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c8bda-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c8bda-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c8bda-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c8bda-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c8bda-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c8bda-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c8bda-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
