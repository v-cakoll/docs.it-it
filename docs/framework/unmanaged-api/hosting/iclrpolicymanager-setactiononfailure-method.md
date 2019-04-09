---
title: Metodo ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117430"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="5e4ef-102">Metodo ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="5e4ef-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="5e4ef-103">Specifica l'azione di criteri che Common language runtime (CLR) deve essere intrapresa quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e4ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e4ef-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e4ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e4ef-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="5e4ef-106">[in] Uno dei [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore per il quale eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="5e4ef-107">[in] Uno dei [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione da intraprendere quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="5e4ef-108">Per un elenco di valori supportati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e4ef-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5e4ef-109">Return Value</span></span>  
  
|<span data-ttu-id="5e4ef-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e4ef-110">HRESULT</span></span>|<span data-ttu-id="5e4ef-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e4ef-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e4ef-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e4ef-112">S_OK</span></span>|`SetActionOnFailure` <span data-ttu-id="5e4ef-113">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-113">returned successfully.</span></span>|  
|<span data-ttu-id="5e4ef-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e4ef-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e4ef-115">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e4ef-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e4ef-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e4ef-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-117">The call timed out.</span></span>|  
|<span data-ttu-id="5e4ef-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e4ef-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e4ef-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e4ef-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e4ef-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e4ef-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e4ef-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e4ef-122">E_FAIL</span></span>|<span data-ttu-id="5e4ef-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e4ef-124">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e4ef-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e4ef-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5e4ef-126">E_INVALIDARG</span></span>|<span data-ttu-id="5e4ef-127">Un'azione di criteri non può essere impostata per l'operazione specificata o è stata specificata un'azione di criteri non validi per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e4ef-128">Note</span><span class="sxs-lookup"><span data-stu-id="5e4ef-128">Remarks</span></span>  
 <span data-ttu-id="5e4ef-129">Per impostazione predefinita, il CLR genera un'eccezione quando non riesce ad allocare una risorsa, ad esempio memoria.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> `SetActionOnFailure` <span data-ttu-id="5e4ef-130">consente all'host eseguire l'override di questo comportamento specificando l'azione di criteri da eseguire in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-130">allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="5e4ef-131">Nella tabella seguente illustra le combinazioni di [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) e [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) i valori supportati.</span><span class="sxs-lookup"><span data-stu-id="5e4ef-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="5e4ef-132">(Il prefisso FAIL_prefix viene omesso dallo [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori.)</span><span class="sxs-lookup"><span data-stu-id="5e4ef-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="5e4ef-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="5e4ef-133">NonCriticalResource</span></span>|<span data-ttu-id="5e4ef-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="5e4ef-134">CriticalResource</span></span>|<span data-ttu-id="5e4ef-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="5e4ef-135">FatalRuntime</span></span>|<span data-ttu-id="5e4ef-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="5e4ef-136">OrphanedLock</span></span>|<span data-ttu-id="5e4ef-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="5e4ef-137">StackOverflow</span></span>|<span data-ttu-id="5e4ef-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="5e4ef-138">AccessViolation</span></span>|<span data-ttu-id="5e4ef-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="5e4ef-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="5e4ef-140">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-140">X</span></span>|<span data-ttu-id="5e4ef-141">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-141">X</span></span>||||<span data-ttu-id="5e4ef-142">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-142">N/A</span></span>||  
|<span data-ttu-id="5e4ef-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="5e4ef-143">eThrowException</span></span>|<span data-ttu-id="5e4ef-144">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-144">X</span></span>|<span data-ttu-id="5e4ef-145">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-145">X</span></span>||||<span data-ttu-id="5e4ef-146">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="5e4ef-147">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-147">X</span></span>|<span data-ttu-id="5e4ef-148">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-148">X</span></span>||||<span data-ttu-id="5e4ef-149">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-149">N/A</span></span>|<span data-ttu-id="5e4ef-150">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="5e4ef-151">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-151">X</span></span>|<span data-ttu-id="5e4ef-152">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-152">X</span></span>||||<span data-ttu-id="5e4ef-153">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-153">N/A</span></span>|<span data-ttu-id="5e4ef-154">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="5e4ef-155">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-155">X</span></span>|<span data-ttu-id="5e4ef-156">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-156">X</span></span>||<span data-ttu-id="5e4ef-157">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-157">X</span></span>||<span data-ttu-id="5e4ef-158">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-158">N/A</span></span>|<span data-ttu-id="5e4ef-159">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="5e4ef-160">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-160">X</span></span>|<span data-ttu-id="5e4ef-161">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-161">X</span></span>||<span data-ttu-id="5e4ef-162">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-162">X</span></span>|<span data-ttu-id="5e4ef-163">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-163">X</span></span>|<span data-ttu-id="5e4ef-164">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-164">N/A</span></span>|<span data-ttu-id="5e4ef-165">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="5e4ef-166">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-166">X</span></span>|<span data-ttu-id="5e4ef-167">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-167">X</span></span>||<span data-ttu-id="5e4ef-168">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-168">X</span></span>|<span data-ttu-id="5e4ef-169">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-169">X</span></span>|<span data-ttu-id="5e4ef-170">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-170">N/A</span></span>|<span data-ttu-id="5e4ef-171">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-171">X</span></span>|  
|<span data-ttu-id="5e4ef-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="5e4ef-172">eFastExitProcess</span></span>|<span data-ttu-id="5e4ef-173">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-173">X</span></span>|<span data-ttu-id="5e4ef-174">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-174">X</span></span>||<span data-ttu-id="5e4ef-175">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-175">X</span></span>|<span data-ttu-id="5e4ef-176">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-176">X</span></span>|<span data-ttu-id="5e4ef-177">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="5e4ef-178">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-178">X</span></span>|<span data-ttu-id="5e4ef-179">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-179">X</span></span>|<span data-ttu-id="5e4ef-180">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-180">X</span></span>|<span data-ttu-id="5e4ef-181">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-181">X</span></span>|<span data-ttu-id="5e4ef-182">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-182">X</span></span>|<span data-ttu-id="5e4ef-183">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="5e4ef-184">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-184">X</span></span>|<span data-ttu-id="5e4ef-185">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-185">X</span></span>|<span data-ttu-id="5e4ef-186">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-186">X</span></span>|<span data-ttu-id="5e4ef-187">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-187">X</span></span>|<span data-ttu-id="5e4ef-188">x</span><span class="sxs-lookup"><span data-stu-id="5e4ef-188">X</span></span>|<span data-ttu-id="5e4ef-189">N/D</span><span class="sxs-lookup"><span data-stu-id="5e4ef-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="5e4ef-190">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e4ef-190">Requirements</span></span>  
 <span data-ttu-id="5e4ef-191">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e4ef-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e4ef-192">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e4ef-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e4ef-193">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5e4ef-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5e4ef-194">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5e4ef-194">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e4ef-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e4ef-195">See also</span></span>

- [<span data-ttu-id="5e4ef-196">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="5e4ef-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="5e4ef-197">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="5e4ef-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="5e4ef-198">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5e4ef-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5e4ef-199">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="5e4ef-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
