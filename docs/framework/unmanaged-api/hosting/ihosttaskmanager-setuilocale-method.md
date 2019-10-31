---
title: Metodo IHostTaskManager::SetUILocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
ms.openlocfilehash: a929a125fc8c70744246f4f96d8a09a4605f537c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132937"
---
# <a name="ihosttaskmanagersetuilocale-method"></a>Metodo IHostTaskManager::SetUILocale
Notifica all'host che la Common Language Runtime (CLR) ha modificato le impostazioni locali dell'interfaccia utente (UI) o le impostazioni cultura nell'attività attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lcid`  
 in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetUILocale` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non consente al codice utente gestito di modificare le impostazioni cultura dell'interfaccia utente.|  
  
## <a name="remarks"></a>Note  
 Il runtime chiama `SetUILocale` quando il valore della proprietà <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> viene modificato dal codice gestito. Questo metodo consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali. Se un host non consente la modifica delle impostazioni locali dell'interfaccia utente dal codice gestito o non implementa un meccanismo per sincronizzare le impostazioni locali, deve restituire E_NOTIMPL da questo metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
