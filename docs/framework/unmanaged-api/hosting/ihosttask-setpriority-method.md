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
ms.openlocfilehash: ac3a8479cdf05e55885bd55d4e4fb8e6e47686f9
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842400"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="5c65e-102">Metodo IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="5c65e-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="5c65e-103">Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall'istanza corrente di [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5c65e-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c65e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c65e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c65e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c65e-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="5c65e-106">in Integer che rappresenta il valore di priorità del thread richiesto per l'attività rappresentata dall' `IHostTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="5c65e-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c65e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5c65e-107">Return Value</span></span>  
  
|<span data-ttu-id="5c65e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c65e-108">HRESULT</span></span>|<span data-ttu-id="5c65e-109">Description</span><span class="sxs-lookup"><span data-stu-id="5c65e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c65e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c65e-110">S_OK</span></span>|<span data-ttu-id="5c65e-111">`SetPriority`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5c65e-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="5c65e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c65e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c65e-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5c65e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c65e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c65e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c65e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5c65e-115">The call timed out.</span></span>|  
|<span data-ttu-id="5c65e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c65e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c65e-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5c65e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c65e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c65e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c65e-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5c65e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c65e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c65e-120">E_FAIL</span></span>|<span data-ttu-id="5c65e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5c65e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c65e-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5c65e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c65e-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5c65e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c65e-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c65e-124">Remarks</span></span>  
 <span data-ttu-id="5c65e-125">Ai thread viene concesso il tempo di elaborazione utilizzando un sistema Round Robin che è parzialmente basato sul livello di priorità di un thread.</span><span class="sxs-lookup"><span data-stu-id="5c65e-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="5c65e-126">`SetPriority`consente a CLR di impostare il livello di priorità del thread per l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="5c65e-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="5c65e-127">`newPriority`Sono supportati i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="5c65e-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="5c65e-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="5c65e-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="5c65e-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="5c65e-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="5c65e-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="5c65e-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="5c65e-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="5c65e-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="5c65e-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="5c65e-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="5c65e-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="5c65e-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="5c65e-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="5c65e-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="5c65e-135">CLR chiama `SetPriority` quando il valore di <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> viene modificato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="5c65e-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="5c65e-136">Un host può definire i propri algoritmi per l'assegnazione della priorità del thread ed è libero di ignorare questa richiesta.</span><span class="sxs-lookup"><span data-stu-id="5c65e-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c65e-137">`SetPriority`non indica se il livello di priorità del thread è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="5c65e-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="5c65e-138">Chiamare [IHostTask:: GetPriority](ihosttask-getpriority-method.md) per determinare il valore del livello di priorità del thread dell'attività.</span><span class="sxs-lookup"><span data-stu-id="5c65e-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="5c65e-139">I valori del livello di priorità dei thread sono definiti dalla `SetThreadPriority` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="5c65e-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="5c65e-140">Per ulteriori informazioni sulla priorità dei thread, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5c65e-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c65e-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c65e-141">Requirements</span></span>  
 <span data-ttu-id="5c65e-142">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c65e-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c65e-143">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c65e-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c65e-144">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c65e-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c65e-145">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c65e-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c65e-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c65e-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="5c65e-147">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5c65e-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5c65e-148">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5c65e-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5c65e-149">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5c65e-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5c65e-150">Metodo GetPriority</span><span class="sxs-lookup"><span data-stu-id="5c65e-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="5c65e-151">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5c65e-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
