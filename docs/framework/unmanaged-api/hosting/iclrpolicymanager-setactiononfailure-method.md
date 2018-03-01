---
title: Metodo ICLRPolicyManager::SetActionOnFailure
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
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4440b36485ed900b5e64adcead2525dbb7d5206e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="f98f2-102">Metodo ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="f98f2-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="f98f2-103">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="f98f2-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f98f2-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f98f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f98f2-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="f98f2-106">[in] Uno del [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore per il quale eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="f98f2-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="f98f2-107">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione da intraprendere quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="f98f2-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="f98f2-108">Per un elenco di valori supportati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="f98f2-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f98f2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f98f2-109">Return Value</span></span>  
  
|<span data-ttu-id="f98f2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f98f2-110">HRESULT</span></span>|<span data-ttu-id="f98f2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f98f2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f98f2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f98f2-112">S_OK</span></span>|<span data-ttu-id="f98f2-113">`SetActionOnFailure`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f98f2-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="f98f2-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f98f2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f98f2-115">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f98f2-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f98f2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f98f2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f98f2-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f98f2-117">The call timed out.</span></span>|  
|<span data-ttu-id="f98f2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f98f2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f98f2-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="f98f2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f98f2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f98f2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f98f2-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f98f2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f98f2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f98f2-122">E_FAIL</span></span>|<span data-ttu-id="f98f2-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f98f2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f98f2-124">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f98f2-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f98f2-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f98f2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f98f2-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f98f2-126">E_INVALIDARG</span></span>|<span data-ttu-id="f98f2-127">Impossibile impostare un'azione di criteri per l'operazione specificata o è stata specificata un'azione di criteri non validi per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f98f2-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f98f2-128">Note</span><span class="sxs-lookup"><span data-stu-id="f98f2-128">Remarks</span></span>  
 <span data-ttu-id="f98f2-129">Per impostazione predefinita, CLR genera un'eccezione quando non è possibile assegnare una risorsa, ad esempio la memoria.</span><span class="sxs-lookup"><span data-stu-id="f98f2-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="f98f2-130">`SetActionOnFailure`consente all'host di eseguire l'override di questo comportamento specificando l'azione di criteri da eseguire in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="f98f2-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="f98f2-131">Nella tabella seguente mostra le combinazioni di [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) e [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) i valori supportati.</span><span class="sxs-lookup"><span data-stu-id="f98f2-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="f98f2-132">(Il prefisso FAIL_prefix viene omesso dalla [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori.)</span><span class="sxs-lookup"><span data-stu-id="f98f2-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="f98f2-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="f98f2-133">NonCriticalResource</span></span>|<span data-ttu-id="f98f2-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="f98f2-134">CriticalResource</span></span>|<span data-ttu-id="f98f2-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="f98f2-135">FatalRuntime</span></span>|<span data-ttu-id="f98f2-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="f98f2-136">OrphanedLock</span></span>|<span data-ttu-id="f98f2-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="f98f2-137">StackOverflow</span></span>|<span data-ttu-id="f98f2-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="f98f2-138">AccessViolation</span></span>|<span data-ttu-id="f98f2-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="f98f2-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="f98f2-140">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-140">X</span></span>|<span data-ttu-id="f98f2-141">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-141">X</span></span>||||<span data-ttu-id="f98f2-142">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-142">N/A</span></span>||  
|<span data-ttu-id="f98f2-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="f98f2-143">eThrowException</span></span>|<span data-ttu-id="f98f2-144">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-144">X</span></span>|<span data-ttu-id="f98f2-145">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-145">X</span></span>||||<span data-ttu-id="f98f2-146">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="f98f2-147">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-147">X</span></span>|<span data-ttu-id="f98f2-148">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-148">X</span></span>||||<span data-ttu-id="f98f2-149">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-149">N/A</span></span>|<span data-ttu-id="f98f2-150">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="f98f2-151">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-151">X</span></span>|<span data-ttu-id="f98f2-152">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-152">X</span></span>||||<span data-ttu-id="f98f2-153">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-153">N/A</span></span>|<span data-ttu-id="f98f2-154">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="f98f2-155">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-155">X</span></span>|<span data-ttu-id="f98f2-156">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-156">X</span></span>||<span data-ttu-id="f98f2-157">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-157">X</span></span>||<span data-ttu-id="f98f2-158">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-158">N/A</span></span>|<span data-ttu-id="f98f2-159">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="f98f2-160">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-160">X</span></span>|<span data-ttu-id="f98f2-161">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-161">X</span></span>||<span data-ttu-id="f98f2-162">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-162">X</span></span>|<span data-ttu-id="f98f2-163">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-163">X</span></span>|<span data-ttu-id="f98f2-164">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-164">N/A</span></span>|<span data-ttu-id="f98f2-165">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="f98f2-166">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-166">X</span></span>|<span data-ttu-id="f98f2-167">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-167">X</span></span>||<span data-ttu-id="f98f2-168">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-168">X</span></span>|<span data-ttu-id="f98f2-169">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-169">X</span></span>|<span data-ttu-id="f98f2-170">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-170">N/A</span></span>|<span data-ttu-id="f98f2-171">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-171">X</span></span>|  
|<span data-ttu-id="f98f2-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="f98f2-172">eFastExitProcess</span></span>|<span data-ttu-id="f98f2-173">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-173">X</span></span>|<span data-ttu-id="f98f2-174">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-174">X</span></span>||<span data-ttu-id="f98f2-175">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-175">X</span></span>|<span data-ttu-id="f98f2-176">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-176">X</span></span>|<span data-ttu-id="f98f2-177">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="f98f2-178">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-178">X</span></span>|<span data-ttu-id="f98f2-179">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-179">X</span></span>|<span data-ttu-id="f98f2-180">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-180">X</span></span>|<span data-ttu-id="f98f2-181">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-181">X</span></span>|<span data-ttu-id="f98f2-182">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-182">X</span></span>|<span data-ttu-id="f98f2-183">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="f98f2-184">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-184">X</span></span>|<span data-ttu-id="f98f2-185">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-185">X</span></span>|<span data-ttu-id="f98f2-186">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-186">X</span></span>|<span data-ttu-id="f98f2-187">X</span><span class="sxs-lookup"><span data-stu-id="f98f2-187">X</span></span>|<span data-ttu-id="f98f2-188">x</span><span class="sxs-lookup"><span data-stu-id="f98f2-188">X</span></span>|<span data-ttu-id="f98f2-189">N/D</span><span class="sxs-lookup"><span data-stu-id="f98f2-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="f98f2-190">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f98f2-190">Requirements</span></span>  
 <span data-ttu-id="f98f2-191">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f98f2-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f98f2-192">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f98f2-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f98f2-193">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f98f2-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f98f2-194">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f98f2-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98f2-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f98f2-195">See Also</span></span>  
 [<span data-ttu-id="f98f2-196">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="f98f2-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="f98f2-197">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="f98f2-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="f98f2-198">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f98f2-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f98f2-199">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f98f2-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
