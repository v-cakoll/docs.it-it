---
title: Metodo ICLRPolicyManager::SetActionOnFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5dc8e27ed1a5701886c3583a7515e4212f490208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Metodo ICLRPolicyManager::SetActionOnFailure
Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `failure`  
 [in] Uno del [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore per il quale eseguire l'azione.  
  
 `action`  
 [in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione da intraprendere quando si verifica un errore. Per un elenco di valori supportati, vedere la sezione Osservazioni.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Impossibile impostare un'azione di criteri per l'operazione specificata o è stata specificata un'azione di criteri non validi per l'operazione.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, CLR genera un'eccezione quando non è possibile assegnare una risorsa, ad esempio la memoria. `SetActionOnFailure`consente all'host di eseguire l'override di questo comportamento specificando l'azione di criteri da eseguire in caso di errore. Nella tabella seguente mostra le combinazioni di [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) e [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) i valori supportati. (Il prefisso FAIL_prefix viene omesso dalla [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori.)  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|CodeContract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||N/D||  
|eThrowException|X|X||||N/D||  
|`eAbortThread`|X|X||||N/D|X|  
|`eRudeAbortThread`|X|X||||N/D|X|  
|`eUnloadAppDomain`|X|X||X||N/D|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|N/D|X|  
|`eExitProcess`|X|X||X|X|N/D|X|  
|eFastExitProcess|X|X||X|X|N/D||  
|`eRudeExitProcess`|X|X|X|X|X|N/D||  
|`eDisableRuntime`|X|X|X|X|X|N/D||  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [EClrFailure (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRPolicyManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
