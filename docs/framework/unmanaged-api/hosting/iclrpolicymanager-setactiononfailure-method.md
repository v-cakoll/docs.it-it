---
title: Metodo ICLRPolicyManager::SetActionOnFailure
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
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4440b36485ed900b5e64adcead2525dbb7d5206e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
|`eNoAction`|x|x||||N/D||  
|eThrowException|x|x||||N/D||  
|`eAbortThread`|x|x||||N/D|x|  
|`eRudeAbortThread`|X|x||||N/D|x|  
|`eUnloadAppDomain`|X|X||x||N/D|x|  
|`eRudeUnloadAppDomain`|X|X||X|x|N/D|x|  
|`eExitProcess`|X|X||X|x|N/D|x|  
|eFastExitProcess|x|X||X|x|N/D||  
|`eRudeExitProcess`|x|X|X|X|x|N/D||  
|`eDisableRuntime`|x|X|X|X|x|N/D||  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
