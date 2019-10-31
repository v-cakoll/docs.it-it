---
title: Metodo IHostTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: e560d08d3e10db1b5978d1bd7be53dfed9ca3268
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132975"
---
# <a name="ihosttaskmanagersetlocale-method"></a>Metodo IHostTaskManager::SetLocale
Notifica all'host che la Common Language Runtime (CLR) ha modificato le impostazioni locali o le impostazioni cultura nell'attività attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lcid`  
 in Valore dell'identificatore delle impostazioni locali mappato alle impostazioni cultura e alla lingua geografiche appena assegnate.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetLocale` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non consente al codice utente gestito di modificare le impostazioni locali.|  
  
## <a name="remarks"></a>Note  
 Il runtime chiama `SetLocale` quando il valore della proprietà <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> viene modificato dal codice gestito. Questo metodo consente all'host di eseguire tutti i meccanismi che potrebbero avere per la sincronizzazione delle impostazioni locali. Se un host non consente la modifica delle impostazioni locali dal codice gestito o non implementa un meccanismo per sincronizzare le impostazioni locali, deve restituire E_NOTIMPL da questo metodo.  
  
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
- [Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
