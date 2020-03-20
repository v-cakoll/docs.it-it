---
title: Metodo IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176292"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>Metodo IHostTaskManager::CallNeedsHostHook
Consente all'host di specificare se Common Language Runtime (CLR) può inline la chiamata specificata a una funzione non gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `target`  
 [in] Indirizzo all'interno del file eseguibile portabile mappato (PE) della funzione non gestita che deve essere chiamata.  
  
 `pbCallNeedsHostHook`  
 [fuori] Puntatore a un valore booleano che indica se l'host richiede l'hook della chiamata.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore catastrofico sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Per ottimizzare l'esecuzione del codice, CLR esegue un'analisi di ogni chiamata di platform invoke durante la compilazione per determinare se la chiamata può essere inline. `CallNeedsHostHook`consente all'host di eseguire l'override di tale decisione richiedendo l'hook di una chiamata a una funzione non gestita. Se l'host richiede un hook, il runtime non inline la chiamata.  
  
 L'host in genere richiede un hook in cui è necessario regolare uno stato a virgola mobile o dopo aver ricevuto la notifica che una chiamata sta entrando in uno stato in cui l'host non può tenere traccia delle richieste di memoria del runtime o di eventuali blocchi eseguiti. Quando l'host richiede l'hook della chiamata, il runtime notifica all'host le transizioni da e verso il codice gestito utilizzando le chiamate a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)e [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
