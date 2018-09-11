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
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="2b32d-102">Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni</span><span class="sxs-lookup"><span data-stu-id="2b32d-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="2b32d-103">Windows Workflow Foundation (WF) consente di rilevare informazioni correlate al flusso di lavoro per fornire dettagli nell'esecuzione di un servizio o applicazione Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="2b32d-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="2b32d-104">Gli host di Windows Workflow Foundation sono in grado di acquisire gli eventi del flusso di lavoro durante l'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2b32d-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="2b32d-105">Se il flusso di lavoro genera errori o eccezioni, è possibile utilizzare Windows Workflow Foundation i dettagli di rilevamento per la risoluzione dei problemi relativa elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2b32d-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="2b32d-106">Risoluzione dei problemi relativi a un'attività WF tramite il rilevamento di WF</span><span class="sxs-lookup"><span data-stu-id="2b32d-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="2b32d-107">Per rilevare gli errori all'interno dell'elaborazione di un'attività di Windows Workflow Foundation, è possibile abilitare il rilevamento con un profilo di rilevamento che esegue una query per un <xref:System.Activities.Tracking.ActivityStateRecord> con lo stato Faulted.</span><span class="sxs-lookup"><span data-stu-id="2b32d-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="2b32d-108">La query corrispondente viene specificata nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2b32d-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="2b32d-109">Se un errore viene propagato e gestito all'interno di un gestore fault (ad esempio un'attività <xref:System.Activities.Statements.TryCatch>), può essere rilevato tramite un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="2b32d-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="2b32d-110"><xref:System.Activities.Tracking.FaultPropagationRecord> indica l'attività di origine dell'errore e il nome del gestore fault.</span><span class="sxs-lookup"><span data-stu-id="2b32d-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="2b32d-111"><xref:System.Activities.Tracking.FaultPropagationRecord> contiene i dettagli dell'errore sotto forma di stack dell'eccezione per l'errore. La query da sottoscrivere per un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord> è illustrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2b32d-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="2b32d-112">Se un errore non viene gestito all'interno del flusso di lavoro, comporta un'eccezione non gestita nell'istanza del flusso di lavoro che viene quindi interrotta.</span><span class="sxs-lookup"><span data-stu-id="2b32d-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="2b32d-113">Per capire i dettagli dell'eccezione non gestita, il profilo di rilevamento deve eseguire una query sul record di istanza del flusso di lavoro con `state name="UnhandledException"` come specificato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2b32d-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="2b32d-114">Quando un'istanza del flusso di lavoro rileva un'eccezione non gestita, una <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> oggetto viene emessa se è stato abilitato il rilevamento di Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="2b32d-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="2b32d-115">Questo record di rilevamento contiene i dettagli dell'errore nel formato di stack dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2b32d-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="2b32d-116">Include i dettagli dell'origine dell'errore (ad esempio, l'attività) che si è verificato e ha generato l'eccezione non gestita. Per sottoscrivere gli eventi di errore da un Windows Workflow Foundation, abilitare il rilevamento aggiungendo un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="2b32d-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="2b32d-117">configurandolo con un profilo di rilevamento che esegue query per `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>e `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="2b32d-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="2b32d-118">Se il rilevamento viene abilitato usando il partecipante del rilevamento ETW, gli eventi dell'errore vengono creati in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="2b32d-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="2b32d-119">Questi eventi possono essere visualizzati usando il Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="2b32d-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="2b32d-120">Questo valore può essere trovato sotto il nodo **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni** nel canale analitico.</span><span class="sxs-lookup"><span data-stu-id="2b32d-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b32d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b32d-121">See Also</span></span>  
 [<span data-ttu-id="2b32d-122">Monitoraggio dell'infrastruttura di App di Windows Server</span><span class="sxs-lookup"><span data-stu-id="2b32d-122">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="2b32d-123">Monitoraggio delle applicazioni con App Fabric</span><span class="sxs-lookup"><span data-stu-id="2b32d-123">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
