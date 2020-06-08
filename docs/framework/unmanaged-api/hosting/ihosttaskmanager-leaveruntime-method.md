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
ms.openlocfilehash: deaebbce3b9b8a26bf9668b826a6818dba94dcc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501379"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="e6486-102">Metodo IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="e6486-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="e6486-103">Notifica all'host che l'attività attualmente in esecuzione sta per uscire dalla Common Language Runtime (CLR) e immettere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="e6486-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e6486-104">Una chiamata corrispondente a [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta reimmettendo il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e6486-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6486-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6486-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6486-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6486-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="e6486-107">in Indirizzo all'interno del file eseguibile portatile mappato della funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="e6486-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6486-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6486-108">Return Value</span></span>  
  
|<span data-ttu-id="e6486-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6486-109">HRESULT</span></span>|<span data-ttu-id="e6486-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6486-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6486-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6486-111">S_OK</span></span>|<span data-ttu-id="e6486-112">`LeaveRuntime`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e6486-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="e6486-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6486-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6486-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6486-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6486-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6486-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6486-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6486-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6486-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6486-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6486-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e6486-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6486-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6486-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6486-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e6486-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6486-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6486-121">E_FAIL</span></span>|<span data-ttu-id="e6486-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e6486-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6486-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e6486-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6486-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e6486-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e6486-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e6486-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e6486-126">La memoria disponibile non è sufficiente per completare l'allocazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="e6486-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6486-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6486-127">Remarks</span></span>  
 <span data-ttu-id="e6486-128">Le sequenze di chiamate da e verso codice non gestito possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="e6486-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="e6486-129">L'elenco seguente, ad esempio, descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.</span><span class="sxs-lookup"><span data-stu-id="e6486-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="e6486-130">Azione</span><span class="sxs-lookup"><span data-stu-id="e6486-130">Action</span></span>|<span data-ttu-id="e6486-131">Chiamata al metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="e6486-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="e6486-132">Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e6486-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="e6486-133">La funzione C non gestita chiama un metodo in una DLL gestita scritta in C#.</span><span class="sxs-lookup"><span data-stu-id="e6486-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="e6486-134">La funzione C# gestita chiama un'altra funzione non gestita scritta in C, usando anche platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e6486-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="e6486-135">La seconda funzione non gestita restituisce l'esecuzione alla funzione C#.</span><span class="sxs-lookup"><span data-stu-id="e6486-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="e6486-136">La funzione C# restituisce l'esecuzione alla prima funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e6486-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="e6486-137">La prima funzione non gestita restituisce l'esecuzione al programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e6486-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="e6486-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6486-138">Requirements</span></span>  
 <span data-ttu-id="e6486-139">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6486-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6486-140">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6486-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6486-141">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6486-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6486-142">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6486-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6486-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6486-143">See also</span></span>

- [<span data-ttu-id="e6486-144">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e6486-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e6486-145">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e6486-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e6486-146">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="e6486-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e6486-147">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e6486-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
