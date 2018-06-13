---
title: Metodo ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc1d16a2d57fea27c1c26fc55fbbfa9b74c25495
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435838"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="766a3-102">Metodo ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="766a3-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="766a3-103">Specifica l'azione di criteri che Common language runtime (CLR) deve eseguire quando il timeout dell'operazione specificato.</span><span class="sxs-lookup"><span data-stu-id="766a3-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="766a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="766a3-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="766a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="766a3-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="766a3-106">[in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'operazione per cui si desidera specificare l'azione di timeout.</span><span class="sxs-lookup"><span data-stu-id="766a3-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="766a3-107">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="766a3-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="766a3-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="766a3-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="766a3-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="766a3-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="766a3-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="766a3-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="766a3-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="766a3-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="766a3-112">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione dei criteri da eseguire quando il timeout dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="766a3-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="766a3-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="766a3-113">Return Value</span></span>  
  
|<span data-ttu-id="766a3-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="766a3-114">HRESULT</span></span>|<span data-ttu-id="766a3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="766a3-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="766a3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="766a3-116">S_OK</span></span>|<span data-ttu-id="766a3-117">`SetActionOnTimeout` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="766a3-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="766a3-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="766a3-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="766a3-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="766a3-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="766a3-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="766a3-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="766a3-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="766a3-121">The call timed out.</span></span>|  
|<span data-ttu-id="766a3-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="766a3-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="766a3-123">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="766a3-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="766a3-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="766a3-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="766a3-125">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="766a3-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="766a3-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="766a3-126">E_FAIL</span></span>|<span data-ttu-id="766a3-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="766a3-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="766a3-128">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="766a3-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="766a3-129">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="766a3-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="766a3-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="766a3-130">E_INVALIDARG</span></span>|<span data-ttu-id="766a3-131">Non è possibile impostare un timeout per l'oggetto specificato `operation`, o è stato specificato un valore non valido per `operation`.</span><span class="sxs-lookup"><span data-stu-id="766a3-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="766a3-132">Note</span><span class="sxs-lookup"><span data-stu-id="766a3-132">Remarks</span></span>  
 <span data-ttu-id="766a3-133">Il valore di timeout può essere il timeout predefinito in CLR, o un valore specificato dall'host in una chiamata al [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="766a3-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="766a3-134">Non tutti i valori di azione criteri possono essere specificati come il comportamento di timeout per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="766a3-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="766a3-135">`SetActionOnTimeout` è in genere usati solo per l'escalation di comportamento.</span><span class="sxs-lookup"><span data-stu-id="766a3-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="766a3-136">Ad esempio, un host può specificare che le interruzioni di thread deve essere trasformata nelle interruzioni di thread, ma non è possibile specificare l'opposto.</span><span class="sxs-lookup"><span data-stu-id="766a3-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="766a3-137">La tabella seguente descrive validi `action` i valori del parametro valido `operation` valori.</span><span class="sxs-lookup"><span data-stu-id="766a3-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="766a3-138">Valore per `operation`</span><span class="sxs-lookup"><span data-stu-id="766a3-138">Value for `operation`</span></span>|<span data-ttu-id="766a3-139">Valori validi per `action`</span><span class="sxs-lookup"><span data-stu-id="766a3-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="766a3-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="766a3-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="766a3-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="766a3-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="766a3-142">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="766a3-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="766a3-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="766a3-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="766a3-144">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="766a3-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="766a3-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-145">-   eExitProcess</span></span><br /><span data-ttu-id="766a3-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="766a3-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="766a3-148">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="766a3-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="766a3-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="766a3-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="766a3-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="766a3-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="766a3-151">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="766a3-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="766a3-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-152">-   eExitProcess</span></span><br /><span data-ttu-id="766a3-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="766a3-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="766a3-155">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="766a3-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="766a3-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="766a3-156">OPR_ProcessExit</span></span>|<span data-ttu-id="766a3-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-157">-   eExitProcess</span></span><br /><span data-ttu-id="766a3-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="766a3-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="766a3-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="766a3-160">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="766a3-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="766a3-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="766a3-161">Requirements</span></span>  
 <span data-ttu-id="766a3-162">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="766a3-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="766a3-163">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="766a3-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="766a3-164">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="766a3-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="766a3-165">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="766a3-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="766a3-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="766a3-166">See Also</span></span>  
 [<span data-ttu-id="766a3-167">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="766a3-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="766a3-168">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="766a3-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="766a3-169">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="766a3-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="766a3-170">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="766a3-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
