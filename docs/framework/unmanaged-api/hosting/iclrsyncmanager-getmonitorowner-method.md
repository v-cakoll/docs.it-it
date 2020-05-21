---
title: Metodo ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: 77debe047f5b379237022f44ef8f9d96718b227d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762500"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>Metodo ICLRSyncManager::GetMonitorOwner
Ottiene l'istanza di [IHostTask](ihosttask-interface.md) a cui appartiene il monitoraggio identificato dal cookie specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cookie`  
 in Cookie associato al monitoraggio.  
  
 `ppOwnerHostTask`  
 out Puntatore all'oggetto `IHostTask` che attualmente possiede il monitoraggio oppure null se nessuna attività ha la proprietà.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host chiama in genere `GetMonitorOwner` come parte di un meccanismo di rilevamento di deadlock. Il cookie è associato a un monitoraggio quando viene creato tramite una chiamata a [IHostSyncManager:: CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
> Una chiamata per rilasciare l'evento sottostante al monitoraggio potrebbe bloccarsi, ma non deadlock, se una chiamata a questo metodo è attualmente attiva sul cookie associato a tale monitoraggio. Anche altre attività potrebbero bloccarsi se tentano di acquisire questo monitoraggio.  
  
 `GetMonitorOwner`viene sempre restituito immediatamente e può essere chiamato in qualsiasi momento dopo una chiamata a `CreateMonitorEvent` . L'host non deve attendere finché un'attività non è in attesa dell'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
