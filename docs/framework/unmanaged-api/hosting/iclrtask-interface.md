---
title: Interfaccia ICLRTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask
helpviewer_keywords: ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fcce85e56abae561b05364a925fdb6b55825669
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask-interface"></a>Interfaccia ICLRTask
Fornisce metodi che consentono all'host per effettuare richieste di common language runtime (CLR) o per fornire la notifica a CLR sull'attività associata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Richiede che Common Language Runtime di interrompere l'attività che corrente `ICLRTask` istanza.|  
|[Metodo ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Notifica a Common Language Runtime che l'attività associata all'oggetto corrente `ICLRTask` istanza sta terminando e tenta di arrestare l'attività normalmente.|  
|[Metodo GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ottiene informazioni statistiche sull'utilizzo di risorse di memoria da parte dell'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.|  
|[Metodo LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ottiene il numero di blocchi mantenuti attivi per l'attività.|  
|[Metodo NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ottiene un valore che indica se l'host deve assegnare una priorità alta alla ripianificazione dell'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informa il CLR che l'host ha completato un'attività e consente di Riutilizzare corrente `ICLRTask` istanza per rappresentare un'altra attività.|  
|[Metodo RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Il CLR di interrompere l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza immediatamente, senza la garanzia che verranno eseguiti i finalizzatori.|  
|[Metodo SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Imposta un identificatore univoco per l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza, per eseguire il debug.|  
|[Metodo SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Notifica a Common Language Runtime che l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza si trova in uno stato eseguibile.|  
|[Metodo SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Notifica a Common Language Runtime che l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza non è più in uno stato eseguibile.|  
|[Metodo YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Richiede che il tempo del processore verificare CLR disponibile ad altre attività. CLR non garantisce che l'attività verrà inserita in uno stato in grado di produrre il tempo di elaborazione.|  
  
## <a name="remarks"></a>Note  
 Un `ICLRTask` è la rappresentazione di un'attività per CLR. In qualsiasi momento durante l'esecuzione di codice, un'attività può essere descritta come in esecuzione o in attesa di esecuzione. L'host chiama il `ICLRTask::SwitchIn` metodo per notificare a Common Language Runtime che l'attività che corrente `ICLRTask` istanza si trova ora in uno stato eseguibile. Dopo una chiamata a `ICLRTask::SwitchIn`, l'host può pianificare l'attività in qualsiasi thread del sistema operativo, eccetto i casi in cui il runtime richiede l'affinità di thread, come specificato dalle chiamate al [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) e [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) metodi. Successivamente, il sistema operativo potrebbe decidere di rimuovere l'attività dal thread e inserirlo in uno stato non in esecuzione. Questa situazione può verificarsi, ad esempio, ogni volta che l'attività Blocca sulle primitive di sincronizzazione o attende il completamento delle operazioni i/o. L'host chiama [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) per notificare a Common Language Runtime che l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza non è più in uno stato eseguibile.  
  
 In genere, un'attività termina alla fine dell'esecuzione del codice. A questo punto, l'host chiama `ICLRTask::ExitTask` per eliminare l'oggetto associato `ICLRTask`. Tuttavia, le attività possono essere riciclate tramite una chiamata a `ICLRTask::Reset`, che consente di `ICLRTask` l'istanza di nuovo. Questo approccio impedisce l'overhead di ripetutamente creazione ed eliminazione delle istanze.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
