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
ms.openlocfilehash: fcf034d93ceb7ececd5f6c71708d442f62a00f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092258"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>Metodo ICLRSyncManager::CreateRWLockOwnerIterator
Richiede che il Common Language Runtime (CLR) crei un iteratore per l'host da utilizzare per determinare il set di attività in attesa di un blocco in lettura/scrittura.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cookie`  
 in Cookie associato al blocco reader-writer desiderato.  
  
 `pIterator`  
 out Puntatore a un iteratore che può essere passato ai metodi [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` è stato chiamato su un thread che sta attualmente eseguendo codice gestito.|  
  
## <a name="remarks"></a>Note  
 In genere, gli host chiamano i metodi `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`e `GetRWLockOwnerNext` durante il rilevamento di deadlock. L'host è responsabile di garantire che il blocco reader-writer sia ancora valido, perché CLR non tenta di mantenere attivo il blocco reader-writer. Per l'host sono disponibili diverse strategie per garantire la validità del blocco:  
  
- L'host può bloccare le chiamate di versione sul blocco reader-writer, ad esempio [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md), assicurando che il blocco non provochi un deadlock.  
  
- L'host può bloccare l'attesa di uscita dall'oggetto evento associato al blocco reader-writer, assicurando di nuovo che il blocco non provochi un deadlock.  
  
> [!NOTE]
> `CreateRWLockOwnerIterator` deve essere chiamato solo nei thread che eseguono attualmente codice non gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
