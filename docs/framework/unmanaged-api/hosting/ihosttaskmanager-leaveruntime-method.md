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
ms.openlocfilehash: 3d31c5c1b95d250f90b202b391d908f9c12afb84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444477"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="d0ff0-102">Metodo IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="d0ff0-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="d0ff0-103">Notifica all'host che l'attività attualmente in esecuzione sta per lasciare common language runtime (CLR) e immettere il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0ff0-104">Una chiamata corrispondente al [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta rientrando nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ff0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0ff0-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0ff0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0ff0-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="d0ff0-107">[in] L'indirizzo all'interno del file eseguibile portabile con mapping di funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0ff0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0ff0-108">Return Value</span></span>  
  
|<span data-ttu-id="d0ff0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0ff0-109">HRESULT</span></span>|<span data-ttu-id="d0ff0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0ff0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0ff0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0ff0-111">S_OK</span></span>|<span data-ttu-id="d0ff0-112">`LeaveRuntime` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="d0ff0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0ff0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0ff0-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d0ff0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0ff0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0ff0-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-116">The call timed out.</span></span>|  
|<span data-ttu-id="d0ff0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0ff0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0ff0-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0ff0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0ff0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0ff0-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0ff0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0ff0-121">E_FAIL</span></span>|<span data-ttu-id="d0ff0-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0ff0-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0ff0-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d0ff0-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0ff0-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d0ff0-126">Memoria insufficiente è disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0ff0-127">Note</span><span class="sxs-lookup"><span data-stu-id="d0ff0-127">Remarks</span></span>  
 <span data-ttu-id="d0ff0-128">Le sequenze di chiamate da e verso codice non gestito possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="d0ff0-129">Ad esempio, nell'elenco seguente descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="d0ff0-130">Operazione</span><span class="sxs-lookup"><span data-stu-id="d0ff0-130">Action</span></span>|<span data-ttu-id="d0ff0-131">Chiamata al metodo corrispondente</span><span class="sxs-lookup"><span data-stu-id="d0ff0-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="d0ff0-132">Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="d0ff0-133">La funzione C non gestita chiama un metodo in una DLL gestita scritta in c#.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="d0ff0-134">La funzione c# gestita chiama un'altra funzione non gestita scritta in C, sempre tramite platform invoke.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="d0ff0-135">La seconda funzione non gestita restituisce l'esecuzione della funzione di c#.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="d0ff0-136">La funzione c# restituisce l'esecuzione per la prima funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="d0ff0-137">La prima funzione non gestita restituisce l'esecuzione del programma Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d0ff0-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="d0ff0-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0ff0-138">Requirements</span></span>  
 <span data-ttu-id="d0ff0-139">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0ff0-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ff0-140">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d0ff0-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0ff0-141">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d0ff0-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0ff0-142">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ff0-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ff0-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ff0-143">See Also</span></span>  
 [<span data-ttu-id="d0ff0-144">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d0ff0-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d0ff0-145">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d0ff0-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d0ff0-146">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="d0ff0-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d0ff0-147">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d0ff0-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
