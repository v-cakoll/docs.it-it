---
title: Interfaccia IHostTaskManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager
helpviewer_keywords: IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a5086f3349b3756e507855a87bd724d2618212f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanager-interface"></a>Interfaccia IHostTaskManager
Fornisce metodi che consentono a common language runtime (CLR) per gestire le attività tramite l'host anziché utilizzare le funzioni fiber o thread del sistema operativo standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[BeginDelayAbort (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere interrotta.|  
|[BeginThreadAffinity (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica all'host che il codice gestito sta entrando in un periodo in cui l'attività corrente non deve essere spostata a un altro thread del sistema operativo.|  
|[CallNeedsHostHook (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Consente all'host di specificare se common language runtime può rendere inline la chiamata a una funzione non gestita specificata.|  
|[CreateTask (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Richieste che l'host crea una nuova attività.|  
|[EndDelayAbort (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica all'host che il codice gestito sta uscendo dalla fase in cui l'attività corrente non deve essere interrotta, dopo una chiamata precedente a `BeginDelayAbort`.|  
|[EndThreadAffinity (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica all'host che il codice gestito sta uscendo dalla fase in cui l'attività corrente non deve essere spostata a un altro thread del sistema operativo, dopo una chiamata precedente a `BeginThreadAffinity`.|  
|[EnterRuntime (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica all'host che una chiamata a un metodo non gestito, ad esempio un platform invoke (metodo), restituisce il controllo dell'esecuzione a CLR.|  
|[GetCurrentTask (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Ottiene un puntatore a interfaccia per l'attività attualmente in esecuzione sul thread del sistema operativo da cui viene effettuata la chiamata.|  
|[GetStackGuarantee (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Ottiene la quantità di spazio dello stack è garantito che siano disponibili dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.|  
|[LeaveRuntime (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica all'host che il codice gestito sta per effettuare una chiamata a una funzione non gestita.|  
|[ReverseEnterRuntime (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica all'host che è in corso una chiamata a common language runtime (CLR) dal codice non gestito.|  
|[ReverseLeaveRuntime (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica all'host controllo CLR lasciando che sia una funzione non gestita, a sua volta, chiamato dal codice gestito.|  
|[SetCLRTaskManager (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Fornisce all'host con un puntatore a interfaccia a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) istanza implementata da CLR.|  
|[SetLocale (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica all'host che Common Language Runtime è stato modificato le impostazioni locali per l'attività corrente.|  
|[SetStackGuarantee (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Riservato esclusivamente per uso interno.|  
|[SetUILocale (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica all'host che le impostazioni locali dell'interfaccia utente sono stata modificata per l'attività corrente.|  
|[Sleep (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica all'host che l'attività corrente verrà sospeso.|  
|[SwitchToTask (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica all'host che deve essere disattivata l'attività corrente.|  
  
## <a name="remarks"></a>Note  
 `IHostTaskManager`consente a CLR di creare e gestire attività, per fornire hook per l'host di eseguire un'azione quando il controllo viene trasferito da gestito a codice non gestito e viceversa e per specificare le azioni l'host può e non può accettare durante l'esecuzione di codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
