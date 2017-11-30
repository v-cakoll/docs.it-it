---
title: Metodo ICLRPolicyManager::SetActionOnFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5dc8e27ed1a5701886c3583a7515e4212f490208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="00ea4-102">Metodo ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="00ea4-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="00ea4-103">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="00ea4-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ea4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00ea4-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00ea4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00ea4-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="00ea4-106">[in] Uno del [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore per il quale eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="00ea4-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="00ea4-107">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione da intraprendere quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="00ea4-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="00ea4-108">Per un elenco di valori supportati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="00ea4-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00ea4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00ea4-109">Return Value</span></span>  
  
|<span data-ttu-id="00ea4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00ea4-110">HRESULT</span></span>|<span data-ttu-id="00ea4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00ea4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00ea4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="00ea4-112">S_OK</span></span>|<span data-ttu-id="00ea4-113">`SetActionOnFailure`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="00ea4-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="00ea4-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00ea4-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00ea4-115">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="00ea4-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00ea4-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00ea4-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00ea4-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="00ea4-117">The call timed out.</span></span>|  
|<span data-ttu-id="00ea4-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00ea4-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00ea4-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="00ea4-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00ea4-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00ea4-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00ea4-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="00ea4-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00ea4-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00ea4-122">E_FAIL</span></span>|<span data-ttu-id="00ea4-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="00ea4-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00ea4-124">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="00ea4-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00ea4-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00ea4-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="00ea4-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="00ea4-126">E_INVALIDARG</span></span>|<span data-ttu-id="00ea4-127">Impossibile impostare un'azione di criteri per l'operazione specificata o è stata specificata un'azione di criteri non validi per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="00ea4-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00ea4-128">Note</span><span class="sxs-lookup"><span data-stu-id="00ea4-128">Remarks</span></span>  
 <span data-ttu-id="00ea4-129">Per impostazione predefinita, CLR genera un'eccezione quando non è possibile assegnare una risorsa, ad esempio la memoria.</span><span class="sxs-lookup"><span data-stu-id="00ea4-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="00ea4-130">`SetActionOnFailure`consente all'host di eseguire l'override di questo comportamento specificando l'azione di criteri da eseguire in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="00ea4-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="00ea4-131">Nella tabella seguente mostra le combinazioni di [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) e [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) i valori supportati.</span><span class="sxs-lookup"><span data-stu-id="00ea4-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="00ea4-132">(Il prefisso FAIL_prefix viene omesso dalla [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori.)</span><span class="sxs-lookup"><span data-stu-id="00ea4-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="00ea4-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="00ea4-133">NonCriticalResource</span></span>|<span data-ttu-id="00ea4-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="00ea4-134">CriticalResource</span></span>|<span data-ttu-id="00ea4-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="00ea4-135">FatalRuntime</span></span>|<span data-ttu-id="00ea4-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="00ea4-136">OrphanedLock</span></span>|<span data-ttu-id="00ea4-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="00ea4-137">StackOverflow</span></span>|<span data-ttu-id="00ea4-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="00ea4-138">AccessViolation</span></span>|<span data-ttu-id="00ea4-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="00ea4-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="00ea4-140">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-140">X</span></span>|<span data-ttu-id="00ea4-141">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-141">X</span></span>||||<span data-ttu-id="00ea4-142">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-142">N/A</span></span>||  
|<span data-ttu-id="00ea4-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="00ea4-143">eThrowException</span></span>|<span data-ttu-id="00ea4-144">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-144">X</span></span>|<span data-ttu-id="00ea4-145">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-145">X</span></span>||||<span data-ttu-id="00ea4-146">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="00ea4-147">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-147">X</span></span>|<span data-ttu-id="00ea4-148">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-148">X</span></span>||||<span data-ttu-id="00ea4-149">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-149">N/A</span></span>|<span data-ttu-id="00ea4-150">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="00ea4-151">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-151">X</span></span>|<span data-ttu-id="00ea4-152">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-152">X</span></span>||||<span data-ttu-id="00ea4-153">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-153">N/A</span></span>|<span data-ttu-id="00ea4-154">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="00ea4-155">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-155">X</span></span>|<span data-ttu-id="00ea4-156">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-156">X</span></span>||<span data-ttu-id="00ea4-157">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-157">X</span></span>||<span data-ttu-id="00ea4-158">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-158">N/A</span></span>|<span data-ttu-id="00ea4-159">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="00ea4-160">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-160">X</span></span>|<span data-ttu-id="00ea4-161">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-161">X</span></span>||<span data-ttu-id="00ea4-162">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-162">X</span></span>|<span data-ttu-id="00ea4-163">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-163">X</span></span>|<span data-ttu-id="00ea4-164">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-164">N/A</span></span>|<span data-ttu-id="00ea4-165">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="00ea4-166">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-166">X</span></span>|<span data-ttu-id="00ea4-167">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-167">X</span></span>||<span data-ttu-id="00ea4-168">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-168">X</span></span>|<span data-ttu-id="00ea4-169">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-169">X</span></span>|<span data-ttu-id="00ea4-170">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-170">N/A</span></span>|<span data-ttu-id="00ea4-171">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-171">X</span></span>|  
|<span data-ttu-id="00ea4-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="00ea4-172">eFastExitProcess</span></span>|<span data-ttu-id="00ea4-173">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-173">X</span></span>|<span data-ttu-id="00ea4-174">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-174">X</span></span>||<span data-ttu-id="00ea4-175">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-175">X</span></span>|<span data-ttu-id="00ea4-176">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-176">X</span></span>|<span data-ttu-id="00ea4-177">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="00ea4-178">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-178">X</span></span>|<span data-ttu-id="00ea4-179">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-179">X</span></span>|<span data-ttu-id="00ea4-180">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-180">X</span></span>|<span data-ttu-id="00ea4-181">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-181">X</span></span>|<span data-ttu-id="00ea4-182">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-182">X</span></span>|<span data-ttu-id="00ea4-183">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="00ea4-184">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-184">X</span></span>|<span data-ttu-id="00ea4-185">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-185">X</span></span>|<span data-ttu-id="00ea4-186">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-186">X</span></span>|<span data-ttu-id="00ea4-187">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-187">X</span></span>|<span data-ttu-id="00ea4-188">X</span><span class="sxs-lookup"><span data-stu-id="00ea4-188">X</span></span>|<span data-ttu-id="00ea4-189">N/D</span><span class="sxs-lookup"><span data-stu-id="00ea4-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="00ea4-190">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00ea4-190">Requirements</span></span>  
 <span data-ttu-id="00ea4-191">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00ea4-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ea4-192">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="00ea4-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00ea4-193">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00ea4-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00ea4-194">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ea4-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ea4-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00ea4-195">See Also</span></span>  
 [<span data-ttu-id="00ea4-196">EClrFailure (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="00ea4-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="00ea4-197">EPolicyAction (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="00ea4-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="00ea4-198">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="00ea4-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="00ea4-199">ICLRPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="00ea4-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
