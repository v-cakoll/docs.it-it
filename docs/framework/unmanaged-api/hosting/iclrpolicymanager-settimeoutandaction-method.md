---
title: Metodo ICLRPolicyManager::SetTimeoutAndAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b896cebea83071bb2a8756157b48c62dcfda7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112269"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="61fcd-102">Metodo ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="61fcd-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="61fcd-103">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando l'operazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="61fcd-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61fcd-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61fcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="61fcd-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="61fcd-106">[in] Uno dei [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'operazione per cui impostare il timeout e criteri `action`.</span><span class="sxs-lookup"><span data-stu-id="61fcd-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="61fcd-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="61fcd-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="61fcd-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="61fcd-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="61fcd-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="61fcd-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="61fcd-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="61fcd-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="61fcd-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="61fcd-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="61fcd-112">[in] Il nuovo valore di timeout, espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="61fcd-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="61fcd-113">Un valore di infinito, `operation` mai il timeout.</span><span class="sxs-lookup"><span data-stu-id="61fcd-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="61fcd-114">[in] Uno dei [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione di criteri che devono richiedere quando CLR `operation` si verifica.</span><span class="sxs-lookup"><span data-stu-id="61fcd-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61fcd-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61fcd-115">Return Value</span></span>  
  
|<span data-ttu-id="61fcd-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61fcd-116">HRESULT</span></span>|<span data-ttu-id="61fcd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61fcd-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61fcd-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="61fcd-118">S_OK</span></span>|<span data-ttu-id="61fcd-119">`SetTimeoutAndAction` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="61fcd-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="61fcd-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61fcd-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61fcd-121">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="61fcd-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61fcd-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61fcd-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61fcd-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61fcd-123">The call timed out.</span></span>|  
|<span data-ttu-id="61fcd-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61fcd-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61fcd-125">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="61fcd-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61fcd-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61fcd-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61fcd-127">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="61fcd-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61fcd-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61fcd-128">E_FAIL</span></span>|<span data-ttu-id="61fcd-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="61fcd-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61fcd-130">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="61fcd-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61fcd-131">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="61fcd-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="61fcd-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61fcd-132">E_INVALIDARG</span></span>|<span data-ttu-id="61fcd-133">Non è possibile impostare un timeout per l'oggetto specificato `operation`, o è stato specificato un valore non valido per `action`.</span><span class="sxs-lookup"><span data-stu-id="61fcd-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61fcd-134">Note</span><span class="sxs-lookup"><span data-stu-id="61fcd-134">Remarks</span></span>  
 <span data-ttu-id="61fcd-135">`SetTimeoutAndAction` incapsula le funzionalità dei [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) e [SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) metodi e può essere chiamato al posto di chiamate sequenziali per questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="61fcd-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="61fcd-136">Non tutti i valori di azione dei criteri possono essere specificati come il comportamento di timeout per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="61fcd-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="61fcd-137">Vedere le sezioni di osservazioni degli argomenti di questi due metodi per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="61fcd-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61fcd-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61fcd-138">Requirements</span></span>  
 <span data-ttu-id="61fcd-139">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61fcd-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61fcd-140">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61fcd-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61fcd-141">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="61fcd-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61fcd-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61fcd-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fcd-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61fcd-143">See also</span></span>

- [<span data-ttu-id="61fcd-144">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="61fcd-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="61fcd-145">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="61fcd-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="61fcd-146">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="61fcd-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="61fcd-147">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="61fcd-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="61fcd-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="61fcd-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
