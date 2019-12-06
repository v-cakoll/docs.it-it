---
title: Record di rilevamento
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: d59db7e4c90b3cffe523c89de093f58f3e520bde
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837610"
---
# <a name="tracking-records"></a>Record di rilevamento
L'esecuzione del flusso di lavoro è instrumentata per creare record di rilevamento per seguire l'esecuzione di un'istanza del flusso di lavoro.  
  
## <a name="tracking-records"></a>Record di rilevamento  
 Nella tabella seguente vengono indicati in dettaglio i record di rilevamento creati dall'esecuzione del flusso di lavoro.  
  
|Record di rilevamento|Descrizione|  
|---------------------|-----------------|  
|Record del ciclo di vita del flusso di lavoro|Creati durante le varie fasi del ciclo di vita dell'istanza del flusso di lavoro. Ad esempio un record viene generato quando viene avviato o completato il flusso di lavoro.|  
|Record del ciclo di vita dell'attività|Illustrano in dettaglio l'esecuzione dell'attività. Questi record indicano lo stato di un'attività del flusso di lavoro, ad esempio quando l'attività viene pianificata, quando viene completata o quando si verifica un errore.|  
|Record di ripresa del segnalibro.|Generato quando viene ripreso un segnalibro all'interno di un'istanza del flusso di lavoro.|  
|Record di rilevamento personalizzati|Un autore del flusso di lavoro può creare record di rilevamento personalizzati e generarli all'interno di un'attività personalizzata.|  
  
 Tutti i record correlati al rilevamento creati dal runtime di WF derivano dalla classe di base <xref:System.Activities.Tracking.TrackingRecord> che contiene il set di dati comune. I record di rilevamento mostrano il ciclo di vita di un flusso di lavoro semplice. Ogni record di rilevamento contiene dettagli sull'evento di rilevamento associato, ad esempio le proprietà <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A> e informazioni aggiuntive specifiche del tipo di record di rilevamento.  
  
 I tipi di oggetti <xref:System.Activities.Tracking.TrackingRecord> riportati di seguito vengono creati dall'esecuzione del flusso di lavoro:  
  
- **WorkflowInstanceRecord** -questo <xref:System.Activities.Tracking.TrackingRecord> descrive il ciclo di vita dell'istanza del flusso di lavoro. Ad esempio un record viene generato quando viene avviato o completato il flusso di lavoro e contiene lo stato dell'istanza del flusso di lavoro. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.WorkflowInstanceRecord>.  
  
- **WorkflowInstanceAbortedRecord** -questo <xref:System.Activities.Tracking.TrackingRecord> viene generato quando un'istanza del flusso di lavoro viene interrotta. Il record contiene il motivo dell'interruzione dell'istanza del flusso di lavoro. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.  
  
- **WorkflowInstanceUnhandledExceptionRecord** : questa <xref:System.Activities.Tracking.TrackingRecord> viene generata se si verifica un'eccezione nell'istanza del flusso di lavoro e non viene gestita da alcuna attività. Il record contiene i dettagli sull'eccezione. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.  
  
- **WorkflowInstanceSuspendedRecord** -questo <xref:System.Activities.Tracking.TrackingRecord> viene generato ogni volta che un'istanza del flusso di lavoro viene sospesa. Il record contiene il motivo della sospensione dell'istanza del flusso di lavoro. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.  
  
- **WorkflowInstanceTerminatedRecord** -questo <xref:System.Activities.Tracking.TrackingRecord> viene generato ogni volta che un'istanza del flusso di lavoro viene terminata. Il record contiene il motivo per il quale l'istanza del flusso di lavoro viene terminata. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.  
  
- **ActivityStateRecord** : questa <xref:System.Activities.Tracking.TrackingRecord> viene generata quando viene eseguita un'attività all'interno di un flusso di lavoro. Questi record indicano lo stato dell'attività all'interno dell'istanza del flusso di lavoro. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.ActivityStateRecord>.  
  
- **ActivityScheduledRecord** : questo <xref:System.Activities.Tracking.TrackingRecord> viene generato quando un'attività pianifica un'attività figlio. Questo record contiene dettagli relativi sia all'attività padre (attività di pianificazione) sia all'attività figlio pianificata. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
- **FaultPropagationRecord** : questo <xref:System.Activities.Tracking.TrackingRecord> viene generato per ogni gestore che esamina il record fino a quando non viene gestito. Viene usato per indicare il percorso di un errore all'interno dell'istanza del flusso di lavoro. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
- **CancelRequestedRecord** -questo <xref:System.Activities.Tracking.TrackingRecord> viene generato ogni volta che un'attività tenta di annullare un'attività figlio. Questo record contiene dettagli relativi sia all'attività padre sia a quella figlio annullata. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
- **BookmarkResumptionRecord** : questo <xref:System.Activities.Tracking.TrackingRecord> tiene traccia dei segnalibri ripresi correttamente. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
- **CustomTrackingRecord** : questo <xref:System.Activities.Tracking.TrackingRecord> viene creato ed emesso da un autore del flusso di lavoro all'interno di un'attività personalizzata del flusso di lavoro. I record di rilevamento personalizzati possono essere popolati con dati da creare insieme ai record. I dettagli relativi a questo record sono disponibili nell'oggetto <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
 Ad esempio potrebbe essere disponibile un'attività <xref:System.Activities.Statements.Sequence> semplice che contiene un'operazione <xref:System.Activities.Statements.WriteLine> con i record di rilevamento creati nell'ordine riportato di seguito:  
  
1. L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica che il flusso di lavoro è in fase di avvio.  
  
2. L'oggetto <xref:System.Activities.Tracking.ActivityScheduledRecord> indica che un'attività è stata pianificata. In questo caso si tratta di un'attività <xref:System.Activities.Statements.Sequence>.  
  
3. L'oggetto <xref:System.Activities.Tracking.ActivityScheduledRecord> rappresenta l'attività <xref:System.Activities.Statements.WriteLine>.  
  
4. Sono disponibili due record <xref:System.Activities.Tracking.ActivityStateRecord> che rappresentano il completamento delle due attività.  
  
5. L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceRecord> indica che il flusso di lavoro è in fase di completamento.  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
