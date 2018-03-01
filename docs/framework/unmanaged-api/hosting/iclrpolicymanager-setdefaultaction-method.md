---
title: Metodo ICLRPolicyManager::SetDefaultAction
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
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751853aaf4322c15b44bb9b912d293a081c24ba8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="3c79a-102">Metodo ICLRPolicyManager::SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="3c79a-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="3c79a-103">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3c79a-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c79a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c79a-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c79a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c79a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="3c79a-106">[in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'azione per CLR che deve essere personalizzato il comportamento.</span><span class="sxs-lookup"><span data-stu-id="3c79a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="3c79a-107">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione di criteri CLR deve intraprendere quando `operation` si verifica.</span><span class="sxs-lookup"><span data-stu-id="3c79a-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c79a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c79a-108">Return Value</span></span>  
  
|<span data-ttu-id="3c79a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c79a-109">HRESULT</span></span>|<span data-ttu-id="3c79a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c79a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c79a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c79a-111">S_OK</span></span>|<span data-ttu-id="3c79a-112">`SetDefaultAction`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c79a-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="3c79a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c79a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c79a-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c79a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c79a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c79a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c79a-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c79a-116">The call timed out.</span></span>|  
|<span data-ttu-id="3c79a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c79a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c79a-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3c79a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c79a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c79a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c79a-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3c79a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c79a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c79a-121">E_FAIL</span></span>|<span data-ttu-id="3c79a-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3c79a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c79a-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3c79a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c79a-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c79a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c79a-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3c79a-125">E_INVALIDARG</span></span>|<span data-ttu-id="3c79a-126">Un valido `action` è stato specificato per il `operation`, o è stato specificato un valore non valido per `operation`.</span><span class="sxs-lookup"><span data-stu-id="3c79a-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c79a-127">Note</span><span class="sxs-lookup"><span data-stu-id="3c79a-127">Remarks</span></span>  
 <span data-ttu-id="3c79a-128">Non tutti i valori di azione criteri possono essere specificati come il comportamento predefinito per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="3c79a-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="3c79a-129">`SetDefaultAction`in genere possono essere utilizzate solo per attivare un comportamento.</span><span class="sxs-lookup"><span data-stu-id="3c79a-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="3c79a-130">Ad esempio, un host può specificare che le interruzioni di thread deve essere trasformata nelle interruzioni di thread, ma non è possibile specificare l'opposto.</span><span class="sxs-lookup"><span data-stu-id="3c79a-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="3c79a-131">La tabella seguente descrive validi `action` i valori per ogni possibile `operation` valore.</span><span class="sxs-lookup"><span data-stu-id="3c79a-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="3c79a-132">Valore per`operation`</span><span class="sxs-lookup"><span data-stu-id="3c79a-132">Value for `operation`</span></span>|<span data-ttu-id="3c79a-133">Valori validi per`action`</span><span class="sxs-lookup"><span data-stu-id="3c79a-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="3c79a-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="3c79a-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="3c79a-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="3c79a-135">-   eAbortThread</span></span><br /><span data-ttu-id="3c79a-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="3c79a-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="3c79a-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-139">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3c79a-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3c79a-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="3c79a-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3c79a-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="3c79a-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="3c79a-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="3c79a-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-148">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3c79a-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3c79a-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="3c79a-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-155">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3c79a-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="3c79a-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="3c79a-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-161">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3c79a-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3c79a-165">OPR_ProcessExit</span></span>|<span data-ttu-id="3c79a-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-166">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3c79a-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="3c79a-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="3c79a-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="3c79a-171">-   eNoAction</span></span><br /><span data-ttu-id="3c79a-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="3c79a-172">-   eAbortThread</span></span><br /><span data-ttu-id="3c79a-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="3c79a-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="3c79a-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3c79a-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3c79a-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-176">-   eExitProcess</span></span><br /><span data-ttu-id="3c79a-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="3c79a-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3c79a-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3c79a-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3c79a-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c79a-180">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c79a-180">Requirements</span></span>  
 <span data-ttu-id="3c79a-181">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c79a-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c79a-182">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3c79a-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c79a-183">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c79a-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c79a-184">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c79a-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c79a-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c79a-185">See Also</span></span>  
 [<span data-ttu-id="3c79a-186">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="3c79a-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="3c79a-187">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="3c79a-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="3c79a-188">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3c79a-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
