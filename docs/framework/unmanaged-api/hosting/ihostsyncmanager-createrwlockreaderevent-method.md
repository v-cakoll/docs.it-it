---
title: Metodo IHostSyncManager::CreateRWLockReaderEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: f3e7456c3f992527981a15b3b1835e1ca72603ad
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803289"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a>Metodo IHostSyncManager::CreateRWLockReaderEvent
Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bInitialState`  
 [in] `true` , se `ppEvent` deve essere segnalato; in caso contrario, `false` .  
  
 `cookie`  
 in Cookie da associare al blocco del lettore.  
  
 `ppEvent`  
 out Puntatore all'indirizzo di un'istanza di [IHostManualEvent](ihostmanualevent-interface.md) o null se non è stato possibile creare l'oggetto evento.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateRWLockReaderEvent`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per creare l'oggetto evento richiesto.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama `CreateRWLockReaderEvent` per ottenere un riferimento a un' `IHostManualEvent` istanza di da utilizzare nell'implementazione di un blocco del lettore. L'host può utilizzare il cookie per determinare quali attività sono in attesa del blocco del lettore eseguendo una query sull'interfaccia [ICLRSyncManager](iclrsyncmanager-interface.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostAutoEvent](ihostautoevent-interface.md)
- [Interfaccia IHostManualEvent](ihostmanualevent-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
