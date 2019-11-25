---
title: Specifiche delle funzionalità di Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 0c312eed1a5ba064771e7cc4c260b43d97b16315
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141877"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Specifiche delle funzionalità di Windows Workflow Foundation

.NET Framework 4 adds a number of features to Windows Workflow Foundation. Questo documento descrive alcune delle nuove funzionalità e fornisce informazioni dettagliate sugli scenari nei quali potrebbero essere utili.

## <a name="messaging-activities"></a>Attività di messaggistica

The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive WCF messages from your workflow. <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a Windows Communication Foundation (WCF) service operation that is exposed via WSDL just like standard WCF web services. <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.

### <a name="getting-started-with-messaging-activities"></a>Introduzione alle attività di messaggistica

- In Visual Studio 2012, create a WCF Workflow Service Application project. Nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.

- Right-click on the project and select **Add Service Reference**. Point to an existing web service WSDL and click **OK**. Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.

- [Workflow services documentation](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>Scenario di esempio relativo alle attività di messaggistica

A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route. Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price. It would also require you to use other out-of-box activities to create the business logic for calculating the best price.

## <a name="workflowservicehost"></a>WorkflowServiceHost

The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted). Inoltre si integra con la persistenza, il rilevamento e il controllo dell'istanza tramite un set di comportamenti del servizio. Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.

### <a name="getting-started-with-workflow-service-host"></a>Guida introduttiva all'host del servizio del flusso di lavoro

- In Visual Studio 2010, create a WCF Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.

- Per ospitare un flusso di lavoro non di messaggistica, aggiungere un <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> personalizzato che creerà l'istanza basata su un messaggio.

- Per controllare le istanze del flusso di lavoro (ad esempio sospeso o terminato), è possibile aggiungere un oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> a <xref:System.ServiceModel.WorkflowServiceHost> e successivamente utilizzare un <xref:System.ServiceModel.Activities.WorkflowControlClient>.

- Esempi di <xref:System.ServiceModel.WorkflowServiceHost> sono disponibili nelle sezioni seguenti:

  - [Esecuzione](./samples/execution.md)

  - Application: [Suspended Instance Management](./samples/suspended-instance-management.md)

- [Hosting Workflow services overview](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>Scenario relativo a WorkflowServiceHost

A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route. Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>. It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.

## <a name="correlation"></a>Correlazione

Una correlazione è una delle modalità seguenti:

- Una modalità di raggruppamento dei messaggi, ovvero la relazione tra un messaggio di richiesta e la sua risposta.

- Una modalità di mapping di un dato a un'istanza del servizio.

### <a name="getting-started"></a>Introduzione

- Per iniziare a usare la correlazione, creare un nuovo progetto in Visual Studio. Creare una variabile di tipo <xref:System.ServiceModel.Activities.CorrelationHandle>.

- Un esempio di correlazione usata per raggruppare i messaggi è una correlazione Request-Reply che raggruppa i messaggi.

  - On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.

  - Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply". Incollarla nel flusso di lavoro dopo l'attività <xref:System.ServiceModel.Activities.Receive>.

- Un esempio di mapping di un dato a un'istanza del servizio è una correlazione basata sul contenuto che associa un dato (ad esempio un ID ordine) a una determinata istanza del flusso di lavoro.

  - In un'attività di messaggistica qualsiasi, fare clic sulla proprietà `CorrelationInitializers` e aggiungere un <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> usando la variabile <xref:System.ServiceModel.Activities.CorrelationHandle> creata in precedenza. Nel messaggio fare doppio clic sulla proprietà desiderata (ad es. OrderID) dal menu a discesa. Impostare la proprietà `CorrelatesWith` sulla variabile <xref:System.ServiceModel.Activities.CorrelationHandle> usata in precedenza.

- [Correlation Conceptual Documentation](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>Scenario relativo alla correlazione

An order-processing workflow is used to handle new order creation and updating existing orders that are in process. Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities. It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.

## <a name="simplified-configuration"></a>Configurazione semplificata

The WCF configuration schema is complex and provides users with many hard to find features. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping WCF users configure their services with the following features:

- Eliminare la necessità della configurazione esplicita di ogni singolo servizio. If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.

- Consentire all'utente di definire valori predefiniti per le associazioni e i comportamenti di WCF che verranno applicati ai servizi senza configurazione esplicita.

- Gli endpoint standard definiscono endpoint preconfigurati riutilizzabili, che dispongono di valori fissi per una o più delle proprietà dell'endpoint (indirizzo, associazione e contratto) e consentono la definizione di proprietà personalizzate.

- Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of WCF client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.

### <a name="getting-started"></a>Introduzione

- [A Developer's Guide to WCF 4.0](https://go.microsoft.com/fwlink/?LinkId=204940)

- [Configurazione di una channel factory](https://go.microsoft.com/fwlink/?LinkId=204941)

- [Standard Endpoint Element](https://go.microsoft.com/fwlink/?LinkId=204942)

- [Service configuration improvements in .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=204943)

- [Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name](https://go.microsoft.com/fwlink/?LinkId=204944)

### <a name="simplified-configuration-scenarios"></a>Scenari di configurazione semplificati

- An experienced ASMX developer wants to start using WCF. However, WCF seems way too complicated! In particolare per tutte le informazioni da scrivere in un file di configurazione. In .NET 4, è anche possibile decidere di non avere un file di configurazione.

- È molto difficile configurare e gestire un set di servizi WCF già esistente. Il file di configurazione è composto da migliaia di righe di codice XML ed è molto pericoloso modificarle. È necessario aiutare gli utenti a ridurre la quantità di codice per renderlo più maneggevole.

## <a name="data-contract-resolver"></a>Resolver del contratto dati

In .NET 3.5, esistevano alcune limitazioni nella progettazione di tipi noti:

- Non era possibile aggiungere in modo dinamico tipi noti durante la serializzazione o la deserializzazione.

- I serializzatori non erano in grado di gestire le informazioni sconosciute su xsi:type.

- Gli utenti non potevano specificare quale xsi:type visualizzare sulla rete per ridurre, ad esempio, le dimensioni di un'istanza di serializzazione.

The [DataContractResolver](../wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.

### <a name="getting-started"></a>Introduzione

- [Data Contract Resolver API documentation](https://go.microsoft.com/fwlink/?LinkId=204946)

- [Introducing the Data Contract Resolver](https://go.microsoft.com/fwlink/?LinkId=204947)

- Esempi:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>Scenari relativi al resolver del contratto dati

- Evitare di dichiarare decine di oggetti <xref:System.Runtime.Serialization.KnownTypeAttribute> in un servizio.

- Ridurre la dimensione del blob XML.

## <a name="flowchart"></a>Diagramma di flusso

Il diagramma di flusso è uno noto paradigma per rappresentare visivamente i problemi di un dominio. In .NET 4 è stato introdotto un nuovo stile del flusso di controllo. Una delle caratteristiche principali del diagramma di flusso è quella di eseguire solo un'attività alla volta. I diagrammi di flusso possono rappresentare cicli e risultati alternativi, ma non possono rappresentare a livello nativo l'esecuzione simultanea di più nodi.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, create a workflow console application. Aggiungere un diagramma di flusso nella finestra di progettazione.

- La funzionalità diagramma di flusso usa le classi seguenti:

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- Esempi:

  - [Gestione errori in un'attività Flowchart usando TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [Processo di assunzione](./samples/hiring-process.md)

- Documentazione della finestra di progettazione:

  - [Activity Designer Flowchart](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>Scenari relativi al diagramma di flusso

Un'attività del diagramma di flusso può essere usata per implementare un gioco per indovinare un numero. Il gioco è molto semplice: il computer seleziona un numero casuale e il giocatore deve indovinare il numero. When the player submits each guess, the computer shows him a hint (i.e. "try a lower number"). Se il giocatore indovina il numero in meno di 7 tentativi, viene visualizzato un messaggio di congratulazioni speciali. È possibile implementare questo gioco con una combinazione delle attività procedurali seguenti:

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Attività procedurali (Sequence, If, ForEach, Switch, Assign, DoWhile, While)

Le attività procedurali forniscono un meccanismo per modellare il flusso di controllo sequenziale usando concetti noti ai programmatori. Queste attività abilitano i costrutti del linguaggio di programmazione strutturati in modo tradizionale e, se opportuno, forniscono la parità di linguaggio con linguaggi procedurali comuni, ad esempio C#/VB.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, create a workflow console application. Aggiungere le attività procedurali nella finestra di progettazione del flusso di lavoro.

- Esempi:

  - [Processo di assunzione](./samples/hiring-process.md)

  - [Processo di acquisto aziendale](./samples/corporate-purchase-process.md)

- Documentazione della finestra di progettazione:

  - [Activity Designer Parallel](/visualstudio/workflow-designer/parallel-activity-designer)

  - [ParallelForEach\<T> Activity Designer](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>Scenari relativi alle attività procedurali

- <xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow. Prima di poter essere pubblicati nella rete Intranet, i documenti devono essere approvati dai responsabili dei diversi reparti. There isn’t an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase. Quando un utente manda in revisione un documento, deve essere approvato dal suo responsabile diretto, dall'amministratore della rete Intranet e dal responsabile delle comunicazioni interne.

- <xref:System.Activities.Statements.ParallelForEach%601>: Un'applicazione WF gestisce gli acquisti di una grande società. In base a quanto definito nei regolamenti aziendali, prima di pianificare qualsiasi operazione di acquisto è necessario valutare tre fornitori diversi. Un dipendente dell'ufficio acquisti seleziona tre fornitori dall'elenco fornitori della società. Una volta selezionati e informati i fornitori, la società attenderà le proposte economiche. Le proposte possono pervenire in qualsiasi ordine. Per implementare questo scenario in WF, viene usato <xref:System.Activities.Statements.ParallelForEach%601> per scorrere l'elenco dei fornitori e richiedere le proposte economiche. Una volta raccolte tutte le offerte, viene scelta e visualizzata la migliore.

## <a name="invokemethod"></a>InvokeMethod

L'attività <xref:System.Activities.Statements.InvokeMethod> consente di richiamare metodi pubblici in oggetti o tipi nell'ambito. Supporta il richiamo di metodi di istanza e statici con o senza parametri (incluse le matrici di parametri) e metodi generici. Consente inoltre l'esecuzione del metodo in modo sincrono e asincrono.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, create a workflow console application. Aggiungere un'attività <xref:System.Activities.Statements.InvokeMethod> nella finestra di progettazione del flusso di lavoro e configurare i metodi di istanza e statici.

- Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>Scenari relativi a InvokeMethod

- È necessario richiamare un metodo in un oggetto nell'ambito. Ad esempio, è necessario aggiungere un valore a un dizionario. Viene richiamato il metodo Add dell'istanza del dizionario e vengono forniti la chiave e il valore.

- È necessario richiamare un metodo su un oggetto CLR legacy. Anziché creare un'attività personalizzata per eseguire il wrapping della chiamata a quella classe legacy, è possibile usare <xref:System.Activities.Statements.InvokeMethod>, se rientra nell'ambito durante l'esecuzione del flusso di lavoro.

## <a name="error-handling-activities"></a>Attività di gestione degli errori

L'attività <xref:System.Activities.Statements.TryCatch> fornisce un meccanismo per il rilevamento delle eccezioni che si verificano durante l'esecuzione di un set di attività contenute (simile al costrutto Try/Catch in C#/VB). <xref:System.Activities.Statements.TryCatch> fornisce la gestione delle eccezioni a livello di flusso di lavoro. Quando viene generata un'eccezione non gestita, il flusso di lavoro viene interrotto e non viene eseguito il blocco Finally. Questo comportamento è coerente con C#.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, create a workflow console application. Aggiungere un'attività <xref:System.Activities.Statements.TryCatch> nella finestra di progettazione del flusso di lavoro.

- Sample: [Fault Handling in a Flowchart Activity Using TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)

### <a name="error-handling-scenarios"></a>Scenari relativi alla gestione degli errori

È necessario eseguire un set di attività e, quando si verifica un errore, è necessario eseguire una logica specifica. Se durante l'esecuzione della logica di gestione degli errori si scopre che l'errore non è risolvibile, viene rigenerata l'eccezione e il problema viene gestito dall'attività padre (o dall'host).

## <a name="pick-activity"></a>Attività Pick

L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di flusso di controllo basato sugli eventi in WF. L'attività <xref:System.Activities.Statements.Pick> contiene molti branch, la cui esecuzione è condizionata dal verificarsi di un particolare evento. In questa impostazione, <xref:System.Activities.Statements.Pick> si comporta in modo analogo a <xref:System.Activities.Statements.Switch%601>, ovvero l'attività esegue solo uno dei set di eventi in ascolto. Ogni ramo è basato sugli eventi e l'evento che si verifica per primo determina l'esecuzione del ramo corrispondente. Tutti gli altri rami vengono annullati e interrompono l'ascolto di altri eventi.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, create a workflow console application. Aggiungere un'attività <xref:System.Activities.Statements.Pick> nella finestra di progettazione del flusso di lavoro.

- Sample: [Using the Pick Activity](./samples/using-the-pick-activity.md)

- Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Scenario relativo all'attività Pick

È necessario richiedere l'input di un utente. In circostanze normali, lo sviluppatore utilizzerebbe una chiamata al metodo come <xref:System.Console.ReadLine%2A> per richiedere l'input di un utente. Il problema di questa impostazione è che il programma attende fino a quando l'utente non immette un valore. In questo scenario, è necessario un timeout per sbloccare un'attività di blocco. Un scenario comune è quello in cui è necessario completare un'attività entro un periodo di tempo specificato. Il timeout di un'attività di blocco è uno scenario in cui l'attività Pick rappresenta un valore aggiunto.

## <a name="wcf-routing-service"></a>Servizio di routing di WCF

The Routing Service is designed to be a generic software Router that allows you to control how WCF messages flow in between your clients and services. The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services. In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located. In addition, WCF in .NET Framework 3.5 had the following limitations:

- La gestione degli errori era complessa, in quanto la logica doveva essere impostata come hardcoded nel client.

- I client e i servizi dovevano usare sempre le stesse associazioni.

- I servizi venivano adeguatamente diversificati molto raramente: è più facile far comunicare il client con un servizio che implementa tutto piuttosto che dover scegliere tra più servizi.

The routing service in .NET 4 is designed to make these problems easier to solve. Il nuovo servizio di routing offre le funzionalità seguenti:

1. Routing basato sul contenuto (gli oggetti<xref:System.ServiceModel.Dispatcher.MessageFilter> esaminano un messaggio per stabilire dove deve essere inviato).

2. Protocol bridging (transport & message)

3. Gestione degli errori (il router intercetta le eccezioni di comunicazione ed esegue il failover sugli endpoint di backup)

4. Aggiornamento dinamico (in memoria) di <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> e configurazione del routing.

### <a name="getting-started"></a>Introduzione

1. Documentation: [Routing](../wcf/feature-details/routing.md)

2. Samples: [Routing Services &#91;WCF Samples&#93;](../wcf/samples/routing-services.md)

3. Blog: [Routing Rules!](https://go.microsoft.com/fwlink/?LinkId=204956)

### <a name="routing-scenarios"></a>Scenari di routing

Il servizio di routing è utile negli scenari seguenti:

- I client possono comunicare con più servizi senza doverli indirizzare tutti direttamente.

- I client possono eseguire una logica aggiuntiva su una richiesta del client per determinare dove indirizzarlo.

- È possibile decomporre le operazioni eseguite da un client in più implementazioni del servizio senza eseguire il refactoring del client.

- I client e i servizi possono supportare associazioni diverse con impostazioni di sicurezza diverse.

- È possibile rendere i client più affidabili in caso di guasto o indisponibilità dei servizi.

## <a name="wcf-discovery"></a>WCF Discovery

WCF Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure. È possibile usarlo per rendere individuabile il servizio e configura i client per la ricerca dei servizi. Non è più necessario impostare i clienti come hardcoded con gli endpoint, pertanto l'applicazione è più affidabile e garantisce una maggiore tolleranza agli errori. Discovery è la piattaforma ideale per integrare funzionalità di configurazione automatica nell'applicazione.

Il prodotto si basa sullo standard WS-Discovery ed è progettato per essere interoperativo, estendibile e generico. Il prodotto supporta due modalità di funzionamento:

1. Gestito: se sulla rete esiste un'entità informata sui servizi esistenti, i client eseguono direttamente una query per ottenere le informazioni. È analogo ad Active Directory.

2. Ad hoc: in questa modalità i client usano messaggi multicast per individuare i servizi.

Inoltre, i messaggi di individuazione non riconoscono il protocollo di rete; è possibile usarli in aggiunta a qualsiasi protocollo che supporta i requisiti della modalità. For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging. These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.

### <a name="getting-started"></a>Introduzione

- Documentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)

- Samples: [Discovery (Samples)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Scenari relativi all'individuazione

Un sviluppatore non desidera impostare gli endpoint come hardcoded, in quanto non è possibile sapere quando sarà disponibile il servizio. Al contrario, lo sviluppatore desidera scegliere un servizio in fase di runtime. I componenti dell'applicazione devono essere più separabili, più affidabili e autoconfigurabili.

## <a name="tracking"></a>Rilevamento

Workflow tracking provides insight into the execution of a workflow instance. The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute. Per sottoscrivere i record di rilevamento, è necessario aggiungere all'host del flusso di lavoro un partecipante del rilevamento del flusso di lavoro. I record di rilevamento vengono filtrati usando un profilo di rilevamento. The .NET Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.

### <a name="getting-started"></a>Introduzione

1. In Visual Studio 2010, creare un progetto Applicazione di servizi flusso di lavoro WCF. Inizialmente, nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.

2. Aprire web.config e aggiungere un comportamento di rilevamento ETW senza profilo.

    1. Viene usato il profilo predefinito.

    2. Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**. Right-click **Analytic** and select **Enable Log**.

    3. Eseguire il servizio del flusso di lavoro.

    4. Osservare gli eventi di rilevamento del flusso di lavoro nel visualizzatore eventi.

3. Samples: [Tracking](./samples/tracking.md)

4. Conceptual documentation: [Workflow Tracking and Tracing](workflow-tracking-and-tracing.md)

## <a name="sql-workflow-instance-store"></a>Archivio di istanze del flusso di lavoro SQL

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> è un'implementazione basata su server SQL di un archivio di istanze. In un archivio di istanze è memorizzato lo stato di un'istanza in esecuzione nonché tutti i dati necessari per caricare e riprendere l'esecuzione di quell'istanza. L'host del servizio indica all'archivio di istanze di salvare lo stato dell'istanza se il flusso di lavoro è persistente e di caricare lo stato dell'istanza all'arrivo di un messaggio per quell'istanza o alla scadenza di un'attività di ritardo.

### <a name="getting-started"></a>Introduzione

1. In Visual Studio 2012, create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity. Aggiungere il comportamento <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> all'host del servizio del flusso di lavoro. Questa operazione può essere eseguita nel codice o nel file di configurazione dell'applicazione.

2. Samples: [Persistence](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. Conceptual documentation: [SQL Workflow Instance Store](sql-workflow-instance-store.md).
