---
title: Metodo ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e37d56a321e6529812045e37c4f1929818b38a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433607"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="97b9b-102">Metodo ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="97b9b-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="97b9b-103">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="97b9b-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97b9b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="97b9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97b9b-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="97b9b-106">[in] Un riferimento all'assembly prima della valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="97b9b-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="97b9b-107">[in] Puntatore a un buffer che contiene i dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="97b9b-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="97b9b-108">[in] Le dimensioni del `pbApplicationPolicy` buffer.</span><span class="sxs-lookup"><span data-stu-id="97b9b-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="97b9b-109">[out] Un riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="97b9b-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="97b9b-110">[in, out] Puntatore alla dimensione del buffer di riferimento di identità assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="97b9b-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="97b9b-111">[out] Un puntatore a una combinazione OR logico di [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valori, che indica quali criteri sono stati applicati.</span><span class="sxs-lookup"><span data-stu-id="97b9b-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97b9b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97b9b-112">Return Value</span></span>  
  
|<span data-ttu-id="97b9b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97b9b-113">HRESULT</span></span>|<span data-ttu-id="97b9b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97b9b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97b9b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="97b9b-115">S_OK</span></span>|<span data-ttu-id="97b9b-116">La valutazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="97b9b-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="97b9b-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="97b9b-117">E_INVALIDARG</span></span>|<span data-ttu-id="97b9b-118">Sia `pwzReferenceIdentity` o `pbApplicationPolicy` è un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="97b9b-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="97b9b-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="97b9b-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="97b9b-120">`cbAppPolicySize` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="97b9b-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="97b9b-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97b9b-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97b9b-122">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="97b9b-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97b9b-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97b9b-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97b9b-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="97b9b-124">The call timed out.</span></span>|  
|<span data-ttu-id="97b9b-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97b9b-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97b9b-126">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="97b9b-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97b9b-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97b9b-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97b9b-128">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="97b9b-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97b9b-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97b9b-129">E_FAIL</span></span>|<span data-ttu-id="97b9b-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="97b9b-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97b9b-131">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="97b9b-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97b9b-132">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="97b9b-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97b9b-133">Note</span><span class="sxs-lookup"><span data-stu-id="97b9b-133">Remarks</span></span>  
 <span data-ttu-id="97b9b-134">Il `EvaluatePolicy` metodo consente all'host per influenzare il criterio di associazione per mantenere assieme a host specifici requisiti di versione.</span><span class="sxs-lookup"><span data-stu-id="97b9b-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="97b9b-135">Il motore dei criteri stesso rimane all'interno di CLR.</span><span class="sxs-lookup"><span data-stu-id="97b9b-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b9b-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97b9b-136">Requirements</span></span>  
 <span data-ttu-id="97b9b-137">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97b9b-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b9b-138">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="97b9b-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97b9b-139">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="97b9b-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97b9b-140">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b9b-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b9b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97b9b-141">See Also</span></span>  
 [<span data-ttu-id="97b9b-142">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="97b9b-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
