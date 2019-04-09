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
ms.openlocfilehash: ad7856a9376880f867e35f1e63bc2cac1ca216fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130154"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="3e40e-102">Metodo ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="3e40e-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="3e40e-103">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="3e40e-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e40e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e40e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3e40e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e40e-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="3e40e-106">[in] Un riferimento all'assembly prima della valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3e40e-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="3e40e-107">[in] Puntatore a un buffer che contiene i dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3e40e-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="3e40e-108">[in] Le dimensioni del `pbApplicationPolicy` buffer.</span><span class="sxs-lookup"><span data-stu-id="3e40e-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="3e40e-109">[out] Un riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3e40e-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="3e40e-110">[in, out] Puntatore alla dimensione del buffer di riferimento di assembly identità dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3e40e-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="3e40e-111">[out] Un puntatore a una combinazione OR logico dei [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valori, che indica quali criteri sono stati applicati.</span><span class="sxs-lookup"><span data-stu-id="3e40e-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e40e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e40e-112">Return Value</span></span>  
  
|<span data-ttu-id="3e40e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e40e-113">HRESULT</span></span>|<span data-ttu-id="3e40e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e40e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e40e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e40e-115">S_OK</span></span>|<span data-ttu-id="3e40e-116">La valutazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e40e-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="3e40e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3e40e-117">E_INVALIDARG</span></span>|<span data-ttu-id="3e40e-118">Sia `pwzReferenceIdentity` o `pbApplicationPolicy` è un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="3e40e-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="3e40e-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3e40e-119">ERROR_INSUFFICIENT_BUFFER</span></span>|`cbAppPolicySize` <span data-ttu-id="3e40e-120">è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="3e40e-120">is too small.</span></span>|  
|<span data-ttu-id="3e40e-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e40e-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e40e-122">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e40e-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e40e-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e40e-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e40e-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e40e-124">The call timed out.</span></span>|  
|<span data-ttu-id="3e40e-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e40e-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e40e-126">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3e40e-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e40e-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e40e-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e40e-128">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e40e-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e40e-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e40e-129">E_FAIL</span></span>|<span data-ttu-id="3e40e-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3e40e-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e40e-131">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3e40e-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e40e-132">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e40e-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e40e-133">Note</span><span class="sxs-lookup"><span data-stu-id="3e40e-133">Remarks</span></span>  
 <span data-ttu-id="3e40e-134">Il `EvaluatePolicy` metodo consente all'host per influenzare i criteri di associazione degli assembly specifici per l'host di mantenere i requisiti di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="3e40e-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="3e40e-135">Il motore dei criteri stesso rimane all'interno di CLR.</span><span class="sxs-lookup"><span data-stu-id="3e40e-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e40e-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e40e-136">Requirements</span></span>  
 <span data-ttu-id="3e40e-137">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e40e-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e40e-138">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e40e-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e40e-139">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3e40e-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3e40e-140">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3e40e-140">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e40e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e40e-141">See also</span></span>

- [<span data-ttu-id="3e40e-142">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3e40e-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
