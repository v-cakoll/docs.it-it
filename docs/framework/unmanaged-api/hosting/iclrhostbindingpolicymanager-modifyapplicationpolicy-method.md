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
ms.openlocfilehash: 07a4998f86958e21fffc8ba8657ec9f2a170f43e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112437"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="20e52-102">Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="20e52-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="20e52-103">Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.</span><span class="sxs-lookup"><span data-stu-id="20e52-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20e52-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="20e52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20e52-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="20e52-106">[in] L'identità dell'assembly da modificare.</span><span class="sxs-lookup"><span data-stu-id="20e52-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="20e52-107">[in] La nuova identità dell'assembly modificato.</span><span class="sxs-lookup"><span data-stu-id="20e52-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="20e52-108">[in] Puntatore a un buffer che contiene i dati dei criteri di associazione per l'assembly da modificare.</span><span class="sxs-lookup"><span data-stu-id="20e52-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="20e52-109">[in] Le dimensioni dei criteri di associazione da sostituire.</span><span class="sxs-lookup"><span data-stu-id="20e52-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="20e52-110">[in] Una combinazione OR logica dei [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valori, che indicano il controllo di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="20e52-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="20e52-111">[out] Puntatore a un buffer che contiene i nuovi dati dei criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="20e52-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="20e52-112">[in, out] Puntatore alla dimensione del nuovo buffer di criteri di associazione.</span><span class="sxs-lookup"><span data-stu-id="20e52-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20e52-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="20e52-113">Return Value</span></span>  
  
|<span data-ttu-id="20e52-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20e52-114">HRESULT</span></span>|<span data-ttu-id="20e52-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20e52-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20e52-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="20e52-116">S_OK</span></span>|<span data-ttu-id="20e52-117">Il criterio è stato modificato correttamente.</span><span class="sxs-lookup"><span data-stu-id="20e52-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="20e52-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="20e52-118">E_INVALIDARG</span></span>|<span data-ttu-id="20e52-119">`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` era un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="20e52-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="20e52-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="20e52-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="20e52-121">`pbNewApplicationPolicy` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="20e52-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="20e52-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20e52-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20e52-123">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="20e52-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20e52-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20e52-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20e52-125">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="20e52-125">The call timed out.</span></span>|  
|<span data-ttu-id="20e52-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20e52-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20e52-127">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="20e52-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20e52-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20e52-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20e52-129">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="20e52-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20e52-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20e52-130">E_FAIL</span></span>|<span data-ttu-id="20e52-131">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="20e52-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20e52-132">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="20e52-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20e52-133">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="20e52-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20e52-134">Note</span><span class="sxs-lookup"><span data-stu-id="20e52-134">Remarks</span></span>  
 <span data-ttu-id="20e52-135">Il `ModifyApplicationPolicy` metodo può essere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="20e52-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="20e52-136">La prima chiamata deve fornire un valore null per il `pbNewApplicationPolicy` parametro.</span><span class="sxs-lookup"><span data-stu-id="20e52-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="20e52-137">Questa chiamata restituirà con il valore necessario per `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="20e52-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="20e52-138">La seconda chiamata dovrebbe fornire questo valore per `pcbNewAppPolicySize`e puntare a un buffer della dimensione per `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="20e52-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20e52-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20e52-139">Requirements</span></span>  
 <span data-ttu-id="20e52-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20e52-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e52-141">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20e52-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20e52-142">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="20e52-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20e52-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e52-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e52-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20e52-144">See also</span></span>

- [<span data-ttu-id="20e52-145">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="20e52-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
