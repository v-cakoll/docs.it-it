---
title: Metodo ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
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
ms.openlocfilehash: 143052febe136e969987c35bc06f6c3b3356aedf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140777"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Metodo ICLRPolicyManager::SetActionOnFailure
Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `failure`  
 in Uno dei valori di [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) , che indica il tipo di errore per il quale eseguire un'azione.  
  
 `action`  
 in Uno dei valori di [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , che indica l'azione da intraprendere quando si verifica un errore. Per un elenco dei valori supportati, vedere la sezione Osservazioni.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Non è possibile impostare un'azione del criterio per l'operazione specificata oppure è stata specificata un'azione del criterio non valida per l'operazione.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, CLR genera un'eccezione quando non riesce ad allocare una risorsa, ad esempio la memoria. `SetActionOnFailure` consente all'host di eseguire l'override di questo comportamento specificando l'azione dei criteri da eseguire in caso di errore. Nella tabella seguente vengono illustrate le combinazioni di valori [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) e [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) supportati. Il prefisso FAIL_ viene omesso dai valori [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) .  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|Codecontract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|x|x||||N/D||  
|eThrowException|x|x||||N/D||  
|`eAbortThread`|x|x||||N/D|x|  
|`eRudeAbortThread`|x|x||||N/D|x|  
|`eUnloadAppDomain`|x|x||x||N/D|x|  
|`eRudeUnloadAppDomain`|x|x||x|x|N/D|x|  
|`eExitProcess`|x|x||x|x|N/D|x|  
|eFastExitProcess|x|x||x|x|N/D||  
|`eRudeExitProcess`|x|x|x|x|x|N/D||  
|`eDisableRuntime`|x|x|x|x|x|N/D||  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
