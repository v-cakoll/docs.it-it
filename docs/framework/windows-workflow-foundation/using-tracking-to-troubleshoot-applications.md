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
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="407ff-102">Utilizzo del rilevamento per la risoluzione dei problemi relativi alle applicazioni</span><span class="sxs-lookup"><span data-stu-id="407ff-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="407ff-103">Windows Workflow Foundation (WF) consente di tenere traccia delle informazioni relative al flusso di lavoro per fornire dettagli sull'esecuzione di un'applicazione o di un servizio di Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="407ff-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="407ff-104">Gli host Windows Workflow Foundation sono in grado di acquisire eventi del flusso di lavoro durante l'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="407ff-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="407ff-105">Se il flusso di lavoro genera errori o eccezioni, è possibile usare i dettagli di rilevamento Windows Workflow Foundation per risolvere i problemi relativi all'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="407ff-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="407ff-106">Risoluzione dei problemi relativi a un'attività WF tramite il rilevamento di WF</span><span class="sxs-lookup"><span data-stu-id="407ff-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="407ff-107">Per rilevare gli errori all'interno dell'elaborazione di un'attività di Windows Workflow Foundation, è possibile abilitare il rilevamento con un profilo di rilevamento che esegue una query per una <xref:System.Activities.Tracking.ActivityStateRecord> con lo stato di errore.</span><span class="sxs-lookup"><span data-stu-id="407ff-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="407ff-108">La query corrispondente viene specificata nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="407ff-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="407ff-109">Se un errore viene propagato e gestito all'interno di un gestore fault (ad esempio un'attività <xref:System.Activities.Statements.TryCatch>), può essere rilevato tramite un oggetto <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="407ff-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="407ff-110"><xref:System.Activities.Tracking.FaultPropagationRecord> indica l'attività di origine dell'errore e il nome del gestore fault.</span><span class="sxs-lookup"><span data-stu-id="407ff-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="407ff-111">Il <xref:System.Activities.Tracking.FaultPropagationRecord> contiene i dettagli dell'errore sotto forma di stack di eccezioni per l'errore.</span><span class="sxs-lookup"><span data-stu-id="407ff-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.</span></span> <span data-ttu-id="407ff-112">Nell'esempio seguente viene illustrata la query per sottoscrivere una <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="407ff-112">The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="407ff-113">Se un errore non viene gestito all'interno del flusso di lavoro, comporta un'eccezione non gestita nell'istanza del flusso di lavoro che viene quindi interrotta.</span><span class="sxs-lookup"><span data-stu-id="407ff-113">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="407ff-114">Per capire i dettagli dell'eccezione non gestita, il profilo di rilevamento deve eseguire una query sul record di istanza del flusso di lavoro con `state name="UnhandledException"` come specificato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="407ff-114">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="407ff-115">Quando un'istanza del flusso di lavoro rileva un'eccezione non gestita, viene generato un oggetto <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> se Windows Workflow Foundation rilevamento è stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="407ff-115">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="407ff-116">Questo record di rilevamento contiene i dettagli dell'errore nel formato di stack dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="407ff-116">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="407ff-117">Contiene informazioni dettagliate sull'origine dell'errore (ad esempio, l'attività) che ha generato l'errore e ha causato l'eccezione non gestita. Per sottoscrivere gli eventi di errore da un Windows Workflow Foundation, abilitare il rilevamento aggiungendo un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="407ff-117">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="407ff-118">configurandolo con un profilo di rilevamento che esegue query per `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>e `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="407ff-118">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="407ff-119">Se il rilevamento viene abilitato usando il partecipante del rilevamento ETW, gli eventi dell'errore vengono creati in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="407ff-119">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="407ff-120">Questi eventi possono essere visualizzati usando il Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="407ff-120">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="407ff-121">Si trova nel nodo **Visualizzatore eventi-> registri applicazioni e servizi-> Microsoft-> Windows-> Application Server-applicazioni** nel canale analitico.</span><span class="sxs-lookup"><span data-stu-id="407ff-121">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="407ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="407ff-122">See also</span></span>

- <span data-ttu-id="407ff-123">[Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="407ff-123">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="407ff-124">[Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="407ff-124">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
