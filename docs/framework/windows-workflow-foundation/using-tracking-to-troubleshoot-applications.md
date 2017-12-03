---
title: Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52a599d9cba2e68fdb74d364dad562d2547ca020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni
[!INCLUDE[wf](../../../includes/wf-md.md)] consente di rilevare informazioni correlate al flusso di lavoro per fornire dettagli nell'esecuzione di un'applicazione o un servizio di [!INCLUDE[wf2](../../../includes/wf2-md.md)]. Gli host [!INCLUDE[wf2](../../../includes/wf2-md.md)] possono acquisire gli eventi del flusso di lavoro durante l'esecuzione di un'istanza del flusso di lavoro. Se il flusso di lavoro genera errori o eccezioni, è possibile usare i dettagli di rilevamento di [!INCLUDE[wf2](../../../includes/wf2-md.md)] per risolvere i problemi relativi all'elaborazione.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Risoluzione dei problemi relativi a un'attività WF tramite il rilevamento di WF  
 Per rilevare gli errori all'interno dell'elaborazione di un'attività [!INCLUDE[wf2](../../../includes/wf2-md.md)], è possibile abilitare il rilevamento con un apposito profilo che esegue query per un oggetto <xref:System.Activities.Tracking.ActivityStateRecord> con lo stato Faulted. La query corrispondente viene specificata nel codice seguente:  
  
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
  
 Quando un'istanza del flusso di lavoro rileva un'eccezione non gestita, viene generato un oggetto <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> se è stato abilitato il rilevamento [!INCLUDE[wf2](../../../includes/wf2-md.md)].  
  
 Questo record di rilevamento contiene i dettagli dell'errore nel formato di stack dell'eccezione. Include dettagli dell'origine dell'errore (ad esempio l'attività) che si è verificato e ha comportato l'eccezione non gestita. Per sottoscrivere gli eventi dell'errore da un servizio [!INCLUDE[wf2](../../../includes/wf2-md.md)], abilitare il rilevamento aggiungendo un partecipante di rilevamento, configurandolo con un profilo di rilevamento che esegue query per `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>e `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Se il rilevamento viene abilitato usando il partecipante del rilevamento ETW, gli eventi dell'errore vengono creati in una sessione ETW. Questi eventi possono essere visualizzati usando il Visualizzatore eventi Si trova sotto il nodo **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni** nel canale analitico.  
  
## <a name="see-also"></a>Vedere anche  
 [Monitoraggio dell'infrastruttura di App di Windows Server](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)
