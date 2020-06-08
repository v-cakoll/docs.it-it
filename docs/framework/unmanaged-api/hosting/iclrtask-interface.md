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
ms.openlocfilehash: b1327e13006ca4b3f9074c1348b1817c9a1b3728
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503952"
---
# <a name="iclrtask-interface"></a>Interfaccia ICLRTask
Fornisce metodi che consentono all'host di effettuare richieste di Common Language Runtime (CLR) o di fornire notifiche a CLR sull'attività associata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](iclrtask-abort-method.md)|Richiede che CLR interrompa l'attività `ICLRTask` rappresentata dall'istanza corrente.|  
|[Metodo ExitTask](iclrtask-exittask-method.md)|Notifica a CLR che l'attività associata all' `ICLRTask` istanza corrente sta terminando e tenta di arrestare correttamente l'attività.|  
|[Metodo GetMemStats](iclrtask-getmemstats-method.md)|Ottiene informazioni statistiche sull'utilizzo delle risorse di memoria da parte dell'attività rappresentata dall' `ICLRTask` istanza corrente.|  
|[Metodo LocksHeld](iclrtask-locksheld-method.md)|Ottiene il numero di blocchi attualmente conservati nell'attività.|  
|[Metodo NeedsPriorityScheduling](iclrtask-needspriorityscheduling-method.md)|Ottiene un valore che indica se l'host deve assegnare una priorità alta alla ripianificazione dell'attività rappresentata dall' `ICLRTask` istanza corrente.|  
|[Metodo Reset](iclrtask-reset-method.md)|Informa il CLR che l'host ha completato un'attività e consente a CLR di riutilizzare l' `ICLRTask` istanza corrente per rappresentare un'altra attività.|  
|[Metodo RudeAbort](iclrtask-rudeabort-method.md)|Fa in modo che CLR interrompa immediatamente l'attività rappresentata dall' `ICLRTask` istanza corrente, senza garantire che i finalizzatori vengano eseguiti.|  
|[Metodo SetTaskIdentifier](iclrtask-settaskidentifier-method.md)|Imposta un identificatore univoco per l'attività rappresentata dall' `ICLRTask` istanza corrente, da utilizzare per il debug.|  
|[Metodo SwitchIn](iclrtask-switchin-method.md)|Notifica a CLR che l'attività rappresentata dall'istanza corrente `ICLRTask` è in uno stato eseguibile.|  
|[Metodo SwitchOut](iclrtask-switchout-method.md)|Notifica a CLR che l'attività rappresentata dall'istanza corrente `ICLRTask` non è più in uno stato eseguibile.|  
|[Metodo YieldTask](iclrtask-yieldtask-method.md)|Richiede che CLR renda disponibile il tempo del processore ad altre attività. CLR non garantisce che l'attività venga inserita in uno stato in cui può produrre tempo di elaborazione.|  
  
## <a name="remarks"></a>Osservazioni  
 Un oggetto `ICLRTask` è la rappresentazione di un'attività per CLR. In qualsiasi momento durante l'esecuzione del codice, un'attività può essere descritta come in esecuzione o in attesa di esecuzione. L'host chiama il `ICLRTask::SwitchIn` metodo per notificare a CLR che l'attività `ICLRTask` rappresentata dall'istanza corrente è ora in uno stato eseguibile. Dopo una chiamata a `ICLRTask::SwitchIn` , l'host può pianificare l'attività su qualsiasi thread del sistema operativo, tranne nei casi in cui il runtime richiede l'affinità di thread, come specificato dalle chiamate ai metodi [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md) e [IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md) . In un secondo momento, il sistema operativo potrebbe decidere di rimuovere l'attività dal thread e inserirla in uno stato non in esecuzione. Questa situazione può ad esempio verificarsi ogni volta che l'attività si blocca sulle primitive di sincronizzazione o attende il completamento delle operazioni di I/O. L'host chiama l' [opzione](iclrtask-switchout-method.md) per notificare a CLR che l'attività rappresentata dall' `ICLRTask` istanza corrente non è più in uno stato eseguibile.  
  
 Un'attività viene in genere terminata al termine dell'esecuzione del codice. In quel momento, l'host chiama `ICLRTask::ExitTask` per eliminare l'oggetto associato `ICLRTask` . Tuttavia, le attività possono essere riciclate anche tramite una chiamata a `ICLRTask::Reset` , che consente `ICLRTask` di riutilizzare l'istanza. Questo approccio impedisce il sovraccarico dovuto alla creazione e all'eliminazione ripetute di istanze.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTaskManager](iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](ihosttask-interface.md)
- [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Interfaccia ICLRTask2](iclrtask2-interface.md)
