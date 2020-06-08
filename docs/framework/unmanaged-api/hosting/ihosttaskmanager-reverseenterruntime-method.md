---
title: Metodo IHostTaskManager::ReverseEnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
ms.openlocfilehash: 1981fdf25440a296801bdbd06c41ebcb4b87e870
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501395"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="9d8dc-102">Metodo IHostTaskManager::ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="9d8dc-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="9d8dc-103">Notifica all'host che viene effettuata una chiamata al Common Language Runtime (CLR) dal codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d8dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d8dc-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9d8dc-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9d8dc-105">Return Value</span></span>  
  
|<span data-ttu-id="9d8dc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d8dc-106">HRESULT</span></span>|<span data-ttu-id="9d8dc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d8dc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d8dc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d8dc-108">S_OK</span></span>|<span data-ttu-id="9d8dc-109">`ReverseEnterRuntime`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="9d8dc-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9d8dc-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9d8dc-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9d8dc-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9d8dc-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9d8dc-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-113">The call timed out.</span></span>|  
|<span data-ttu-id="9d8dc-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d8dc-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9d8dc-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9d8dc-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9d8dc-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9d8dc-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9d8dc-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9d8dc-118">E_FAIL</span></span>|<span data-ttu-id="9d8dc-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9d8dc-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9d8dc-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9d8dc-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9d8dc-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9d8dc-123">La memoria disponibile non è sufficiente per completare l'allocazione delle risorse richiesta.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d8dc-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9d8dc-124">Remarks</span></span>  
 <span data-ttu-id="9d8dc-125">Se la chiamata a CLR viene eseguita da una sequenza originata nel codice gestito, ogni chiamata a `ReverseEnterRuntime` corrisponde a una chiamata a [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="9d8dc-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d8dc-126">Le chiamate possono provenire da codice non gestito senza essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="9d8dc-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="9d8dc-127">In questo caso, non viene effettuata alcuna chiamata a [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)o `ReverseLeaveRuntime` e il numero di chiamate a `ReverseEnterRuntime` non equivale al numero di chiamate a `ReverseLeaveRuntime` .</span><span class="sxs-lookup"><span data-stu-id="9d8dc-127">In this case, there is no call to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d8dc-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d8dc-128">Requirements</span></span>  
 <span data-ttu-id="9d8dc-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d8dc-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d8dc-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9d8dc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d8dc-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d8dc-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d8dc-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d8dc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8dc-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d8dc-133">See also</span></span>

- [<span data-ttu-id="9d8dc-134">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9d8dc-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9d8dc-135">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9d8dc-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9d8dc-136">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="9d8dc-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9d8dc-137">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9d8dc-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
