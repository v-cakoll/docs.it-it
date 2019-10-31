---
title: Metodo IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133795"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>Metodo IHostIoCompletionManager::InitializeHostOverlapped
Fornisce all'host la possibilità di inizializzare i dati personalizzati da accodare a una struttura di `OVERLAPPED` Win32 utilizzata per le richieste di I/O asincrone.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pvOverlapped`  
 in Puntatore alla struttura `OVERLAPPED` Win32 da includere con la richiesta di I/O.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per l'allocazione della risorsa richiesta.|  
  
## <a name="remarks"></a>Note  
 Le funzioni della piattaforma Windows utilizzano la struttura `OVERLAPPED` per archiviare lo stato delle richieste di I/O asincrone. CLR chiama il metodo `InitializeHostOverlapped` per concedere all'host la possibilità di accodare dati personalizzati a un'istanza di `OVERLAPPED`.  
  
> [!IMPORTANT]
> Per ottenere l'inizio del blocco di dati personalizzato, gli host devono impostare l'offset sulle dimensioni della struttura di `OVERLAPPED` (`sizeof(OVERLAPPED)`).  
  
 Un valore restituito di E_OUTOFMEMORY indica che l'host non è stato in grado di inizializzare i dati personalizzati. In questo caso, CLR segnala un errore e non riesce a chiamare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Metodo GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [Interfaccia IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
