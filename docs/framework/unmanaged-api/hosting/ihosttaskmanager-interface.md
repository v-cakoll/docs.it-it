---
title: Interfaccia IHostTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 470e2ac06f433dc12d66f6cac97337a6de1d8183
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133015"
---
# <a name="ihosttaskmanager-interface"></a>Interfaccia IHostTaskManager
Fornisce metodi che consentono all'Common Language Runtime (CLR) di utilizzare le attività attraverso l'host anziché utilizzare il threading del sistema operativo standard o le funzioni fiber.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica all'host che il codice gestito sta immettendo un punto in cui l'attività corrente non deve essere interrotta.|  
|[Metodo BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica all'host che il codice gestito sta immettendo un punto in cui l'attività corrente non deve essere spostata in un altro thread del sistema operativo.|  
|[Metodo CallNeedsHostHook](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Consente all'host di specificare se il Common Language Runtime può incorporare la chiamata specificata a una funzione non gestita.|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Richiede che l'host crei una nuova attività.|  
|[Metodo EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere interrotta, in seguito a una precedente chiamata a `BeginDelayAbort`.|  
|[Metodo EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere spostata in un altro thread del sistema operativo, dopo una chiamata precedente a `BeginThreadAffinity`.|  
|[Metodo EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica all'host che una chiamata a un metodo non gestito, ad esempio un metodo di platform invoke, sta restituendo il controllo di esecuzione a CLR.|  
|[Metodo GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione nel thread del sistema operativo da cui viene effettuata la chiamata.|  
|[Metodo GetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ottiene la quantità di spazio dello stack che è garantita come disponibile al termine di un'operazione dello stack, ma prima della chiusura di un processo.|  
|[Metodo LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica all'host che il codice gestito sta per effettuare una chiamata a una funzione non gestita.|  
|[Metodo ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica all'host che viene effettuata una chiamata al Common Language Runtime (CLR) dal codice non gestito.|  
|[Metodo ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica all'host che il controllo sta lasciando il CLR e immettendo una funzione non gestita che, a sua volta, è stata chiamata dal codice gestito.|  
|[Metodo SetCLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) implementata da CLR.|  
|[Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica all'host che CLR ha modificato le impostazioni locali nell'attività corrente.|  
|[Metodo SetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Riservato esclusivamente per uso interno.|  
|[Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica all'host che le impostazioni locali dell'interfaccia utente sono state modificate nell'attività corrente.|  
|[Metodo Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica all'host che l'attività corrente è in fase di sospensione.|  
|[Metodo SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica all'host che dovrebbe disattivare l'attività corrente.|  
  
## <a name="remarks"></a>Note  
 `IHostTaskManager` consente a CLR di creare e gestire le attività, per fornire hook affinché l'host intervenga quando il controllo viene trasferito dal codice gestito al codice non gestito e viceversa e per specificare determinate azioni che l'host può e non può eseguire durante l'esecuzione del codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
