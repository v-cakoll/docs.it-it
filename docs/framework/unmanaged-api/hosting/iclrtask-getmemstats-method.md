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
ms.openlocfilehash: 0d2975d6247cd9ecdb07b564d77518151404c7d0
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762461"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="d7631-102">Metodo ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="d7631-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="d7631-103">Ottiene informazioni statistiche sull'utilizzo della memoria correlate all'attività rappresentata dall'istanza corrente di [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d7631-103">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7631-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7631-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7631-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7631-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="d7631-106">out Puntatore a un'istanza di [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) contenente i dettagli sull'utilizzo della memoria dell'attività, incluso il numero di byte allocati.</span><span class="sxs-lookup"><span data-stu-id="d7631-106">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7631-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d7631-107">Return Value</span></span>  
  
|<span data-ttu-id="d7631-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7631-108">HRESULT</span></span>|<span data-ttu-id="d7631-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7631-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7631-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7631-110">S_OK</span></span>|<span data-ttu-id="d7631-111">`GetMemStats`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d7631-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="d7631-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7631-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7631-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d7631-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7631-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7631-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7631-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d7631-115">The call timed out.</span></span>|  
|<span data-ttu-id="d7631-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7631-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7631-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d7631-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7631-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7631-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7631-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d7631-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7631-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7631-120">E_FAIL</span></span>|<span data-ttu-id="d7631-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d7631-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7631-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d7631-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7631-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d7631-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7631-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7631-124">Requirements</span></span>  
 <span data-ttu-id="d7631-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7631-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7631-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d7631-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7631-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7631-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7631-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7631-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7631-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7631-129">See also</span></span>

- [<span data-ttu-id="d7631-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d7631-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="d7631-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d7631-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="d7631-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="d7631-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="d7631-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d7631-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
