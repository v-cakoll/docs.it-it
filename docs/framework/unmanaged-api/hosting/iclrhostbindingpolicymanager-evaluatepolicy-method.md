---
title: Metodo ICLRHostBindingPolicyManager::EvaluatePolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.EvaluatePolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14f4db56529fbbb08f8f3d9adde0d4dc7a8ce045
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="afc41-102">Metodo ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="afc41-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="afc41-103">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="afc41-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afc41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afc41-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afc41-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="afc41-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="afc41-106">[in] Un riferimento all'assembly prima della valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="afc41-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="afc41-107">[in] Puntatore a un buffer che contiene i dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="afc41-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="afc41-108">[in] Le dimensioni del `pbApplicationPolicy` buffer.</span><span class="sxs-lookup"><span data-stu-id="afc41-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="afc41-109">[out] Un riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="afc41-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="afc41-110">[in, out] Puntatore alla dimensione del buffer di riferimento di identità assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="afc41-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="afc41-111">[out] Un puntatore a una combinazione OR logico di [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valori, che indica quali criteri sono stati applicati.</span><span class="sxs-lookup"><span data-stu-id="afc41-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afc41-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="afc41-112">Return Value</span></span>  
  
|<span data-ttu-id="afc41-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="afc41-113">HRESULT</span></span>|<span data-ttu-id="afc41-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afc41-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afc41-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="afc41-115">S_OK</span></span>|<span data-ttu-id="afc41-116">La valutazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="afc41-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="afc41-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="afc41-117">E_INVALIDARG</span></span>|<span data-ttu-id="afc41-118">Sia `pwzReferenceIdentity` o `pbApplicationPolicy` è un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="afc41-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="afc41-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="afc41-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="afc41-120">`cbAppPolicySize`è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="afc41-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="afc41-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="afc41-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="afc41-122">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="afc41-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="afc41-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="afc41-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="afc41-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="afc41-124">The call timed out.</span></span>|  
|<span data-ttu-id="afc41-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="afc41-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="afc41-126">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="afc41-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="afc41-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="afc41-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="afc41-128">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="afc41-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="afc41-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="afc41-129">E_FAIL</span></span>|<span data-ttu-id="afc41-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="afc41-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="afc41-131">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="afc41-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="afc41-132">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="afc41-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afc41-133">Note</span><span class="sxs-lookup"><span data-stu-id="afc41-133">Remarks</span></span>  
 <span data-ttu-id="afc41-134">Il `EvaluatePolicy` metodo consente all'host per influenzare il criterio di associazione per mantenere assieme a host specifici requisiti di versione.</span><span class="sxs-lookup"><span data-stu-id="afc41-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="afc41-135">Il motore dei criteri stesso rimane all'interno di CLR.</span><span class="sxs-lookup"><span data-stu-id="afc41-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afc41-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afc41-136">Requirements</span></span>  
 <span data-ttu-id="afc41-137">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afc41-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afc41-138">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="afc41-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afc41-139">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afc41-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afc41-140">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afc41-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc41-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afc41-141">See Also</span></span>  
 [<span data-ttu-id="afc41-142">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="afc41-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
