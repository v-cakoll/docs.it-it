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
ms.openlocfilehash: c375fdffacccb27c20878c4e6adef9dd947148e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435524"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="8c335-102">Metodo ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="8c335-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="8c335-103">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8c335-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c335-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c335-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c335-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c335-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="8c335-106">[in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'operazione per cui impostare il timeout e il criterio `action`.</span><span class="sxs-lookup"><span data-stu-id="8c335-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="8c335-107">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="8c335-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="8c335-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="8c335-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="8c335-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="8c335-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="8c335-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8c335-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="8c335-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8c335-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="8c335-112">[in] Il nuovo valore di timeout, espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="8c335-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="8c335-113">Un valore di infinito, `operation` mai il timeout.</span><span class="sxs-lookup"><span data-stu-id="8c335-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="8c335-114">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione dei criteri che dovrebbe trascorrere quando CLR `operation` si verifica.</span><span class="sxs-lookup"><span data-stu-id="8c335-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c335-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c335-115">Return Value</span></span>  
  
|<span data-ttu-id="8c335-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c335-116">HRESULT</span></span>|<span data-ttu-id="8c335-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c335-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c335-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c335-118">S_OK</span></span>|<span data-ttu-id="8c335-119">`SetTimeoutAndAction` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8c335-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="8c335-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c335-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c335-121">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c335-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c335-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c335-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c335-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c335-123">The call timed out.</span></span>|  
|<span data-ttu-id="8c335-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c335-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c335-125">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="8c335-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c335-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c335-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c335-127">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8c335-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c335-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c335-128">E_FAIL</span></span>|<span data-ttu-id="8c335-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8c335-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c335-130">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8c335-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c335-131">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c335-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8c335-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8c335-132">E_INVALIDARG</span></span>|<span data-ttu-id="8c335-133">Non è possibile impostare un timeout per l'oggetto specificato `operation`, o è stato specificato un valore non valido per `action`.</span><span class="sxs-lookup"><span data-stu-id="8c335-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c335-134">Note</span><span class="sxs-lookup"><span data-stu-id="8c335-134">Remarks</span></span>  
 <span data-ttu-id="8c335-135">`SetTimeoutAndAction` incapsula le funzionalità del [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) e [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) metodi e può essere chiamato al posto di chiamate sequenziali di questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="8c335-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c335-136">Non tutti i valori di azione criteri possono essere specificati come il comportamento di timeout per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="8c335-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="8c335-137">Vedere la sezione Note degli argomenti di questi due metodi per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="8c335-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c335-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c335-138">Requirements</span></span>  
 <span data-ttu-id="8c335-139">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c335-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c335-140">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8c335-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c335-141">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8c335-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c335-142">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c335-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c335-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c335-143">See Also</span></span>  
 [<span data-ttu-id="8c335-144">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="8c335-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="8c335-145">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="8c335-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="8c335-146">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="8c335-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="8c335-147">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="8c335-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [<span data-ttu-id="8c335-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="8c335-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
