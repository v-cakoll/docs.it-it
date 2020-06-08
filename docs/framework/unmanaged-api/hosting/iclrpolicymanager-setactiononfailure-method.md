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
ms.openlocfilehash: 727cd82226b9a59c4879ffea5e87f93dd5fe38c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504108"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="0c5d7-102">Metodo ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="0c5d7-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="0c5d7-103">Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c5d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c5d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c5d7-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="0c5d7-106">in Uno dei valori di [EClrFailure](eclrfailure-enumeration.md) , che indica il tipo di errore per il quale eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="0c5d7-107">in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione da intraprendere quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="0c5d7-108">Per un elenco dei valori supportati, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c5d7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c5d7-109">Return Value</span></span>  
  
|<span data-ttu-id="0c5d7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c5d7-110">HRESULT</span></span>|<span data-ttu-id="0c5d7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c5d7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c5d7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c5d7-112">S_OK</span></span>|<span data-ttu-id="0c5d7-113">`SetActionOnFailure`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="0c5d7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c5d7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c5d7-115">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c5d7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c5d7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c5d7-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-117">The call timed out.</span></span>|  
|<span data-ttu-id="0c5d7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c5d7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c5d7-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c5d7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c5d7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c5d7-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c5d7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c5d7-122">E_FAIL</span></span>|<span data-ttu-id="0c5d7-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c5d7-124">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c5d7-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c5d7-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c5d7-126">E_INVALIDARG</span></span>|<span data-ttu-id="0c5d7-127">Non è possibile impostare un'azione del criterio per l'operazione specificata oppure è stata specificata un'azione del criterio non valida per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c5d7-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c5d7-128">Remarks</span></span>  
 <span data-ttu-id="0c5d7-129">Per impostazione predefinita, CLR genera un'eccezione quando non riesce ad allocare una risorsa, ad esempio la memoria.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="0c5d7-130">`SetActionOnFailure`consente all'host di eseguire l'override di questo comportamento specificando l'azione del criterio da eseguire quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="0c5d7-131">Nella tabella seguente vengono illustrate le combinazioni di valori [EClrFailure](eclrfailure-enumeration.md) e [EPolicyAction](epolicyaction-enumeration.md) supportati.</span><span class="sxs-lookup"><span data-stu-id="0c5d7-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="0c5d7-132">Il prefisso FAIL_ viene omesso dai valori [EClrFailure](eclrfailure-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0c5d7-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="0c5d7-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="0c5d7-133">NonCriticalResource</span></span>|<span data-ttu-id="0c5d7-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="0c5d7-134">CriticalResource</span></span>|<span data-ttu-id="0c5d7-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="0c5d7-135">FatalRuntime</span></span>|<span data-ttu-id="0c5d7-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="0c5d7-136">OrphanedLock</span></span>|<span data-ttu-id="0c5d7-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="0c5d7-137">StackOverflow</span></span>|<span data-ttu-id="0c5d7-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="0c5d7-138">AccessViolation</span></span>|<span data-ttu-id="0c5d7-139">Codecontract</span><span class="sxs-lookup"><span data-stu-id="0c5d7-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="0c5d7-140">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-140">X</span></span>|<span data-ttu-id="0c5d7-141">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-141">X</span></span>||||<span data-ttu-id="0c5d7-142">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-142">N/A</span></span>||  
|<span data-ttu-id="0c5d7-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="0c5d7-143">eThrowException</span></span>|<span data-ttu-id="0c5d7-144">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-144">X</span></span>|<span data-ttu-id="0c5d7-145">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-145">X</span></span>||||<span data-ttu-id="0c5d7-146">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="0c5d7-147">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-147">X</span></span>|<span data-ttu-id="0c5d7-148">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-148">X</span></span>||||<span data-ttu-id="0c5d7-149">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-149">N/A</span></span>|<span data-ttu-id="0c5d7-150">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="0c5d7-151">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-151">X</span></span>|<span data-ttu-id="0c5d7-152">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-152">X</span></span>||||<span data-ttu-id="0c5d7-153">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-153">N/A</span></span>|<span data-ttu-id="0c5d7-154">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="0c5d7-155">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-155">X</span></span>|<span data-ttu-id="0c5d7-156">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-156">X</span></span>||<span data-ttu-id="0c5d7-157">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-157">X</span></span>||<span data-ttu-id="0c5d7-158">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-158">N/A</span></span>|<span data-ttu-id="0c5d7-159">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="0c5d7-160">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-160">X</span></span>|<span data-ttu-id="0c5d7-161">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-161">X</span></span>||<span data-ttu-id="0c5d7-162">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-162">X</span></span>|<span data-ttu-id="0c5d7-163">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-163">X</span></span>|<span data-ttu-id="0c5d7-164">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-164">N/A</span></span>|<span data-ttu-id="0c5d7-165">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="0c5d7-166">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-166">X</span></span>|<span data-ttu-id="0c5d7-167">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-167">X</span></span>||<span data-ttu-id="0c5d7-168">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-168">X</span></span>|<span data-ttu-id="0c5d7-169">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-169">X</span></span>|<span data-ttu-id="0c5d7-170">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-170">N/A</span></span>|<span data-ttu-id="0c5d7-171">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-171">X</span></span>|  
|<span data-ttu-id="0c5d7-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="0c5d7-172">eFastExitProcess</span></span>|<span data-ttu-id="0c5d7-173">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-173">X</span></span>|<span data-ttu-id="0c5d7-174">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-174">X</span></span>||<span data-ttu-id="0c5d7-175">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-175">X</span></span>|<span data-ttu-id="0c5d7-176">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-176">X</span></span>|<span data-ttu-id="0c5d7-177">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="0c5d7-178">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-178">X</span></span>|<span data-ttu-id="0c5d7-179">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-179">X</span></span>|<span data-ttu-id="0c5d7-180">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-180">X</span></span>|<span data-ttu-id="0c5d7-181">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-181">X</span></span>|<span data-ttu-id="0c5d7-182">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-182">X</span></span>|<span data-ttu-id="0c5d7-183">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="0c5d7-184">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-184">X</span></span>|<span data-ttu-id="0c5d7-185">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-185">X</span></span>|<span data-ttu-id="0c5d7-186">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-186">X</span></span>|<span data-ttu-id="0c5d7-187">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-187">X</span></span>|<span data-ttu-id="0c5d7-188">X</span><span class="sxs-lookup"><span data-stu-id="0c5d7-188">X</span></span>|<span data-ttu-id="0c5d7-189">N/D</span><span class="sxs-lookup"><span data-stu-id="0c5d7-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="0c5d7-190">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c5d7-190">Requirements</span></span>  
 <span data-ttu-id="0c5d7-191">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c5d7-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5d7-192">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0c5d7-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c5d7-193">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c5d7-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c5d7-194">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5d7-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5d7-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5d7-195">See also</span></span>

- [<span data-ttu-id="0c5d7-196">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="0c5d7-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="0c5d7-197">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="0c5d7-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="0c5d7-198">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0c5d7-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0c5d7-199">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0c5d7-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
