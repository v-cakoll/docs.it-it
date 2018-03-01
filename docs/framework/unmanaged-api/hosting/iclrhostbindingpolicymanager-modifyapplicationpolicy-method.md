---
title: Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 018dc40895a79788a9eef20082d764db0b2265c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>Metodo ICLRHostBindingPolicyManager::ModifyApplicationPolicy
Modifica i criteri di associazione per l'assembly specificato e crea una nuova versione del criterio.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
#### <a name="parameters"></a>Parametri  
 `pwzSourceAssemblyIdentity`  
 [in] L'identità dell'assembly da modificare.  
  
 `pwzTargetAssemblyIdentity`  
 [in] La nuova identità dell'assembly modificato.  
  
 `pbApplicationPolicy`  
 [in] Puntatore a un buffer che contiene i dati dei criteri di associazione per l'assembly da modificare.  
  
 `cbAppPolicySize`  
 [in] Le dimensioni dei criteri di associazione da sostituire.  
  
 `dwPolicyModifyFlags`  
 [in] Una combinazione OR logica di [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valori, che indica il controllo del reindirizzamento.  
  
 `pbNewApplicationPolicy`  
 [out] Puntatore a un buffer che contiene i nuovi dati di criteri di associazione.  
  
 `pcbNewAppPolicySize`  
 [in, out] Un puntatore alla dimensione del buffer di nuovi criteri di associazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il criterio è stato modificato.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era un riferimento null.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`è troppo piccolo.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il `ModifyApplicationPolicy` metodo può essere chiamato due volte. La prima chiamata deve fornire un valore null per il `pbNewApplicationPolicy` parametro. Questa chiamata restituirà con il valore necessario per `pcbNewAppPolicySize`. La seconda chiamata deve fornire questo valore per `pcbNewAppPolicySize`e puntare a un buffer di tale dimensione per `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
