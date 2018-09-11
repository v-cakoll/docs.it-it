---
title: Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: f991533b61705c8d0a1a8e71b632dd53f24dd979
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44263778"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
Windows Workflow Foundation (WF) consente di rilevare informazioni correlate al flusso di lavoro per fornire dettagli nell'esecuzione di un servizio o applicazione Windows Workflow Foundation. Gli host di Windows Workflow Foundation sono in grado di acquisire gli eventi del flusso di lavoro durante l'esecuzione di un'istanza del flusso di lavoro. Se il flusso di lavoro genera errori o eccezioni, è possibile utilizzare Windows Workflow Foundation i dettagli di rilevamento per la risoluzione dei problemi relativa elaborazione.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Risoluzione dei problemi relativi a un'attività WF tramite il rilevamento di WF  
 Per rilevare gli errori all'interno dell'elaborazione di un'attività di Windows Workflow Foundation, è possibile abilitare il rilevamento con un profilo di rilevamento che esegue una query per un <xref:System.Activities.Tracking.ActivityStateRecord> con lo stato Faulted. La query corrispondente viene specificata nel codice seguente:  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Se un errore viene propagato e gestito all'interno di un gestore fault (ad esempio un'attività <xref:System.Activities.Statements.TryCatch>), può essere rilevato tramite un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord>. <xref:System.Activities.Tracking.FaultPropagationRecord> indica l'attività di origine dell'errore e il nome del gestore fault. <xref:System.Activities.Tracking.FaultPropagationRecord> contiene i dettagli dell'errore sotto forma di stack dell'eccezione per l'errore. La query da sottoscrivere per un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord> è illustrata nell'esempio seguente:  
  
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
  
 Quando un'istanza del flusso di lavoro rileva un'eccezione non gestita, una <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> oggetto viene emessa se è stato abilitato il rilevamento di Windows Workflow Foundation.  
  
 Questo record di rilevamento contiene i dettagli dell'errore nel formato di stack dell'eccezione. Include i dettagli dell'origine dell'errore (ad esempio, l'attività) che si è verificato e ha generato l'eccezione non gestita. Per sottoscrivere gli eventi di errore da un Windows Workflow Foundation, abilitare il rilevamento aggiungendo un partecipante del rilevamento. configurandolo con un profilo di rilevamento che esegue query per `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>e `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Se il rilevamento viene abilitato usando il partecipante del rilevamento ETW, gli eventi dell'errore vengono creati in una sessione ETW. Questi eventi possono essere visualizzati usando il Visualizzatore eventi Questo valore può essere trovato sotto il nodo **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni** nel canale analitico.  
  
## <a name="see-also"></a>Vedere anche  
 [Monitoraggio dell'infrastruttura di App di Windows Server](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
