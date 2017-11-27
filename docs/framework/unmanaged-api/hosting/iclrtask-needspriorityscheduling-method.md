---
title: Metodo ICLRTask::NeedsPriorityScheduling
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.NeedsPriorityScheduling
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 46da785535bef3443a1b917a5fb997e8e6ef3fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="562c0-102">Metodo ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="562c0-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="562c0-103">Ottiene un valore che indica se l'attività corrente, che si sta per essere disattivato, deve essere contrassegnato come una priorità per la ripianificazione.</span><span class="sxs-lookup"><span data-stu-id="562c0-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="562c0-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="562c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="562c0-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="562c0-106">[out] `true`, se l'host deve tentare di ripianificare l'attività corrente appena possibile; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="562c0-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="562c0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="562c0-107">Return Value</span></span>  
  
|<span data-ttu-id="562c0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="562c0-108">HRESULT</span></span>|<span data-ttu-id="562c0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="562c0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="562c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="562c0-110">S_OK</span></span>|<span data-ttu-id="562c0-111">`NeedsPriorityRescheduling`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="562c0-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="562c0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="562c0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="562c0-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="562c0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="562c0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="562c0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="562c0-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="562c0-115">The call timed out.</span></span>|  
|<span data-ttu-id="562c0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="562c0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="562c0-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="562c0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="562c0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="562c0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="562c0-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="562c0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="562c0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="562c0-120">E_FAIL</span></span>|<span data-ttu-id="562c0-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="562c0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="562c0-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="562c0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="562c0-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="562c0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="562c0-124">Note</span><span class="sxs-lookup"><span data-stu-id="562c0-124">Remarks</span></span>  
 <span data-ttu-id="562c0-125">In situazioni in cui l'attività sta per essere raccolta dal garbage collector, Common Language Runtime imposta il valore di `pbNeedsPriorityScheduling` a `true`, che indica la ripianificazione con priorità alta.</span><span class="sxs-lookup"><span data-stu-id="562c0-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="562c0-126">Questo consente all'host ripianificare l'attività rapidamente, in modo da ridurre al minimo il rischio di ritardi nell'operazione di garbage collection e che consente all'host e il runtime di risparmio di risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="562c0-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="562c0-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="562c0-127">Requirements</span></span>  
 <span data-ttu-id="562c0-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="562c0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="562c0-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="562c0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="562c0-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="562c0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="562c0-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="562c0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562c0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="562c0-132">See Also</span></span>  
 [<span data-ttu-id="562c0-133">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="562c0-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="562c0-134">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="562c0-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="562c0-135">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="562c0-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="562c0-136">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="562c0-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
