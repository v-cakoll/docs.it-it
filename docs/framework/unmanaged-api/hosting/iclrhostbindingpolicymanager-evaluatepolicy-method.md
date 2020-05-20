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
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>Metodo ICLRHostBindingPolicyManager::EvaluatePolicy
Valuta i criteri di associazione per conto dell'host.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
## <a name="parameters"></a>Parametri  
 `pwzReferenceIdentity`  
 in Riferimento all'assembly prima della valutazione dei criteri.  
  
 `pbApplicationPolicy`  
 in Puntatore a un buffer che contiene i dati dei criteri.  
  
 `cbAppPolicySize`  
 in Dimensioni del `pbApplicationPolicy` buffer.  
  
 `pwzPostPolicyReferenceIdentity`  
 out Riferimento all'assembly dopo la valutazione dei nuovi dati dei criteri.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Puntatore alla dimensione del buffer del riferimento all'identità dell'assembly dopo la valutazione dei nuovi dati dei criteri.  
  
 `pdwPoliciesApplied`  
 out Puntatore a una combinazione logica o di valori [EBindPolicyLevels](ebindpolicylevels-enumeration.md) , che indica i criteri applicati.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|La valutazione è stata completata correttamente.|  
|E_INVALIDARG|`pwzReferenceIdentity`O `pbApplicationPolicy` è un riferimento null.|  
|ERROR_INSUFFICIENT_BUFFER|Il valore di `cbAppPolicySize` è troppo piccolo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `EvaluatePolicy` metodo consente all'host di influenzare i criteri di associazione per gestire i requisiti di controllo delle versioni degli assembly specifici dell'host. Il motore dei criteri rimane all'interno di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
