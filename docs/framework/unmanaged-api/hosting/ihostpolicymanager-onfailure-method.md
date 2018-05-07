---
title: Metodo IHostPolicyManager::OnFailure
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87b4d4a9606723e5cf55fac19469809e1014b7c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ihostpolicymanageronfailure-method"></a>Metodo IHostPolicyManager::OnFailure
Notifica all'host che common language runtime (CLR) sta per eseguire l'azione specificata da una chiamata al [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metodo in risposta a un errore di allocazione o il recupero di risorse.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `failure`  
 [in] Uno del [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore a cui risponde il CLR.  
  
 `action`  
 [in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione CLR richiede in risposta a `failure`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OnFailure` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
