---
title: Metodo ICLRPolicyManager::SetDefaultAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 8dc3a3c04a619ace566e173fb8d8945a9d921bce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140771"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>Metodo ICLRPolicyManager::SetDefaultAction
Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'operazione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `operation`  
 in Uno dei valori di [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , che indica l'azione per la quale è necessario personalizzare il comportamento CLR.  
  
 `action`  
 in Uno dei valori di [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , che indica l'azione del criterio che CLR deve eseguire quando si verifica `operation`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|È stato specificato un `action` non valido per il `operation`oppure è stato fornito un valore non valido per `operation`.|  
  
## <a name="remarks"></a>Note  
 Non tutti i valori dell'azione del criterio possono essere specificati come comportamento predefinito per le operazioni CLR. `SetDefaultAction` in genere può essere utilizzato solo per l'escalation del comportamento. Un host può, ad esempio, specificare che le interruzioni dei thread vengano trasformate in interruzioni di thread rude, ma non è possibile specificare l'opposto. Nella tabella seguente vengono descritti i valori `action` validi per ogni possibile valore di `operation`.  
  
|Valore per `operation`|Valori validi per `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|- eAbortThread<br />- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainRudeUnload|- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ProcessExit|- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_FinalizerRun|- eNoAction<br />- eAbortThread<br />- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
