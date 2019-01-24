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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2a26e32040f705fd46f9d9d8909fd47e963baa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510781"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="8205d-102">Metodo ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="8205d-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="8205d-103">Ottiene un valore che indica se l'attività corrente, che viene viene disattivato, deve essere contrassegnato come una priorità assoluta per la ripianificazione.</span><span class="sxs-lookup"><span data-stu-id="8205d-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8205d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8205d-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8205d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8205d-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="8205d-106">[out] `true`, se l'host deve tentare di modificare la pianificazione l'istanza corrente dell'attività appena possibile; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8205d-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8205d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8205d-107">Return Value</span></span>  
  
|<span data-ttu-id="8205d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8205d-108">HRESULT</span></span>|<span data-ttu-id="8205d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8205d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8205d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8205d-110">S_OK</span></span>|<span data-ttu-id="8205d-111">`NeedsPriorityRescheduling` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8205d-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="8205d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8205d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8205d-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8205d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8205d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8205d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8205d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8205d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8205d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8205d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8205d-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8205d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8205d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8205d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8205d-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8205d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8205d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8205d-120">E_FAIL</span></span>|<span data-ttu-id="8205d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8205d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8205d-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8205d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8205d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8205d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8205d-124">Note</span><span class="sxs-lookup"><span data-stu-id="8205d-124">Remarks</span></span>  
 <span data-ttu-id="8205d-125">In situazioni in cui l'attività è vicino raccolto dal garbage collector di Common Language Runtime imposta il valore della `pbNeedsPriorityScheduling` a `true`, che indica la ripianificazione con priorità alta.</span><span class="sxs-lookup"><span data-stu-id="8205d-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="8205d-126">Ciò consente all'host ripianificare l'attività rapidamente, in modo da ridurre al minimo il rischio di ritardi nell'operazione di garbage collection e consentono a host e il runtime di risparmio di risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="8205d-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8205d-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8205d-127">Requirements</span></span>  
 <span data-ttu-id="8205d-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8205d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8205d-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8205d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8205d-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8205d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8205d-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8205d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8205d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8205d-132">See also</span></span>
- [<span data-ttu-id="8205d-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8205d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8205d-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8205d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8205d-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8205d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8205d-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8205d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
