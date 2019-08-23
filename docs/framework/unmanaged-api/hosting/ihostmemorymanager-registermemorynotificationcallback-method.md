---
title: Metodo IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34701642a9e76ec52141e00fe9dde92878faccd2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945442"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>Metodo IHostMemoryManager::RegisterMemoryNotificationCallback
Registra un puntatore a una funzione di callback richiamata dall'host per notificare al Common Language Runtime (CLR) il carico di memoria corrente nel computer.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCallback`  
 in Puntatore di interfaccia a un'istanza di [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) implementata da CLR.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|DESCRIZIONE|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Poiché l' `ICLRMemoryNotificationCallback` interfaccia definisce un solo metodo ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) e poiché `pCallback` è un puntatore a un' `ICLRMemoryNotificationCallback` istanza fornita da CLR, la registrazione è efficace per funzione di callback stessa. L'host richiama `OnMemoryNotification` per segnalare le condizioni di utilizzo della memoria, anziché utilizzare la funzione `CreateMemoryResourceNotification` Win32 standard. Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.  
  
> [!NOTE]
> Chiamate a `OnMemoryNotification` Never Block. Restituiscono sempre immediatamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
