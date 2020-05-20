---
title: Metodo ICLRPolicyManager::SetTimeoutAndAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: efd30ef04c148d5e098110efcb37e50f143884e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703433"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>Metodo ICLRPolicyManager::SetTimeoutAndAction
Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'operazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `operation`  
 in Uno dei valori di [EClrOperation](eclroperation-enumeration.md) , che indica l'operazione per la quale impostare il timeout e i criteri `action` . Sono supportati i valori seguenti:  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 in Nuovo valore di timeout, in millisecondi. Il valore infinito non determina `operation` mai il timeout.  
  
 `action`  
 in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione del criterio che CLR deve eseguire quando `operation` si verifica.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Non è possibile impostare un timeout per l'oggetto specificato `operation` oppure è stato fornito un valore non valido per `action` .|  
  
## <a name="remarks"></a>Osservazioni  
 `SetTimeoutAndAction`Incapsula le funzionalità dei metodi [ICLRPolicyManager:: Setime](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) out e [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) e può essere chiamato al posto di chiamate sequenziali a questi due metodi.  
  
> [!IMPORTANT]
> Non tutti i valori dell'azione del criterio possono essere specificati come comportamento di timeout per le operazioni CLR. Vedere le sezioni Note degli argomenti per questi due metodi per i valori validi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Metodo SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)
- [ICLRPolicyManager:: SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)
