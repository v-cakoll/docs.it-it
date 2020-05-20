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
ms.openlocfilehash: f72a66354bfc907dab7ebc24de515bdfb20ddfb2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703590"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="06a88-102">Metodo ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="06a88-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="06a88-103">Valuta i criteri di associazione per conto dell'host.</span><span class="sxs-lookup"><span data-stu-id="06a88-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06a88-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06a88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06a88-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="06a88-106">in Riferimento all'assembly prima della valutazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06a88-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="06a88-107">in Puntatore a un buffer che contiene i dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06a88-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="06a88-108">in Dimensioni del `pbApplicationPolicy` buffer.</span><span class="sxs-lookup"><span data-stu-id="06a88-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="06a88-109">out Riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06a88-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="06a88-110">[in, out] Puntatore alla dimensione del buffer del riferimento all'identità dell'assembly dopo la valutazione dei nuovi dati dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06a88-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="06a88-111">out Puntatore a una combinazione logica o di valori [EBindPolicyLevels](ebindpolicylevels-enumeration.md) , che indica i criteri applicati.</span><span class="sxs-lookup"><span data-stu-id="06a88-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06a88-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="06a88-112">Return Value</span></span>  
  
|<span data-ttu-id="06a88-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06a88-113">HRESULT</span></span>|<span data-ttu-id="06a88-114">Description</span><span class="sxs-lookup"><span data-stu-id="06a88-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06a88-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="06a88-115">S_OK</span></span>|<span data-ttu-id="06a88-116">La valutazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="06a88-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="06a88-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="06a88-117">E_INVALIDARG</span></span>|<span data-ttu-id="06a88-118">`pwzReferenceIdentity`O `pbApplicationPolicy` è un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="06a88-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="06a88-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="06a88-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="06a88-120">Il valore di `cbAppPolicySize` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="06a88-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="06a88-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06a88-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06a88-122">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="06a88-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06a88-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06a88-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06a88-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="06a88-124">The call timed out.</span></span>|  
|<span data-ttu-id="06a88-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06a88-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06a88-126">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="06a88-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06a88-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06a88-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06a88-128">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="06a88-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06a88-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06a88-129">E_FAIL</span></span>|<span data-ttu-id="06a88-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="06a88-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06a88-131">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="06a88-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06a88-132">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="06a88-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06a88-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="06a88-133">Remarks</span></span>  
 <span data-ttu-id="06a88-134">Il `EvaluatePolicy` metodo consente all'host di influenzare i criteri di associazione per gestire i requisiti di controllo delle versioni degli assembly specifici dell'host.</span><span class="sxs-lookup"><span data-stu-id="06a88-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="06a88-135">Il motore dei criteri rimane all'interno di CLR.</span><span class="sxs-lookup"><span data-stu-id="06a88-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a88-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06a88-136">Requirements</span></span>  
 <span data-ttu-id="06a88-137">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06a88-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a88-138">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="06a88-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06a88-139">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06a88-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06a88-140">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a88-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a88-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a88-141">See also</span></span>

- [<span data-ttu-id="06a88-142">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="06a88-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
