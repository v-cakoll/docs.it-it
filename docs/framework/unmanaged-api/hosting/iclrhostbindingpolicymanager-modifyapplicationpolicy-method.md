---
title: Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a221b286ada97c3c03387556cb30ee6ddd2c453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436254"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="a68dd-102">Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a68dd-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="a68dd-103">Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.</span><span class="sxs-lookup"><span data-stu-id="a68dd-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a68dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a68dd-104">Syntax</span></span>  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a68dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a68dd-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="a68dd-106">[in] L'identità dell'assembly da modificare.</span><span class="sxs-lookup"><span data-stu-id="a68dd-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="a68dd-107">[in] La nuova identità dell'assembly modificato.</span><span class="sxs-lookup"><span data-stu-id="a68dd-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="a68dd-108">[in] Puntatore a un buffer che contiene i dati dei criteri di associazione per l'assembly da modificare.</span><span class="sxs-lookup"><span data-stu-id="a68dd-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="a68dd-109">[in] Le dimensioni dei criteri di associazione da sostituire.</span><span class="sxs-lookup"><span data-stu-id="a68dd-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="a68dd-110">[in] Una combinazione OR logica di [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valori, che indica il controllo del reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="a68dd-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="a68dd-111">[out] Puntatore a un buffer che contiene i nuovi dati di criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="a68dd-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="a68dd-112">[in, out] Un puntatore alla dimensione del buffer di nuovi criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="a68dd-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a68dd-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a68dd-113">Return Value</span></span>  
  
|<span data-ttu-id="a68dd-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a68dd-114">HRESULT</span></span>|<span data-ttu-id="a68dd-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a68dd-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a68dd-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a68dd-116">S_OK</span></span>|<span data-ttu-id="a68dd-117">Il criterio è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="a68dd-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="a68dd-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a68dd-118">E_INVALIDARG</span></span>|<span data-ttu-id="a68dd-119">`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` fosse un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="a68dd-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="a68dd-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a68dd-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a68dd-121">`pbNewApplicationPolicy` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="a68dd-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="a68dd-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a68dd-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a68dd-123">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a68dd-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a68dd-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a68dd-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a68dd-125">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a68dd-125">The call timed out.</span></span>|  
|<span data-ttu-id="a68dd-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a68dd-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a68dd-127">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="a68dd-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a68dd-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a68dd-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a68dd-129">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a68dd-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a68dd-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a68dd-130">E_FAIL</span></span>|<span data-ttu-id="a68dd-131">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a68dd-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a68dd-132">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a68dd-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a68dd-133">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a68dd-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a68dd-134">Note</span><span class="sxs-lookup"><span data-stu-id="a68dd-134">Remarks</span></span>  
 <span data-ttu-id="a68dd-135">Il `ModifyApplicationPolicy` metodo può essere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="a68dd-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="a68dd-136">La prima chiamata deve fornire un valore null per il `pbNewApplicationPolicy` parametro.</span><span class="sxs-lookup"><span data-stu-id="a68dd-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="a68dd-137">Questa chiamata restituirà con il valore necessario per `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="a68dd-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="a68dd-138">La seconda chiamata deve fornire questo valore per `pcbNewAppPolicySize`e puntare a un buffer di tale dimensione per `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="a68dd-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a68dd-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a68dd-139">Requirements</span></span>  
 <span data-ttu-id="a68dd-140">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a68dd-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a68dd-141">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a68dd-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a68dd-142">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a68dd-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a68dd-143">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a68dd-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68dd-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a68dd-144">See Also</span></span>  
 [<span data-ttu-id="a68dd-145">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a68dd-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
