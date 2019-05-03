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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30e75bf4a58e66bb0dd8210368b162cf14c3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936474"
---
# <a name="ihosttaskmanager-interface"></a>Interfaccia IHostTaskManager
Fornisce metodi che consentono di common language runtime (CLR) per gestire le attività tramite l'host invece di usare le funzioni di fiber o thread di sistema operativo standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere interrotta.|  
|[Metodo BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo.|  
|[Metodo CallNeedsHostHook](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Consente all'host specificare se common language runtime può rendere inline la chiamata a una funzione non gestita specificata.|  
|[Metodo CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Richieste che l'host crea una nuova attività.|  
|[Metodo EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica all'host che il codice gestito è uscendo dalla fase in cui l'attività corrente non deve essere interrotta, seguendo una precedente chiamata a `BeginDelayAbort`.|  
|[Metodo EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica all'host che il codice gestito è uscendo dalla fase in cui l'attività corrente non deve essere spostato a un altro thread del sistema operativo, seguendo una precedente chiamata a `BeginThreadAffinity`.|  
|[Metodo EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica all'host che una chiamata a un metodo non gestito, ad esempio un platform invoke (metodo), restituisce il controllo dell'esecuzione a CLR.|  
|[Metodo GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione nel thread del sistema operativo da cui viene effettuata la chiamata.|  
|[Metodo GetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ottiene la quantità di spazio dello stack che viene garantito come disponibile dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.|  
|[Metodo LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica all'host che il codice gestito sta per effettuare una chiamata a una funzione non gestita.|  
|[Metodo ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica all'host che è in corso una chiamata a common language runtime (CLR) dal codice non gestito.|  
|[Metodo ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica all'host controllo lasciando CLR che è una funzione non gestita, a sua volta, chiamato dal codice gestito.|  
|[Metodo SetCLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Fornisce l'host con un puntatore a interfaccia a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) istanza implementato da CLR.|  
|[Metodo SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica all'host che CLR ha modificato le impostazioni locali dell'attività corrente.|  
|[Metodo SetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Riservato esclusivamente per uso interno.|  
|[Metodo SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica all'host che le impostazioni locali dell'interfaccia utente sono stata modificata per l'attività corrente.|  
|[Metodo Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica all'host che l'attività corrente verrà sospeso.|  
|[Metodo SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica all'host che si passa all'attività corrente.|  
  
## <a name="remarks"></a>Note  
 `IHostTaskManager` consente a CLR creare e gestire le attività, fornire hook per l'host di eseguire un'azione quando il controllo viene trasferito dal codice gestito a codice non gestito e viceversa e specificare determinate azioni l'host può e non può eseguire durante l'esecuzione di codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
