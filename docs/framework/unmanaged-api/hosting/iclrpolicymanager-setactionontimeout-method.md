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
ms.openlocfilehash: 0b8e7dfbe377e60b548003af10fb11392b514030
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703447"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="a4011-102">Metodo ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="a4011-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="a4011-103">Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica il timeout dell'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="a4011-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4011-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4011-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4011-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4011-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="a4011-106">in Uno dei valori di [EClrOperation](eclroperation-enumeration.md) , che indica l'operazione per la quale specificare l'azione di timeout.</span><span class="sxs-lookup"><span data-stu-id="a4011-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="a4011-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4011-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="a4011-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="a4011-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="a4011-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="a4011-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="a4011-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a4011-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="a4011-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a4011-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="a4011-112">in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione del criterio da intraprendere quando si verifica il timeout dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="a4011-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4011-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a4011-113">Return Value</span></span>  
  
|<span data-ttu-id="a4011-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4011-114">HRESULT</span></span>|<span data-ttu-id="a4011-115">Description</span><span class="sxs-lookup"><span data-stu-id="a4011-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4011-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4011-116">S_OK</span></span>|<span data-ttu-id="a4011-117">`SetActionOnTimeout`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a4011-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="a4011-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4011-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4011-119">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a4011-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4011-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4011-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4011-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a4011-121">The call timed out.</span></span>|  
|<span data-ttu-id="a4011-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4011-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4011-123">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a4011-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4011-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4011-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4011-125">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a4011-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4011-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4011-126">E_FAIL</span></span>|<span data-ttu-id="a4011-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a4011-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4011-128">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a4011-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4011-129">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4011-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a4011-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a4011-130">E_INVALIDARG</span></span>|<span data-ttu-id="a4011-131">Non è possibile impostare un timeout per l'oggetto specificato `operation` oppure è stato fornito un valore non valido per `operation` .</span><span class="sxs-lookup"><span data-stu-id="a4011-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4011-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a4011-132">Remarks</span></span>  
 <span data-ttu-id="a4011-133">Il valore di timeout può essere il timeout predefinito impostato da CLR o un valore specificato dall'host in una chiamata al metodo [ICLRPolicyManager::](iclrpolicymanager-settimeout-method.md) SetValue.</span><span class="sxs-lookup"><span data-stu-id="a4011-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="a4011-134">Non tutti i valori dell'azione del criterio possono essere specificati come comportamento di timeout per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="a4011-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="a4011-135">`SetActionOnTimeout`viene in genere utilizzato solo per l'escalation del comportamento.</span><span class="sxs-lookup"><span data-stu-id="a4011-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="a4011-136">Un host può, ad esempio, specificare che le interruzioni dei thread vengano trasformate in interruzioni di thread rude, ma non è possibile specificare l'opposto.</span><span class="sxs-lookup"><span data-stu-id="a4011-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="a4011-137">Nella tabella seguente vengono descritti i `action` valori validi per i `operation` valori validi.</span><span class="sxs-lookup"><span data-stu-id="a4011-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="a4011-138">Valore per`operation`</span><span class="sxs-lookup"><span data-stu-id="a4011-138">Value for `operation`</span></span>|<span data-ttu-id="a4011-139">Valori validi per`action`</span><span class="sxs-lookup"><span data-stu-id="a4011-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="a4011-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a4011-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="a4011-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="a4011-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="a4011-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="a4011-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="a4011-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a4011-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a4011-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a4011-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a4011-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-145">-   eExitProcess</span></span><br /><span data-ttu-id="a4011-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="a4011-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a4011-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a4011-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a4011-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="a4011-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="a4011-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a4011-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="a4011-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="a4011-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="a4011-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-152">-   eExitProcess</span></span><br /><span data-ttu-id="a4011-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="a4011-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a4011-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a4011-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="a4011-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="a4011-156">OPR_ProcessExit</span></span>|<span data-ttu-id="a4011-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-157">-   eExitProcess</span></span><br /><span data-ttu-id="a4011-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="a4011-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="a4011-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="a4011-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="a4011-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4011-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4011-161">Requirements</span></span>  
 <span data-ttu-id="a4011-162">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4011-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4011-163">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4011-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4011-164">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a4011-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4011-165">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4011-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4011-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4011-166">See also</span></span>

- [<span data-ttu-id="a4011-167">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="a4011-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="a4011-168">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="a4011-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="a4011-169">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a4011-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="a4011-170">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a4011-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
