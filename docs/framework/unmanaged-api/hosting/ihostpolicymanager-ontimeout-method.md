---
title: Metodo IHostPolicyManager::OnTimeout
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
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b8c29bc281b64368e8b310e2b13f3fcb1bdc6ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="ffa28-102">Metodo IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="ffa28-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="ffa28-103">Notifica all'host che common language runtime (CLR) sta per eseguire l'azione specificata da una chiamata al [ICLRPolicyManager::](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) metodo in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="ffa28-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffa28-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffa28-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ffa28-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ffa28-106">[in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica il tipo di operazione scadute.</span><span class="sxs-lookup"><span data-stu-id="ffa28-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="ffa28-107">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione CLR richiede in risposta al timeout.</span><span class="sxs-lookup"><span data-stu-id="ffa28-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffa28-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ffa28-108">Return Value</span></span>  
  
|<span data-ttu-id="ffa28-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffa28-109">HRESULT</span></span>|<span data-ttu-id="ffa28-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffa28-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffa28-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffa28-111">S_OK</span></span>|<span data-ttu-id="ffa28-112">`OnTimeout`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ffa28-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="ffa28-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffa28-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffa28-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ffa28-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffa28-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffa28-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffa28-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ffa28-116">The call timed out.</span></span>|  
|<span data-ttu-id="ffa28-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffa28-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffa28-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="ffa28-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffa28-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffa28-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffa28-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ffa28-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffa28-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffa28-121">E_FAIL</span></span>|<span data-ttu-id="ffa28-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ffa28-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffa28-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ffa28-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffa28-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ffa28-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffa28-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffa28-125">Requirements</span></span>  
 <span data-ttu-id="ffa28-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa28-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa28-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ffa28-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffa28-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffa28-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffa28-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa28-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa28-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffa28-130">See Also</span></span>  
 [<span data-ttu-id="ffa28-131">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="ffa28-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="ffa28-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="ffa28-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="ffa28-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ffa28-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="ffa28-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ffa28-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
