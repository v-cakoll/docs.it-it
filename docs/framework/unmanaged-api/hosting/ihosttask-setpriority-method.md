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
ms.openlocfilehash: c64cee9ec9b62d87e0c4ae1aafaff59bb985ec95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121347"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="82110-102">Metodo IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="82110-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="82110-103">Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall'istanza corrente di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="82110-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82110-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82110-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82110-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82110-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="82110-106">in Integer che rappresenta il valore di priorità del thread richiesto per l'attività rappresentata dall'istanza di `IHostTask` corrente.</span><span class="sxs-lookup"><span data-stu-id="82110-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82110-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82110-107">Return Value</span></span>  
  
|<span data-ttu-id="82110-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82110-108">HRESULT</span></span>|<span data-ttu-id="82110-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82110-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82110-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="82110-110">S_OK</span></span>|<span data-ttu-id="82110-111">`SetPriority` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="82110-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="82110-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82110-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82110-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="82110-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82110-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82110-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82110-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="82110-115">The call timed out.</span></span>|  
|<span data-ttu-id="82110-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82110-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82110-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="82110-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82110-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82110-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82110-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="82110-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82110-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82110-120">E_FAIL</span></span>|<span data-ttu-id="82110-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="82110-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82110-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="82110-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82110-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82110-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82110-124">Note</span><span class="sxs-lookup"><span data-stu-id="82110-124">Remarks</span></span>  
 <span data-ttu-id="82110-125">Ai thread viene concesso il tempo di elaborazione utilizzando un sistema Round Robin che è parzialmente basato sul livello di priorità di un thread.</span><span class="sxs-lookup"><span data-stu-id="82110-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="82110-126">`SetPriority` consente a CLR di impostare il livello di priorità del thread per l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="82110-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="82110-127">Sono supportati i valori `newPriority` seguenti.</span><span class="sxs-lookup"><span data-stu-id="82110-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="82110-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="82110-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="82110-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="82110-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="82110-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="82110-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="82110-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="82110-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="82110-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="82110-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="82110-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="82110-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="82110-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="82110-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="82110-135">CLR chiama `SetPriority` quando il valore del <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> viene modificato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="82110-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="82110-136">Un host può definire i propri algoritmi per l'assegnazione della priorità del thread ed è libero di ignorare questa richiesta.</span><span class="sxs-lookup"><span data-stu-id="82110-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82110-137">`SetPriority` non indica se il livello di priorità del thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="82110-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="82110-138">Chiamare [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) per determinare il valore del livello di priorità del thread dell'attività.</span><span class="sxs-lookup"><span data-stu-id="82110-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="82110-139">I valori del livello di priorità dei thread sono definiti dalla funzione Win32 `SetThreadPriority`.</span><span class="sxs-lookup"><span data-stu-id="82110-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="82110-140">Per ulteriori informazioni sulla priorità dei thread, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="82110-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82110-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82110-141">Requirements</span></span>  
 <span data-ttu-id="82110-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82110-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82110-143">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82110-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82110-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82110-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82110-145">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82110-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82110-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82110-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="82110-147">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="82110-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="82110-148">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="82110-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="82110-149">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="82110-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="82110-150">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="82110-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="82110-151">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="82110-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
