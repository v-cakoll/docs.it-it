---
title: Metodo IHostTaskManager::EndDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: cf79c0d0f6def46d7f4d55f17afbd1f1dff00ad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133067"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a>Metodo IHostTaskManager::EndDelayAbort
Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere interrotta, in seguito a una precedente chiamata a [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`EndDelayAbort` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_UNEXPECTED|`EndDelayAbort` stata chiamata senza una chiamata corrispondente a `BeginDelayAbort`.|  
  
## <a name="remarks"></a>Note  
 CLR esegue una chiamata corrispondente a `BeginDelayAbort` sull'attività corrente prima di chiamare `EndDelayAbort`. In assenza di una chiamata corrispondente, l'implementazione dell'host di [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED da `EndDelayAbort`e non deve intraprendere alcuna azione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading>
- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
