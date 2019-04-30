---
title: Metodo IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90bf2b7472af3f9125edbd29f6924ddec9c1530
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973134"
---
# <a name="ihostmanualeventwait-method"></a>Metodo IHostManualEvent::Wait
Fa sì che l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza in attesa fino a quando non è di proprietà o un determinato periodo di tempo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwMilliseconds`  
 [in] Il numero di millisecondi di attesa prima della restituzione, se l'oggetto corrente `IHostManualEvent` istanza non è di proprietà.  
  
 `option`  
 [in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che indica l'azione che l'host deve avere se questa operazione si blocca.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Wait` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_DEADLOCK|L'host ha rilevato un deadlock durante l'intervallo di attesa e sceglie corrente `IHostManualEvent` istanza come vittima del deadlock.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaccia IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [Interfaccia IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [Interfaccia IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [Interfaccia IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
