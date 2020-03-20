---
title: Gestione di più versioni in WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
ms.openlocfilehash: bc662e51c96a06737e1bd6fd78d5f70f3922d080
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184465"
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a>Gestione di più versioni in WorkflowServiceHost
Il <xref:System.ServiceModel.Activities.WorkflowServiceHost> controllo delle versioni side-by-side introdotto in .NET Framework 4.5.NET Framework 4.5 offre la possibilità di ospitare più versioni di un servizio flusso di lavoro in un singolo endpoint. La funzionalità side-by-side consente di configurare un servizio di flusso di lavoro in modo che le sue nuove istanze vengano create con la nuova definizione del flusso di lavoro, mentre le istanze in esecuzione vengono completate con la definizione esistente. In questo argomento viene fornita una panoramica dell'esecuzione side-by-side del servizio di flusso di lavoro usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
> [!NOTE]
> Per scaricare un esempio e guardare una procedura dettagliata video del controllo delle versioni side-by-side del servizio flusso di lavoro, vedere [Controllo delle versioni side-by-side con un servizio flusso di lavoro Xamlx ospitato](https://go.microsoft.com/fwlink/?LinkId=393746)sul Web .  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a>Hosting di più versioni in un servizio di flusso di lavoro  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene due proprietà che possono essere configurate per consentire l'esecuzione side-by-side di più versioni di un flusso di lavoro: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> e <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>. La proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contiene le versioni supportate del servizio di flusso di lavoro e la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene usata per identificare in modo univoco ogni servizio di flusso di lavoro. Questa operazione viene effettuata associando un oggetto <xref:System.Activities.WorkflowIdentity> al servizio di flusso di lavoro. <xref:System.Activities.WorkflowIdentity> contiene tre informazioni di identificazione. Le proprietà <xref:System.Activities.WorkflowIdentity.Name%2A> e <xref:System.Activities.WorkflowIdentity.Version%2A> contengono un nome e un oggetto <xref:System.Version> e sono obbligatorie, mentre la proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e può essere usata per specificare una stringa aggiuntiva che contiene informazioni quali il nome dell'assembly o altre informazioni desiderate. A ogni servizio di flusso di lavoro contenuto nella raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> deve essere associato un oggetto <xref:System.Activities.WorkflowIdentity> univoco. Un oggetto <xref:System.Activities.WorkflowIdentity> è univoco se una qualsiasi delle tre relative proprietà è diversa da un altro oggetto <xref:System.Activities.WorkflowIdentity>. Un `null` <xref:System.Activities.WorkflowIdentity> è un valore <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>consentito per , ma solo una `null` <xref:System.Activities.WorkflowIdentity>versione precedente di un servizio flusso di lavoro può avere un estensione .  
  
> [!IMPORTANT]
> <xref:System.Activities.WorkflowIdentity> non deve contenere eventuali informazioni identificabili personalmente (PII). <xref:System.Activities.WorkflowIdentity> si compone di tre parti: <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) e <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>). Le informazioni su <xref:System.Activities.WorkflowIdentity> usate per creare un'istanza vengono generate a tutti i servizi di rilevamento configurati in vari punti del ciclo di vita di attività dal runtime. La verifica di WF non ha alcun meccanismo per nascondere i PII (dati riservati dell'utente). Di conseguenza, un'istanza di <xref:System.Activities.WorkflowIdentity> non deve contenere dati di PII poiché verrebbe generata dal runtime nei record di rilevamento e può essere visibile agli utenti con accesso alla visualizzazione dei record di rilevamento.  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a>Regole per l'hosting di più versioni di un servizio di flusso di lavoro  
 Quando un utente aggiunge un'ulteriore versione a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, è necessario soddisfare diverse condizioni affinché un servizio di flusso di lavoro possa essere ospitato con lo stesso set di endpoint e la medesima descrizione. Se una delle versioni aggiuntive non soddisfa queste condizioni, <xref:System.ServiceModel.Activities.WorkflowServiceHost> genera un'eccezione quando viene chiamato `Open`. Ogni definizione di flusso di lavoro fornita all'host come versione aggiuntiva deve soddisfare i requisiti seguenti (dove la versione principale è la definizione del servizio di flusso di lavoro fornita al costruttore host). La versione aggiuntiva del flusso di lavoro deve soddisfare i requisiti seguenti:  
  
- Disporre della stessa proprietà <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> della versione principale del servizio di flusso di lavoro.  
  
- Non disporre di alcuna attività <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.SendReply> in <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> che non sia presente anche nella versione principale e, nel caso, tali attività devono corrispondere al contratto dell'operazione.  
  
- Disporre di una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> univoca. Una sola definizione di flusso di lavoro può avere `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
 Alcune modifiche sono consentite. Gli elementi seguenti possono essere diversi tra una versione e l'altra:  
  
- <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> può avere un nome e un pacchetto diversi rispetto alla versione principale.  
  
- Il valore di <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> può essere diverso rispetto alla versione principale.  
  
- Il valore di <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> può essere diverso rispetto alla versione principale.  
  
- Il valore di <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> può essere diverso rispetto alla versione principale.  
  
### <a name="configuring-the-definitionidentity"></a>Configurazione di DefinitionIdentity  
 Quando un servizio flusso di lavoro <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene creato utilizzando la finestra di progettazione del flusso di lavoro, l'oggetto viene impostato utilizzando la finestra **Proprietà.When** a workflow service is created using the workflow designer, the is set using the Properties window. Fare clic all'esterno dell'attività radice del servizio nella finestra di progettazione per selezionare il servizio flusso di lavoro e scegliere **Finestra Proprietà** dal menu **Visualizza.** Selezionare **WorkflowIdentity** dall'elenco a discesa visualizzato accanto alla proprietà **DefinitionIdentity,** quindi espandere e specificare le proprietà desiderate. <xref:System.Activities.WorkflowIdentity> Nell'esempio riportato di seguito l'oggetto <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> è configurato con <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` il e un <xref:System.Activities.WorkflowIdentity.Version%2A> di `1.0.0.0`. La proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e in questo esempio è `null`.  
  
 ![Screenshot che mostra la proprietà DefinitionIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-property.bmp)  
  
 Quando un servizio di flusso di lavoro è self-hosted, la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene configurata quando il servizio di flusso di lavoro viene costruito. Nell'esempio riportato <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> di seguito, l'oggetto è configurato <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` con <xref:System.Activities.WorkflowIdentity.Name%2A> `1.0.0.0`gli stessi valori dell'esempio precedente, con il oggetto e un di .  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 Un <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> oggetto non è obbligatorio, anche se solo una versione del servizio flusso di lavoro può avere un **valore null.**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>  
  
> [!NOTE]
> Questa condizione è utile se il servizio è stato distribuito inizialmente senza una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configurata e, successivamente, viene creata una versione aggiornata.  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a>Aggiunta di una nuova versione a un servizio di flusso di lavoro ospitato sul Web  
 Il primo passaggio della configurazione di una nuova versione di un servizio di flusso di lavoro in un servizio ospitato sul Web consiste nel creare una nuova cartella nella cartella `App_Code`, denominandola come il file del servizio. Se il file `xamlx` del servizio è denominato `MortgageWorkflow.xamlx`, la cartella deve essere denominata `MortgageWorkflow`. Inserire una copia del file `xamlx` del servizio originale in questa cartella e assegnarle un nuovo nome, ad esempio `MortgageWorkflowV1.xamlx`. Apportare le modifiche desiderate al servizio principale, aggiornare la relativa proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, quindi distribuire il servizio. Nell'esempio seguente, la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> è stata aggiornata con la proprietà <xref:System.Activities.WorkflowIdentity.Name%2A>`MortgageWorkflow` e la proprietà <xref:System.Activities.WorkflowIdentity.Version%2A>`2.0.0.0`.  
  
 ![Screenshot that shows DefinitionIdentity of WorkflowIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-workflowidentity.bmp)  
  
 Quando il servizio viene riavviato, la versione precedente verrà aggiunta automaticamente alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> poiché si trova nella sottocartella `App_Code` designata. Si noti che se la versione `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> principale del servizio flusso di lavoro ha le versioni precedenti non verrà aggiunto. Una versione può avere una proprietà `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, tuttavia se sono presenti più versioni, la versione principale non deve essere quella con la proprietà `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, altrimenti le versioni precedenti non verranno aggiunte alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a>Aggiunta di una nuova versione a un servizio di flusso di lavoro self-hosted  
 Quando si aggiunge una nuova versione a un servizio di flusso di lavoro self-hosted, l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> viene configurato con la versione principale del servizio di flusso di lavoro e le versioni precedenti devono essere aggiunte in modo esplicito alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. Nell'esempio seguente un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> viene configurato con un servizio di flusso di lavoro principale che usa una definizione del flusso di lavoro `MortgageWorkflowV2` e un servizio di flusso di lavoro configurato con una definizione del flusso di lavoro `MortgageWorkflowV1` viene aggiunto alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>. Ogni servizio di flusso di lavoro è configurato con una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> univoca che riflette la versione della definizione del flusso di lavoro.  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```
