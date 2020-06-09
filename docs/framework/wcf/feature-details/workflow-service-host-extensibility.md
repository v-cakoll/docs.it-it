---
title: Estensibilità host del servizio flusso di lavoro
ms.date: 03/30/2017
ms.assetid: c0e8f7bb-cb13-49ec-852f-b85d7c23972f
ms.openlocfilehash: 4c2edec8c23e27f019b95223c998c72069384c75
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594894"
---
# <a name="workflow-service-host-extensibility"></a>Estensibilità host del servizio flusso di lavoro
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] fornisce la classe <xref:System.ServiceModel.Activities.WorkflowServiceHost> per ospitare i servizi flusso di lavoro. Questa classe viene usata in caso di hosting automatico di un servizio flusso di lavoro in un'applicazione gestita o un servizio Windows. La classe viene inoltre usata quando si ospita un servizio flusso di lavoro con IIS (Internet Information Services) o con il servizio Attivazione Processo Windows (WAS, Windows Process Activation Service). La classe <xref:System.ServiceModel.Activities.WorkflowServiceHost> fornisce punti di estensione che consentono di aggiungere estensioni personalizzate, modificare il comportamento inattivo e ospitare flussi di lavoro non di servizi (ovvero che non usano attività di messaggistica).  
  
## <a name="workflow-service-host-extensions"></a>Estensioni host del servizio flusso di lavoro  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene una proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> di tipo <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager> che fornisce un metodo per l'aggiunta di estensioni a <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Usare il metodo <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager.Add%2A> per aggiungere un'estensione per ogni istanza del servizio flusso di lavoro. Il delegato specificato viene chiamato per creare una nuova estensione quando un'istanza del servizio flusso di lavoro viene creata o caricata da un archivio di persistenza. Usare il metodo <xref:System.Activities.Hosting.WorkflowInstanceExtensionManager.Add%2A> per aggiungere un'estensione per ogni host del servizio flusso di lavoro. Un'istanza dell'estensione viene condivisa per tutte le istanze del servizio flusso di lavoro.  
  
## <a name="react-to-unhandled-exceptions"></a>Reazione alle eccezioni non gestite  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> consente di specificare l'azione da eseguire quando si verifica un'eccezione non gestita in un servizio flusso di lavoro. La proprietà <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior.Action%2A> specifica uno dei valori <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>:  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Abandon> - Interrompe l'istanza del servizio flusso di lavoro.  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.AbandonAndSuspend> - Esegue il rollback all'ultimo stato persistente e sospende l'istanza del servizio flusso di lavoro. Questo caso si verifica solo se il flusso di lavoro è già stato reso persistente almeno una volta. In caso contrario, l'istanza del flusso di lavoro viene interrotta.  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Cancel> - Annulla l'istanza.  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Terminate> - Termina l'istanza.  
  
 È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.  
  
```csharp  
host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.Abandon });  
```  
  
 È inoltre possibile configurarlo in un file di configurazione, come indicato nell'esempio seguente.  
  
```xml
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <workflowUnhandledExceptionBehavior action="Abandon" />
        </behavior>  
      </serviceBehaviors>  
</behaviors>
```  
  
## <a name="hosting-non-service-workflows"></a>Hosting di flussi di lavoro non di servizi  
 È possibile usare <xref:System.ServiceModel.Activities.WorkflowServiceHost> per ospitare flussi di lavoro non di servizi, che non iniziano con un'attività <xref:System.ServiceModel.Activities.Receive> o che non usano le attività di messaggistica. I servizi flusso di lavoro iniziano in genere con un'attività <xref:System.ServiceModel.Activities.Receive>. Se <xref:System.ServiceModel.Activities.WorkflowServiceHost> riceve un messaggio per un servizio flusso di lavoro, viene creata una nuova istanza del servizio flusso di lavoro (se non è già in esecuzione o non è stata già resa persistente). Se un flusso di lavoro non inizia con un'attività Receive, non può essere avviato inviando un messaggio, poiché non è presente alcuna attività che riceva il messaggio. Per ospitare un flusso di lavoro non di servizio, derivare una classe da <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> ed eseguire l'override di <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A>, <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> e <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnResolveBookmark%2A>. Eseguire l'override di <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> se si desidera fornire un ID istanza preferito. Eseguire l'override di <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> per creare un contesto di creazione di flusso di lavoro personalizzato o popolare un'istanza dell'elemento <xref:System.ServiceModel.Activities.WorkflowCreationContext> esistente. Eseguire l'override di <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnResolveBookmark%2A> per estrarre manualmente il segnalibro dal messaggio in ingresso. Se si esegue l'override di questo metodo, è necessario richiamare <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> dal corpo del metodo per rispondere al messaggio inviato a WorkflowHostingEndpoint. In caso contrario, potrebbe venire superato il limite <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>. Nei contratti bidirezionali, potrebbe rilevarsi l'impossibilità di richiamare <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> in quanto il client non è in grado di ricevere una risposta. Nei contratti unidirezionali è invece possibile che non si riesca a rilevare l'impossibilità di richiamare <xref:System.ServiceModel.Activities.WorkflowHostingResponseContext.SendResponse%2A> se non troppo tardi, dopo che il limite <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> è stato superato. Per ulteriori informazioni, vedere il [segnalibro Resume WorkflowHostingEndpoint](../../windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)per creare una nuova istanza di un flusso di lavoro non di servizio, dichiarare un contratto di servizio che definisce un'operazione che crea una nuova istanza. L'operazione di creazione deve prendere un IDictionary \<string, object> per passare tutti i parametri del flusso di lavoro necessari. Questo contratto viene implementato in modo implicito dalla classe derivata da <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>. In fase di hosting del flusso di lavoro, aggiungere un'istanza della classe derivata da <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> all'host chiamando <xref:System.ServiceModel.Activities.WorkflowServiceHost.AddServiceEndpoint%2A> e chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Per creare un'istanza del flusso di lavoro, creare un elemento <xref:System.ServiceModel.ChannelFactory%601> del tipo di contratto di servizio e chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. È quindi possibile chiamare l'operazione di creazione definita nel contratto di servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](workflow-services.md)
- [Attività di messaggistica](messaging-activities.md)
