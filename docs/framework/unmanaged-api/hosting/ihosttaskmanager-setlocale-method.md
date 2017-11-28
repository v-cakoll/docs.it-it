---
title: Metodo IHostTaskManager::SetLocale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetLocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 885dd41a3bc5afb156d1f338fb3564731d5a742a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetlocale-method"></a>Metodo IHostTaskManager::SetLocale
Notifica all'host che common language runtime (CLR) ha modificato le impostazioni locali, o le impostazioni cultura, l'attività attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `lcid`  
 [in] Il valore dell'identificatore delle impostazioni locali che esegue il mapping alle nuove impostazioni e alla lingua.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetLocale`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non consente il codice utente gestito modificare le impostazioni locali.|  
  
## <a name="remarks"></a>Note  
 Il runtime chiama `SetLocale` quando il valore di <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> proprietà viene modificata dal codice gestito. Questo metodo fornisce una possibilità per l'host di eseguire qualsiasi meccanismi che disponibili per la sincronizzazione delle impostazioni locali. Se un host non consente le impostazioni locali essere modificato dal codice gestito o non implementa un meccanismo per la sincronizzazione delle impostazioni locali, da questo metodo deve restituire E_NOTIMPL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [SetUILocale (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
