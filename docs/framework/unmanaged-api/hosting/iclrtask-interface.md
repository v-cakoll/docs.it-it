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
ms.openlocfilehash: c4f27a73022b0495b2772c0485c14a1b007dc883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132638"
---
# <a name="iclrtask-interface"></a>Interfaccia ICLRTask
Fornisce metodi che consentono all'host di effettuare richieste di Common Language Runtime (CLR) o di fornire notifiche a CLR sull'attività associata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Richiede che CLR interrompa l'attività rappresentata dall'istanza di `ICLRTask` corrente.|  
|[Metodo ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Notifica a CLR che l'attività associata all'istanza di `ICLRTask` corrente sta terminando e tenta di arrestare correttamente l'attività.|  
|[Metodo GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Ottiene informazioni statistiche sull'utilizzo delle risorse di memoria da parte dell'attività rappresentata dall'istanza di `ICLRTask` corrente.|  
|[Metodo LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Ottiene il numero di blocchi attualmente conservati nell'attività.|  
|[Metodo NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Ottiene un valore che indica se l'host deve assegnare una priorità alta alla ripianificazione dell'attività rappresentata dall'istanza di `ICLRTask` corrente.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informa il CLR che l'host ha completato un'attività e consente a CLR di riutilizzare l'istanza `ICLRTask` corrente per rappresentare un'altra attività.|  
|[Metodo RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Fa in modo che CLR interrompa immediatamente l'attività rappresentata dall'istanza corrente di `ICLRTask`, senza garantire che i finalizzatori vengano eseguiti.|  
|[Metodo SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Imposta un identificatore univoco per l'attività rappresentata dall'istanza di `ICLRTask` corrente, da utilizzare nel debug.|  
|[Metodo SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Notifica a CLR che l'attività rappresentata dall'istanza di `ICLRTask` corrente è in uno stato eseguibile.|  
|[Metodo SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Notifica a CLR che l'attività rappresentata dall'istanza corrente di `ICLRTask` non è più in uno stato eseguibile.|  
|[Metodo YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Richiede che CLR renda disponibile il tempo del processore ad altre attività. CLR non garantisce che l'attività venga inserita in uno stato in cui può produrre tempo di elaborazione.|  
  
## <a name="remarks"></a>Note  
 Un `ICLRTask` è la rappresentazione di un'attività per CLR. In qualsiasi momento durante l'esecuzione del codice, un'attività può essere descritta come in esecuzione o in attesa di esecuzione. L'host chiama il metodo `ICLRTask::SwitchIn` per notificare a CLR che l'attività rappresentata dall'istanza di `ICLRTask` corrente è ora in uno stato operativo. Dopo una chiamata a `ICLRTask::SwitchIn`, l'host può pianificare l'attività su qualsiasi thread del sistema operativo, tranne nei casi in cui il runtime richiede l'affinità di thread, come specificato dalle chiamate a [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) e [IHostTaskManager:: Metodi EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) . In un secondo momento, il sistema operativo potrebbe decidere di rimuovere l'attività dal thread e inserirla in uno stato non in esecuzione. Questa situazione può ad esempio verificarsi ogni volta che l'attività si blocca sulle primitive di sincronizzazione o attende il completamento delle operazioni di I/O. L'host chiama l' [opzione](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) per notificare a CLR che l'attività rappresentata dall'istanza corrente di `ICLRTask` non è più in uno stato eseguibile.  
  
 Un'attività viene in genere terminata al termine dell'esecuzione del codice. In quel momento, l'host chiama `ICLRTask::ExitTask` per eliminare il `ICLRTask`associato. Tuttavia, le attività possono essere riciclate anche tramite una chiamata a `ICLRTask::Reset`, che consente di riutilizzare l'istanza di `ICLRTask`. Questo approccio impedisce il sovraccarico dovuto alla creazione e all'eliminazione ripetute di istanze.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
