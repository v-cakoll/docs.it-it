---
title: Metodo ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2461d20dc65706fcfdb8b9a2088d634c771fa1fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855597"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a>Metodo ICLRSyncManager::GetRWLockOwnerNext
Ottiene l'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) successiva bloccata sul blocco reader-writer corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Iterator`  
 in Iteratore creato tramite una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).  
  
 `ppOwnerHostTask`  
 out Puntatore al successivo `IHostTask` in attesa del blocco oppure null se nessuna attività è in attesa.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetRWLockOwnerNext`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il metodo [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
> [!NOTE]
> CLR chiama `AddRef` `IHostTask` su a cui `ppOwnerHostTask` punta per impedire l'uscita da questa attività mentre l'host include il puntatore. L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine dell'operazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
