---
title: Metodo ICLRTask::NeedsPriorityScheduling
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
ms.openlocfilehash: 91c1ea51969447861ff6d0956c5714baa0054450
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124662"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="74d2a-102">Metodo ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="74d2a-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="74d2a-103">Ottiene un valore che indica se l'attività corrente, che viene disattivata, deve essere contrassegnata come priorità elevata per la ripianificazione.</span><span class="sxs-lookup"><span data-stu-id="74d2a-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74d2a-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74d2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74d2a-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="74d2a-106">[out] `true`, se l'host deve tentare di ripianificare l'istanza dell'attività corrente il prima possibile; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="74d2a-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74d2a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="74d2a-107">Return Value</span></span>  
  
|<span data-ttu-id="74d2a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74d2a-108">HRESULT</span></span>|<span data-ttu-id="74d2a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74d2a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74d2a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74d2a-110">S_OK</span></span>|<span data-ttu-id="74d2a-111">`NeedsPriorityRescheduling` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="74d2a-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="74d2a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74d2a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74d2a-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="74d2a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74d2a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74d2a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74d2a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="74d2a-115">The call timed out.</span></span>|  
|<span data-ttu-id="74d2a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74d2a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74d2a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="74d2a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74d2a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74d2a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74d2a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="74d2a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74d2a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74d2a-120">E_FAIL</span></span>|<span data-ttu-id="74d2a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="74d2a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74d2a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="74d2a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74d2a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="74d2a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74d2a-124">Note</span><span class="sxs-lookup"><span data-stu-id="74d2a-124">Remarks</span></span>  
 <span data-ttu-id="74d2a-125">Nelle situazioni in cui l'attività è vicina a essere raccolta dal Garbage Collector, CLR imposta il valore di `pbNeedsPriorityScheduling` su `true`, che indica una ripianificazione ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="74d2a-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="74d2a-126">Questo consente all'host di ripianificare rapidamente l'attività, riducendo al minimo il rischio di ritardi nel Garbage Collection e consentendo all'host e al runtime di collaborare con la conservazione delle risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="74d2a-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d2a-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74d2a-127">Requirements</span></span>  
 <span data-ttu-id="74d2a-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74d2a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74d2a-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="74d2a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74d2a-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="74d2a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74d2a-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74d2a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d2a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d2a-132">See also</span></span>

- [<span data-ttu-id="74d2a-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="74d2a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="74d2a-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="74d2a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="74d2a-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="74d2a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="74d2a-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="74d2a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
