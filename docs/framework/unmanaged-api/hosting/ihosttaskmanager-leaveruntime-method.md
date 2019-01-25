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
ms.openlocfilehash: e22ed258390f7adc9bbf8cd425afe208b2f9b12c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607043"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="b7bf2-102">Metodo IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="b7bf2-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="b7bf2-103">Notifica all'host che l'attività attualmente in esecuzione sta per lasciare common language runtime (CLR) e immettere il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7bf2-104">Una chiamata corrispondente al [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione è reinserimento codice gestito.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bf2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7bf2-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7bf2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7bf2-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="b7bf2-107">[in] L'indirizzo all'interno del file eseguibile portabile con mapping di funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7bf2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b7bf2-108">Return Value</span></span>  
  
|<span data-ttu-id="b7bf2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7bf2-109">HRESULT</span></span>|<span data-ttu-id="b7bf2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7bf2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7bf2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7bf2-111">S_OK</span></span>|<span data-ttu-id="b7bf2-112">`LeaveRuntime` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b7bf2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7bf2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7bf2-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7bf2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7bf2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7bf2-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-116">The call timed out.</span></span>|  
|<span data-ttu-id="b7bf2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7bf2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7bf2-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7bf2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7bf2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7bf2-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7bf2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7bf2-121">E_FAIL</span></span>|<span data-ttu-id="b7bf2-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7bf2-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7bf2-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7bf2-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b7bf2-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b7bf2-126">Memoria insufficiente è disponibile per completare l'allocazione di richiesta.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7bf2-127">Note</span><span class="sxs-lookup"><span data-stu-id="b7bf2-127">Remarks</span></span>  
 <span data-ttu-id="b7bf2-128">Le sequenze di chiamate da e verso il codice non gestito possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="b7bf2-129">Ad esempio, l'elenco seguente descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime`, [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="b7bf2-130">Operazione</span><span class="sxs-lookup"><span data-stu-id="b7bf2-130">Action</span></span>|<span data-ttu-id="b7bf2-131">Chiamata di metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="b7bf2-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="b7bf2-132">Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C usando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b7bf2-133">La funzione non gestita C chiama un metodo in una DLL gestita scritta in C#.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="b7bf2-134">Gestito C# funzione chiama un'altra funzione non gestita scritta in C, anche usando il platform invoke.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b7bf2-135">La seconda funzione non gestita restituisce l'esecuzione di C# (funzione).</span><span class="sxs-lookup"><span data-stu-id="b7bf2-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="b7bf2-136">Il C# funzione restituisce l'esecuzione per la prima funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="b7bf2-137">La funzione non gestita prima restituisce l'esecuzione del programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b7bf2-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="b7bf2-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7bf2-138">Requirements</span></span>  
 <span data-ttu-id="b7bf2-139">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7bf2-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bf2-140">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7bf2-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7bf2-141">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b7bf2-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7bf2-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bf2-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bf2-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7bf2-143">See also</span></span>
- [<span data-ttu-id="b7bf2-144">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b7bf2-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b7bf2-145">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b7bf2-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b7bf2-146">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="b7bf2-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b7bf2-147">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b7bf2-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
