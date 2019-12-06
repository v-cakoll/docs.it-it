---
title: Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: b07e850810734082568ddca9776a72575c986094
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837558"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
Windows Workflow Foundation (WF) consente di tenere traccia delle informazioni relative al flusso di lavoro per fornire dettagli sull'esecuzione di un'applicazione o di un servizio di Windows Workflow Foundation. Gli host Windows Workflow Foundation sono in grado di acquisire eventi del flusso di lavoro durante l'esecuzione di un'istanza del flusso di lavoro. Se il flusso di lavoro genera errori o eccezioni, è possibile usare i dettagli di rilevamento Windows Workflow Foundation per risolvere i problemi relativi all'elaborazione.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Risoluzione dei problemi relativi a un'attività WF tramite il rilevamento di WF  
 Per rilevare gli errori all'interno dell'elaborazione di un'attività di Windows Workflow Foundation, è possibile abilitare il rilevamento con un profilo di rilevamento che esegue una query per una <xref:System.Activities.Tracking.ActivityStateRecord> con lo stato di errore. La query corrispondente viene specificata nel codice seguente:  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Se un errore viene propagato e gestito all'interno di un gestore fault (ad esempio un'attività <xref:System.Activities.Statements.TryCatch>), può essere rilevato tramite un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord>. <xref:System.Activities.Tracking.FaultPropagationRecord> indica l'attività di origine dell'errore e il nome del gestore fault. Il <xref:System.Activities.Tracking.FaultPropagationRecord> contiene i dettagli dell'errore sotto forma di stack di eccezioni per l'errore. Nell'esempio seguente viene illustrata la query per sottoscrivere una <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 Se un errore non viene gestito all'interno del flusso di lavoro, comporta un'eccezione non gestita nell'istanza del flusso di lavoro che viene quindi interrotta. Per capire i dettagli dell'eccezione non gestita, il profilo di rilevamento deve eseguire una query sul record di istanza del flusso di lavoro con `state name="UnhandledException"` come specificato nell'esempio seguente.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 Quando un'istanza del flusso di lavoro rileva un'eccezione non gestita, viene generato un oggetto <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> se Windows Workflow Foundation rilevamento è stato abilitato.  
  
 Questo record di rilevamento contiene i dettagli dell'errore nel formato di stack dell'eccezione. Contiene informazioni dettagliate sull'origine dell'errore (ad esempio, l'attività) che ha generato l'errore e ha causato l'eccezione non gestita. Per sottoscrivere gli eventi di errore da un Windows Workflow Foundation, abilitare il rilevamento aggiungendo un partecipante del rilevamento. configurandolo con un profilo di rilevamento che esegue query per `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>e `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Se il rilevamento viene abilitato usando il partecipante del rilevamento ETW, gli eventi dell'errore vengono creati in una sessione ETW. Questi eventi possono essere visualizzati usando il Visualizzatore eventi Si trova nel nodo **Visualizzatore eventi-> registri applicazioni e servizi-> Microsoft-> Windows-> Application Server-applicazioni** nel canale analitico.  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
