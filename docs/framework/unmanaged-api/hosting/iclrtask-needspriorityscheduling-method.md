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
ms.openlocfilehash: df20e98a9e88c10bac748a5acfc91adcb133da79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762992"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="dd419-102">Metodo ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="dd419-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="dd419-103">Ottiene un valore che indica se l'attività corrente, che viene disattivata, deve essere contrassegnata come priorità elevata per la ripianificazione.</span><span class="sxs-lookup"><span data-stu-id="dd419-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd419-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd419-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd419-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd419-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="dd419-106">[out] `true` , se l'host deve tentare di ripianificare l'istanza dell'attività corrente il prima possibile; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="dd419-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd419-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd419-107">Return Value</span></span>  
  
|<span data-ttu-id="dd419-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd419-108">HRESULT</span></span>|<span data-ttu-id="dd419-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd419-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd419-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd419-110">S_OK</span></span>|<span data-ttu-id="dd419-111">`NeedsPriorityRescheduling`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="dd419-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="dd419-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd419-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd419-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="dd419-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd419-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd419-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd419-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dd419-115">The call timed out.</span></span>|  
|<span data-ttu-id="dd419-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd419-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd419-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="dd419-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd419-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd419-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd419-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="dd419-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd419-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd419-120">E_FAIL</span></span>|<span data-ttu-id="dd419-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="dd419-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd419-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="dd419-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd419-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd419-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd419-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dd419-124">Remarks</span></span>  
 <span data-ttu-id="dd419-125">Nelle situazioni in cui l'attività è vicina a essere raccolta dal Garbage Collector, CLR imposta il valore di `pbNeedsPriorityScheduling` su `true` , che indica una ripianificazione ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="dd419-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="dd419-126">Questo consente all'host di ripianificare rapidamente l'attività, riducendo al minimo il rischio di ritardi nel Garbage Collection e consentendo all'host e al runtime di collaborare con la conservazione delle risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="dd419-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd419-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd419-127">Requirements</span></span>  
 <span data-ttu-id="dd419-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd419-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd419-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd419-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd419-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dd419-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd419-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd419-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd419-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd419-132">See also</span></span>

- [<span data-ttu-id="dd419-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dd419-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="dd419-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd419-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd419-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="dd419-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="dd419-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd419-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
