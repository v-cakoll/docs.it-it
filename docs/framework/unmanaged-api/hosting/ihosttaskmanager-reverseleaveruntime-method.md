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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd3012d966c777749eb800b8986974a4e8d401f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796635"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="980d3-102">Metodo IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="980d3-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="980d3-103">Notifica all'host controllo lasciando common language runtime (CLR) che è una funzione non gestita, a sua volta, chiamato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="980d3-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="980d3-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="980d3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="980d3-105">Return Value</span></span>  
  
|<span data-ttu-id="980d3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="980d3-106">HRESULT</span></span>|<span data-ttu-id="980d3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="980d3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="980d3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="980d3-108">S_OK</span></span>|<span data-ttu-id="980d3-109">`ReverseLeaveRuntime` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="980d3-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="980d3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="980d3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="980d3-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="980d3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="980d3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="980d3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="980d3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="980d3-113">The call timed out.</span></span>|  
|<span data-ttu-id="980d3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="980d3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="980d3-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="980d3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="980d3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="980d3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="980d3-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="980d3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="980d3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="980d3-118">E_FAIL</span></span>|<span data-ttu-id="980d3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="980d3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="980d3-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="980d3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="980d3-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="980d3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="980d3-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="980d3-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="980d3-123">Memoria insufficiente è disponibile per completare l'allocazione delle risorse richieste.</span><span class="sxs-lookup"><span data-stu-id="980d3-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="980d3-124">Note</span><span class="sxs-lookup"><span data-stu-id="980d3-124">Remarks</span></span>  
 <span data-ttu-id="980d3-125">CLR chiama `ReverseLeaveRuntime` per notificare all'host che l'attività attualmente in esecuzione restituisce controllo a una funzione non gestita, a sua volta, chiamato dal codice gestito mediante platform invoke.</span><span class="sxs-lookup"><span data-stu-id="980d3-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="980d3-126">Ogni chiamata a `ReverseLeaveRuntime` corrisponde a una chiamata corrispondente [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="980d3-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="980d3-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="980d3-127">Requirements</span></span>  
 <span data-ttu-id="980d3-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="980d3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980d3-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="980d3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="980d3-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="980d3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="980d3-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980d3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980d3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="980d3-132">See also</span></span>

- [<span data-ttu-id="980d3-133">Metodo CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="980d3-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="980d3-134">Metodo EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="980d3-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="980d3-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="980d3-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="980d3-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="980d3-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="980d3-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="980d3-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="980d3-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="980d3-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="980d3-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="980d3-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="980d3-140">[Informazioni dettagliate su platform invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="980d3-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
