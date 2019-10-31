---
title: Metodo ICLRIoCompletionManager::OnComplete
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141016"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>Metodo ICLRIoCompletionManager::OnComplete
Notifica al Common Language Runtime (CLR) lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwErrorCode`  
 in Valore HRESULT che indica lo stato dell'operazione di associazione.  
  
- S_OK indica che l'operazione è stata completata correttamente.  
  
- HOST_E_INTERRUPTED indica che la chiamata è stata interrotta prima del completamento.  
  
- E_FAIL indica che si è verificato un errore irreversibile sconosciuto, irreversibile.  
  
 `NumberOfBytesTransferred`  
 in Numero di byte trasferiti durante l'elaborazione della richiesta di I/O.  
  
 `pvOverlapped`  
 in Puntatore alla struttura `OVERLAPPED` passata alla chiamata al metodo `IHostIoCompletionManager::Bind`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OnComplete` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Se l'host implementa un'astrazione di completamento I/O, CLR esegue le richieste I/O attraverso l'host usando i metodi di [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md). L'host chiama quindi il metodo `OnComplete` per notificare al runtime il risultato di tali richieste.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
