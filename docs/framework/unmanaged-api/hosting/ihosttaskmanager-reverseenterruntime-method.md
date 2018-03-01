---
title: Metodo IHostTaskManager::ReverseEnterRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69743f6b7229f89d19d4134a11bb5f37fe5ca928
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="a41d8-102">Metodo IHostTaskManager::ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="a41d8-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="a41d8-103">Notifica all'host che è in corso una chiamata a common language runtime (CLR) dal codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="a41d8-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a41d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a41d8-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a41d8-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a41d8-105">Return Value</span></span>  
  
|<span data-ttu-id="a41d8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a41d8-106">HRESULT</span></span>|<span data-ttu-id="a41d8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a41d8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a41d8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a41d8-108">S_OK</span></span>|<span data-ttu-id="a41d8-109">`ReverseEnterRuntime`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a41d8-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="a41d8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a41d8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a41d8-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a41d8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a41d8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a41d8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a41d8-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a41d8-113">The call timed out.</span></span>|  
|<span data-ttu-id="a41d8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a41d8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a41d8-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="a41d8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a41d8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a41d8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a41d8-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a41d8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a41d8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a41d8-118">E_FAIL</span></span>|<span data-ttu-id="a41d8-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a41d8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a41d8-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a41d8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a41d8-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a41d8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a41d8-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a41d8-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a41d8-123">Memoria insufficiente è disponibile per completare l'allocazione delle risorse richieste.</span><span class="sxs-lookup"><span data-stu-id="a41d8-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a41d8-124">Note</span><span class="sxs-lookup"><span data-stu-id="a41d8-124">Remarks</span></span>  
 <span data-ttu-id="a41d8-125">Se viene effettuata la chiamata in CLR da una sequenza che ha avuto origine nel codice gestito, ogni chiamata a `ReverseEnterRuntime` corrisponde a una chiamata a [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="a41d8-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a41d8-126">Le chiamate possono provenire da codice non gestito senza essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="a41d8-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="a41d8-127">In questo caso, non vi è alcuna chiamata a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), o `ReverseLeaveRuntime`e il numero di chiamate a `ReverseEnterRuntime` è uguale al numero di chiamate a `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="a41d8-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a41d8-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a41d8-128">Requirements</span></span>  
 <span data-ttu-id="a41d8-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a41d8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a41d8-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a41d8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a41d8-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a41d8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a41d8-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a41d8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41d8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a41d8-133">See Also</span></span>  
 [<span data-ttu-id="a41d8-134">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a41d8-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a41d8-135">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a41d8-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a41d8-136">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="a41d8-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a41d8-137">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a41d8-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
