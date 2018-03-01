---
title: Metodo ICLRSyncManager::GetMonitorOwner
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b998a26056aec739587b77c1b1b39f0e9392a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>Metodo ICLRSyncManager::GetMonitorOwner
Ottiene il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che possiede il monitor identificato dal cookie specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cookie`  
 [in] Il cookie associato al monitor.  
  
 `ppOwnerHostTask`  
 [out] Un puntatore al `IHostTask` che possiede attualmente il monitor oppure null se nessuna attività dispone di proprietà.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 L'host chiama in genere `GetMonitorOwner` come parte di un meccanismo di rilevamento di deadlock. Il cookie è associato a un monitoraggio quando viene creato mediante una chiamata a [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
>  Una chiamata per il rilascio dell'evento sottostante il monitoraggio potrebbe bloccarsi, ma non un deadlock, se una chiamata a questo metodo è attualmente attiva nel cookie associato al monitor. Se si tenta di acquisire il monitor, potrebbe bloccare anche altre attività.  
  
 `GetMonitorOwner`sempre immediatamente e può essere chiamato in qualsiasi momento dopo una chiamata a `CreateMonitorEvent`. L'host non è necessario attendere fino a quando un'attività è in attesa dell'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
