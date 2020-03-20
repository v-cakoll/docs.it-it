---
title: Metodo IHostPolicyManager::OnTimeout
ms.date: 03/30/2017
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
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178010"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="6451e-102">Metodo IHostPolicyManager::OnTimeout</span><span class="sxs-lookup"><span data-stu-id="6451e-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="6451e-103">Notifica all'host che Common Language Runtime (CLR) sta per eseguire l'azione specificata da una chiamata al metodo [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="6451e-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6451e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6451e-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6451e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6451e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="6451e-106">[in] Uno dei valori [di EClrOperation,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) che indica il tipo di operazione sfrattato.</span><span class="sxs-lookup"><span data-stu-id="6451e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="6451e-107">[in] Uno dei valori [di EPolicyAction,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) che indica l'azione eseguita da CLR in risposta al timeout.</span><span class="sxs-lookup"><span data-stu-id="6451e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6451e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6451e-108">Return Value</span></span>  
  
|<span data-ttu-id="6451e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6451e-109">HRESULT</span></span>|<span data-ttu-id="6451e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6451e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6451e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6451e-111">S_OK</span></span>|<span data-ttu-id="6451e-112">`OnTimeout`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="6451e-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="6451e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6451e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6451e-114">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6451e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6451e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6451e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6451e-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6451e-116">The call timed out.</span></span>|  
|<span data-ttu-id="6451e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6451e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6451e-118">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="6451e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6451e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6451e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6451e-120">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6451e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6451e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6451e-121">E_FAIL</span></span>|<span data-ttu-id="6451e-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6451e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6451e-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6451e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6451e-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6451e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6451e-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6451e-125">Requirements</span></span>  
 <span data-ttu-id="6451e-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6451e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6451e-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6451e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6451e-128">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6451e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6451e-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6451e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6451e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6451e-130">See also</span></span>

- [<span data-ttu-id="6451e-131">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="6451e-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="6451e-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="6451e-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="6451e-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6451e-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="6451e-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6451e-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
