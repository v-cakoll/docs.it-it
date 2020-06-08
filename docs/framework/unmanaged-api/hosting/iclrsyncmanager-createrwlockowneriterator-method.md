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
ms.openlocfilehash: f8fde4905c41dffde90c6361b5a8cdffa15deb4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503965"
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
 out Puntatore a un iteratore che può essere passato ai metodi [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator`è stato chiamato su un thread che sta attualmente eseguendo codice gestito.|  
  
## <a name="remarks"></a>Osservazioni  
 In genere, gli host chiamano i `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` metodi, e `GetRWLockOwnerNext` durante il rilevamento di deadlock. L'host è responsabile di garantire che il blocco reader-writer sia ancora valido, perché CLR non tenta di mantenere attivo il blocco reader-writer. Per l'host sono disponibili diverse strategie per garantire la validità del blocco:  
  
- L'host può bloccare le chiamate di versione sul blocco reader-writer, ad esempio [IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md), assicurando che il blocco non provochi un deadlock.  
  
- L'host può bloccare l'attesa di uscita dall'oggetto evento associato al blocco reader-writer, assicurando di nuovo che il blocco non provochi un deadlock.  
  
> [!NOTE]
> `CreateRWLockOwnerIterator`deve essere chiamato solo nei thread che eseguono attualmente codice non gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
