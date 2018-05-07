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
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>Metodo ICLRHostBindingPolicyManager::EvaluatePolicy
Valuta i criteri di associazione per conto dell'host.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
#### <a name="parameters"></a>Parametri  
 `pwzReferenceIdentity`  
 [in] Un riferimento all'assembly prima della valutazione dei criteri.  
  
 `pbApplicationPolicy`  
 [in] Puntatore a un buffer che contiene i dati dei criteri.  
  
 `cbAppPolicySize`  
 [in] Le dimensioni del `pbApplicationPolicy` buffer.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Un riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Puntatore alla dimensione del buffer di riferimento di identità assembly dopo la valutazione dei nuovi dati dei criteri.  
  
 `pdwPoliciesApplied`  
 [out] Un puntatore a una combinazione OR logico di [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valori, che indica quali criteri sono stati applicati.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La valutazione è stata completata correttamente.|  
|E_INVALIDARG|Sia `pwzReferenceIdentity` o `pbApplicationPolicy` è un riferimento null.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` è troppo piccolo.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il `EvaluatePolicy` metodo consente all'host per influenzare il criterio di associazione per mantenere assieme a host specifici requisiti di versione. Il motore dei criteri stesso rimane all'interno di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
