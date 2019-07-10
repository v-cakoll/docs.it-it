---
title: Metodo ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1c986de068cd79ae3662c82ed24906d42bf2780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759041"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>Metodo ICLRSyncManager::GetMonitorOwner
Ottiene il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che possiede il monitoraggio identificato dal cookie specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cookie`  
 [in] Il cookie associato al monitoraggio.  
  
 `ppOwnerHostTask`  
 [out] Un puntatore al `IHostTask` che possiede attualmente il monitoraggio o null se la proprietà non dispone di alcuna attività.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 L'host chiama in genere `GetMonitorOwner` come parte di un meccanismo di rilevamento di deadlock. Il cookie è associato a un monitoraggio quando viene creato mediante una chiamata a [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
>  Una chiamata a rilasciare l'evento sottostante il monitoraggio potrebbe essere bloccata, ma non un deadlock, ovvero se una chiamata a questo metodo è attualmente in vigore nel cookie associato che monitora il. Altre attività può anche bloccare se tentano di acquisire il monitor.  
  
 `GetMonitorOwner` sempre restituisce immediatamente un valore e può essere chiamato in qualsiasi momento dopo una chiamata a `CreateMonitorEvent`. L'host non è necessario attendere un'attività è in attesa dell'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
