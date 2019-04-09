---
title: Metodo ICLRSyncManager::CreateRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c742410da8e7dbce53b53978516ab94243455849
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217549"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>Metodo ICLRSyncManager::CreateRWLockOwnerIterator
Richieste che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cookie`  
 [in] Il cookie associato al blocco di lettura / scrittura desiderato.  
  
 `pIterator`  
 [out] Un puntatore a un iteratore che può essere passato per il [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) metodi.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` è stato chiamato su un thread attualmente in esecuzione il codice gestito.|  
  
## <a name="remarks"></a>Note  
 Gli host in genere chiamano il `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, e `GetRWLockOwnerNext` metodi durante il rilevamento dei deadlock. L'host è responsabile di garantire che il blocco di lettura / scrittura sia ancora valido, in quanto CLR in alcun modo per mantenere attivo il blocco di lettura / scrittura. Sono disponibili per l'host garantire la validità del blocco diverse strategie:  
  
-   L'host può bloccare le chiamate di rilascio il blocco di lettura / scrittura (ad esempio, [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)), garantendo che questo blocco non causi un deadlock.  
  
-   L'host può bloccare l'uscita dall'attesa per l'oggetto evento associato al blocco di lettura / scrittura, garantendo anche che questo blocco non causi un deadlock.  
  
> [!NOTE]
>  `CreateRWLockOwnerIterator` deve essere chiamato solo sul thread che sono attualmente in esecuzione il codice non gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
