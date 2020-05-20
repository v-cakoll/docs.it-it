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
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703446"
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
 in Uno dei valori di [EClrOperation](eclroperation-enumeration.md) , che indica l'azione per la quale è necessario personalizzare il comportamento CLR.  
  
 `action`  
 in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione del criterio che CLR deve eseguire quando `operation` si verifica.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`action`È stato specificato un valore non valido per l'oggetto `operation` oppure è stato fornito un valore non valido per `operation` .|  
  
## <a name="remarks"></a>Osservazioni  
 Non tutti i valori dell'azione del criterio possono essere specificati come comportamento predefinito per le operazioni CLR. `SetDefaultAction`in genere può essere utilizzato solo per l'escalation del comportamento. Un host può, ad esempio, specificare che le interruzioni dei thread vengano trasformate in interruzioni di thread rude, ma non è possibile specificare l'opposto. Nella tabella seguente vengono descritti i `action` valori validi per ogni `operation` valore possibile.  
  
|Valore per`operation`|Valori validi per`action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|- eAbortThread<br />- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainRudeUnload|- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ProcessExit|- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_FinalizerRun|- eNoAction<br />- eAbortThread<br />- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
