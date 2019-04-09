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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154167"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="5e51b-102">Metodo IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="5e51b-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="5e51b-103">Notifica all'host controllo lasciando common language runtime (CLR) che è una funzione non gestita, a sua volta, chiamato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5e51b-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e51b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e51b-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5e51b-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5e51b-105">Return Value</span></span>  
  
|<span data-ttu-id="5e51b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e51b-106">HRESULT</span></span>|<span data-ttu-id="5e51b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e51b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e51b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e51b-108">S_OK</span></span>|`ReverseLeaveRuntime` <span data-ttu-id="5e51b-109">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5e51b-109">returned successfully.</span></span>|  
|<span data-ttu-id="5e51b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e51b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e51b-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e51b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e51b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e51b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e51b-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e51b-113">The call timed out.</span></span>|  
|<span data-ttu-id="5e51b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e51b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e51b-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="5e51b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e51b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e51b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e51b-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5e51b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e51b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e51b-118">E_FAIL</span></span>|<span data-ttu-id="5e51b-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5e51b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e51b-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5e51b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e51b-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5e51b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e51b-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5e51b-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5e51b-123">Memoria insufficiente è disponibile per completare l'allocazione delle risorse richieste.</span><span class="sxs-lookup"><span data-stu-id="5e51b-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e51b-124">Note</span><span class="sxs-lookup"><span data-stu-id="5e51b-124">Remarks</span></span>  
 <span data-ttu-id="5e51b-125">CLR chiama `ReverseLeaveRuntime` per notificare all'host che l'attività attualmente in esecuzione restituisce controllo a una funzione non gestita, a sua volta, chiamato dal codice gestito mediante platform invoke.</span><span class="sxs-lookup"><span data-stu-id="5e51b-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="5e51b-126">Ogni chiamata a `ReverseLeaveRuntime` corrisponde a una chiamata corrispondente [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e51b-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e51b-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e51b-127">Requirements</span></span>  
 <span data-ttu-id="5e51b-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e51b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e51b-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e51b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e51b-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5e51b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5e51b-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5e51b-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e51b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e51b-132">See also</span></span>

- [<span data-ttu-id="5e51b-133">Metodo CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="5e51b-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="5e51b-134">Metodo EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="5e51b-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="5e51b-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5e51b-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5e51b-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5e51b-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5e51b-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5e51b-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5e51b-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5e51b-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="5e51b-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="5e51b-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- [<span data-ttu-id="5e51b-140">Informazioni dettagliate su platform invoke</span><span class="sxs-lookup"><span data-stu-id="5e51b-140">A Closer Look at Platform Invoke</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))
