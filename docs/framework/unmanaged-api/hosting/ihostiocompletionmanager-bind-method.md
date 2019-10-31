---
title: Metodo IHostIoCompletionManager::Bind
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133905"
---
# <a name="ihostiocompletionmanagerbind-method"></a>Metodo IHostIoCompletionManager::Bind
Associa l'handle specificato a una porta di completamento di I/O creata da una chiamata precedente a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hPort`  
 in Porta di completamento I/O a cui associare `hHandle`. Se il valore di `hPort` è null, `hHandle` viene associato alla porta di completamento I/O predefinita.  
  
 `hHandle`  
 in Handle del sistema operativo da associare a `hPort`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Bind` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Viene creata una porta di completamento di I/O tramite una chiamata a `CreateIoCompletionPort`. CLR chiama `Bind` per associare un handle a tale porta.  
  
> [!NOTE]
> Quando una richiesta di I/O viene completata, l'host deve chiamare il metodo [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
