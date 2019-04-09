---
title: Interfaccia ICLRTask
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1baeac5db41aa64380d694ebab5419229d8adb4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088206"
---
# <a name="iclrtask-interface"></a>Interfaccia ICLRTask
Fornisce metodi che consentono all'host per effettuare richieste di common language runtime (CLR) o per fornire la notifica a CLR sull'attività associata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Richiede a CLR di interrompere l'attività che corrente `ICLRTask` istanza rappresenta.|  
|[Metodo ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Invia una notifica il runtime di cui l'attività associata all'oggetto corrente `ICLRTask` istanza sta terminando e tenta di arresto normale di attività.|  
|[Metodo GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ottiene le informazioni statistiche sull'utilizzo di risorse di memoria da parte dell'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.|  
|[Metodo LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ottiene il numero di blocchi attualmente mantenuti attivi per l'attività.|  
|[Metodo NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ottiene un valore che indica se l'host deve assegnare una priorità alta per l'attività rappresentata dall'istanza corrente di ripianificazione `ICLRTask` istanza.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Indica a CLR l'host ha completato un'attività che consente a CLR di riutilizzare corrente `ICLRTask` per rappresentare un'altra attività.|  
|[Metodo RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Fa in modo che CLR di interrompere l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza immediatamente, senza la garanzia che i finalizzatori vengano eseguiti.|  
|[Metodo SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Imposta un identificatore univoco per l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza, per eseguire il debug.|  
|[Metodo SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Invia una notifica il runtime di cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza è in uno stato eseguibile.|  
|[Metodo SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Invia una notifica il runtime di cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza non è più in uno stato eseguibile.|  
|[Metodo YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Richiede che il tempo del processore di rendere CLR disponibile ad altre attività. CLR non garantisce che l'attività verrà inserito in uno stato in grado di produrre tempi di elaborazione.|  
  
## <a name="remarks"></a>Note  
 Un `ICLRTask` è la rappresentazione di un'attività per il CLR. In qualsiasi momento durante l'esecuzione di codice, un'attività può essere descritta come in esecuzione o in attesa di esecuzione. L'host chiama il `ICLRTask::SwitchIn` metodo per notificare a CLR che l'attività che corrente `ICLRTask` istanza si trova ora in uno stato eseguibile. Dopo una chiamata a `ICLRTask::SwitchIn`, l'host può pianificare l'attività in qualsiasi thread del sistema operativo, tranne nei casi in cui il runtime richiede l'affinità di thread, come specificato dalle chiamate al [BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) e [EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) metodi. Successivamente, il sistema operativo potrebbe decidere di rimuovere l'attività del thread e inserirlo in uno stato non in esecuzione. Questa situazione può verificarsi, ad esempio, ogni volta che l'attività Blocca sulle primitive di sincronizzazione o in attesa di completamento delle operazioni i/o. L'host chiama [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) per notificare a CLR che l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza non è più in uno stato eseguibile.  
  
 Un'attività è in genere termina alla fine dell'esecuzione del codice. A quel punto, l'host chiama `ICLRTask::ExitTask` distruggere associato `ICLRTask`. Tuttavia, le attività possono essere riciclate mediante una chiamata a `ICLRTask::Reset`, che consente la `ICLRTask` istanza per essere riusata. Questo approccio impedisce l'overhead di creazione e distruzione di istanze.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
