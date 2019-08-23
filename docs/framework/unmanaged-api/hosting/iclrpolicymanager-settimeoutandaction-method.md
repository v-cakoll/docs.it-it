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
ms.openlocfilehash: 120dbfdc463a7441cce8ca7d87561998a8e28eda
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916957"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="da99a-102">Metodo ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="da99a-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="da99a-103">Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'operazione.</span><span class="sxs-lookup"><span data-stu-id="da99a-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da99a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da99a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da99a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da99a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="da99a-106">in Uno dei valori di [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , che indica l'operazione per la quale impostare il timeout e `action`i criteri.</span><span class="sxs-lookup"><span data-stu-id="da99a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="da99a-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="da99a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="da99a-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="da99a-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="da99a-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="da99a-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="da99a-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="da99a-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="da99a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="da99a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="da99a-112">in Nuovo valore di timeout, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="da99a-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="da99a-113">Il valore infinito non determina `operation` mai il timeout.</span><span class="sxs-lookup"><span data-stu-id="da99a-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="da99a-114">in Uno dei valori di [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , che indica l'azione del criterio che CLR deve eseguire `operation` quando si verifica.</span><span class="sxs-lookup"><span data-stu-id="da99a-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da99a-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da99a-115">Return Value</span></span>  
  
|<span data-ttu-id="da99a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da99a-116">HRESULT</span></span>|<span data-ttu-id="da99a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da99a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da99a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="da99a-118">S_OK</span></span>|<span data-ttu-id="da99a-119">`SetTimeoutAndAction`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="da99a-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="da99a-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da99a-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da99a-121">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="da99a-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da99a-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da99a-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da99a-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="da99a-123">The call timed out.</span></span>|  
|<span data-ttu-id="da99a-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da99a-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da99a-125">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="da99a-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da99a-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da99a-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da99a-127">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="da99a-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da99a-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da99a-128">E_FAIL</span></span>|<span data-ttu-id="da99a-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="da99a-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da99a-130">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="da99a-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da99a-131">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="da99a-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="da99a-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="da99a-132">E_INVALIDARG</span></span>|<span data-ttu-id="da99a-133">Non è possibile impostare un timeout per l' `operation`oggetto specificato oppure è stato fornito un valore `action`non valido per.</span><span class="sxs-lookup"><span data-stu-id="da99a-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da99a-134">Note</span><span class="sxs-lookup"><span data-stu-id="da99a-134">Remarks</span></span>  
 <span data-ttu-id="da99a-135">`SetTimeoutAndAction`Incapsula le funzionalità dei metodi [ICLRPolicyManager:: Setime](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) out e [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) e può essere chiamato al posto di chiamate sequenziali a questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="da99a-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="da99a-136">Non tutti i valori dell'azione del criterio possono essere specificati come comportamento di timeout per le operazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="da99a-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="da99a-137">Vedere le sezioni Note degli argomenti per questi due metodi per i valori validi.</span><span class="sxs-lookup"><span data-stu-id="da99a-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da99a-138">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da99a-138">Requirements</span></span>  
 <span data-ttu-id="da99a-139">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da99a-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da99a-140">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="da99a-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da99a-141">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="da99a-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da99a-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da99a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da99a-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da99a-143">See also</span></span>

- [<span data-ttu-id="da99a-144">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="da99a-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="da99a-145">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="da99a-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="da99a-146">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="da99a-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="da99a-147">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="da99a-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="da99a-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="da99a-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
