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
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139698"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="0a9bb-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="0a9bb-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="0a9bb-103">Ottiene informazioni statistiche sull'utilizzo della memoria correlate all'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0a9bb-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a9bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a9bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a9bb-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="0a9bb-106">out Puntatore a un'istanza di [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) che contiene i dettagli sull'utilizzo della memoria dell'attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a9bb-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a9bb-107">Return Value</span></span>  
  
|<span data-ttu-id="0a9bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a9bb-108">HRESULT</span></span>|<span data-ttu-id="0a9bb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a9bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a9bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a9bb-110">S_OK</span></span>|<span data-ttu-id="0a9bb-111">`GetMemStats` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="0a9bb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a9bb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a9bb-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a9bb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a9bb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a9bb-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-115">The call timed out.</span></span>|  
|<span data-ttu-id="0a9bb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a9bb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a9bb-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a9bb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a9bb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a9bb-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a9bb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a9bb-120">E_FAIL</span></span>|<span data-ttu-id="0a9bb-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a9bb-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a9bb-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a9bb-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a9bb-124">Requirements</span></span>  
 <span data-ttu-id="0a9bb-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a9bb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a9bb-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0a9bb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a9bb-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0a9bb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a9bb-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a9bb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9bb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a9bb-129">See also</span></span>

- [<span data-ttu-id="0a9bb-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0a9bb-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0a9bb-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0a9bb-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0a9bb-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="0a9bb-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0a9bb-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0a9bb-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
