---
title: Metodo IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b2e8e636915b3921fcd727fc78a3fb18fc69104
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959032"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="8b0a4-102">Metodo IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="8b0a4-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="8b0a4-103">Notifica all'host che l'attività attualmente in esecuzione sta per uscire dalla Common Language Runtime (CLR) e immettere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8b0a4-104">Una chiamata corrispondente a [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta reimmettendo il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b0a4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b0a4-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b0a4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b0a4-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="8b0a4-107">in Indirizzo all'interno del file eseguibile portatile mappato della funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b0a4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8b0a4-108">Return Value</span></span>  
  
|<span data-ttu-id="8b0a4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b0a4-109">HRESULT</span></span>|<span data-ttu-id="8b0a4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b0a4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b0a4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b0a4-111">S_OK</span></span>|<span data-ttu-id="8b0a4-112">`LeaveRuntime`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="8b0a4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b0a4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b0a4-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b0a4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b0a4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b0a4-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-116">The call timed out.</span></span>|  
|<span data-ttu-id="8b0a4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b0a4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b0a4-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b0a4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b0a4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b0a4-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b0a4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b0a4-121">E_FAIL</span></span>|<span data-ttu-id="8b0a4-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b0a4-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b0a4-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8b0a4-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8b0a4-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8b0a4-126">La memoria disponibile non è sufficiente per completare l'allocazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b0a4-127">Note</span><span class="sxs-lookup"><span data-stu-id="8b0a4-127">Remarks</span></span>  
 <span data-ttu-id="8b0a4-128">Le sequenze di chiamate da e verso codice non gestito possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="8b0a4-129">L'elenco seguente, ad esempio, descrive una situazione ipotetica in cui la sequenza di `LeaveRuntime`chiamate a, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="8b0a4-130">Azione</span><span class="sxs-lookup"><span data-stu-id="8b0a4-130">Action</span></span>|<span data-ttu-id="8b0a4-131">Chiamata al metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="8b0a4-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="8b0a4-132">Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="8b0a4-133">La funzione C non gestita chiama un metodo in una DLL gestita scritta in C#.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="8b0a4-134">La funzione C# gestita chiama un'altra funzione non gestita scritta in C, usando anche Platform Invoke.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="8b0a4-135">La seconda funzione non gestita restituisce l' C# esecuzione alla funzione.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="8b0a4-136">La C# funzione restituisce l'esecuzione alla prima funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="8b0a4-137">La prima funzione non gestita restituisce l'esecuzione al programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8b0a4-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="8b0a4-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b0a4-138">Requirements</span></span>  
 <span data-ttu-id="8b0a4-139">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b0a4-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b0a4-140">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8b0a4-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b0a4-141">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8b0a4-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b0a4-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b0a4-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b0a4-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b0a4-143">See also</span></span>

- [<span data-ttu-id="8b0a4-144">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8b0a4-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8b0a4-145">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b0a4-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8b0a4-146">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8b0a4-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8b0a4-147">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b0a4-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
