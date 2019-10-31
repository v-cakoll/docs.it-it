---
title: Metodo IHostTaskManager::ReverseLeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: 362239c584f469c9bd88f9f937bb3cdae7235429
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132949"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="7c550-102">Metodo IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="7c550-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="7c550-103">Notifica all'host che il controllo sta lasciando il Common Language Runtime (CLR) e immettendo una funzione non gestita che, a sua volta, è stata chiamata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7c550-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c550-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c550-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7c550-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c550-105">Return Value</span></span>  
  
|<span data-ttu-id="7c550-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c550-106">HRESULT</span></span>|<span data-ttu-id="7c550-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c550-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c550-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c550-108">S_OK</span></span>|<span data-ttu-id="7c550-109">`ReverseLeaveRuntime` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7c550-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7c550-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c550-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c550-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7c550-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c550-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c550-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c550-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c550-113">The call timed out.</span></span>|  
|<span data-ttu-id="7c550-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c550-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c550-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="7c550-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c550-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c550-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c550-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7c550-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c550-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c550-118">E_FAIL</span></span>|<span data-ttu-id="7c550-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7c550-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c550-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7c550-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c550-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c550-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c550-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c550-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c550-123">La memoria disponibile non è sufficiente per completare l'allocazione delle risorse richiesta.</span><span class="sxs-lookup"><span data-stu-id="7c550-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c550-124">Note</span><span class="sxs-lookup"><span data-stu-id="7c550-124">Remarks</span></span>  
 <span data-ttu-id="7c550-125">CLR chiama `ReverseLeaveRuntime` per informare l'host che l'attività attualmente in esecuzione restituisce il controllo a una funzione non gestita che, a sua volta, è stata chiamata dal codice gestito tramite platform invoke.</span><span class="sxs-lookup"><span data-stu-id="7c550-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="7c550-126">Ogni chiamata a `ReverseLeaveRuntime` corrisponde a una chiamata corrispondente a [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="7c550-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c550-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c550-127">Requirements</span></span>  
 <span data-ttu-id="7c550-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c550-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c550-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7c550-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c550-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7c550-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c550-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c550-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c550-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c550-132">See also</span></span>

- [<span data-ttu-id="7c550-133">Metodo CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="7c550-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="7c550-134">Metodo EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="7c550-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="7c550-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="7c550-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7c550-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="7c550-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7c550-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="7c550-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7c550-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="7c550-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7c550-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="7c550-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="7c550-140">[Informazioni dettagliate su platform invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7c550-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
