---
title: Metodo IHostTask::SetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9ecdeb4df6210805490586f1818298025fc036
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749945"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="71b5b-102">Metodo IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="71b5b-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="71b5b-103">Il livello di richiede che l'host di modificare la priorità del thread per l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="71b5b-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71b5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71b5b-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="71b5b-106">[in] Intero che rappresenta il valore di priorità di thread richiesti per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="71b5b-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71b5b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71b5b-107">Return Value</span></span>  
  
|<span data-ttu-id="71b5b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71b5b-108">HRESULT</span></span>|<span data-ttu-id="71b5b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71b5b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71b5b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71b5b-110">S_OK</span></span>|<span data-ttu-id="71b5b-111">`SetPriority` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="71b5b-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="71b5b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71b5b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71b5b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71b5b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71b5b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71b5b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71b5b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71b5b-115">The call timed out.</span></span>|  
|<span data-ttu-id="71b5b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71b5b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71b5b-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="71b5b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71b5b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71b5b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71b5b-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="71b5b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71b5b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71b5b-120">E_FAIL</span></span>|<span data-ttu-id="71b5b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="71b5b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71b5b-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="71b5b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71b5b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71b5b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71b5b-124">Note</span><span class="sxs-lookup"><span data-stu-id="71b5b-124">Remarks</span></span>  
 <span data-ttu-id="71b5b-125">Thread vengono concesse tempo di elaborazione utilizzando un sistema con distribuzione round robin in parte basato sul livello di priorità del thread.</span><span class="sxs-lookup"><span data-stu-id="71b5b-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="71b5b-126">`SetPriority` consente a CLR impostare tale livello di priorità di thread per l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="71b5b-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="71b5b-127">Nell'esempio `newPriority` sono supportati i valori.</span><span class="sxs-lookup"><span data-stu-id="71b5b-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="71b5b-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="71b5b-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="71b5b-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="71b5b-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="71b5b-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="71b5b-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="71b5b-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="71b5b-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="71b5b-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="71b5b-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="71b5b-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="71b5b-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="71b5b-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="71b5b-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="71b5b-135">CLR chiama `SetPriority` quando il valore della <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> viene modificato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="71b5b-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="71b5b-136">Un host può definire i propri algoritmi per l'assegnazione di priorità di thread e può ignorare questa richiesta.</span><span class="sxs-lookup"><span data-stu-id="71b5b-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71b5b-137">`SetPriority` non segnala se il livello di priorità di thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="71b5b-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="71b5b-138">Chiamare [GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) per determinare il valore del livello di priorità di thread dell'attività.</span><span class="sxs-lookup"><span data-stu-id="71b5b-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="71b5b-139">I valori del livello di priorità del thread vengono definiti da Win32 `SetThreadPriority` (funzione).</span><span class="sxs-lookup"><span data-stu-id="71b5b-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="71b5b-140">Per altre informazioni sulla priorità dei thread, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="71b5b-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b5b-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71b5b-141">Requirements</span></span>  
 <span data-ttu-id="71b5b-142">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71b5b-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b5b-143">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71b5b-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71b5b-144">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="71b5b-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71b5b-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b5b-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b5b-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71b5b-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="71b5b-147">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="71b5b-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="71b5b-148">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="71b5b-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="71b5b-149">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="71b5b-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="71b5b-150">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="71b5b-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="71b5b-151">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="71b5b-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
