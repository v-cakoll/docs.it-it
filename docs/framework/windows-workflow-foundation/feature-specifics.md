---
title: Specifiche delle funzionalità di Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 11bde5edea44f09ef1a5658cdf0e20ec1349c84b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182916"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Specifiche delle funzionalità di Windows Workflow Foundation

.NET Framework 4 aggiunge una serie di funzionalità a Windows Workflow Foundation. Questo documento descrive alcune delle nuove funzionalità e fornisce informazioni dettagliate sugli scenari nei quali potrebbero essere utili.

## <a name="messaging-activities"></a>Attività di messaggistica

Le attività<xref:System.ServiceModel.Activities.Receive>di <xref:System.ServiceModel.Activities.SendReply> <xref:System.ServiceModel.Activities.Send>messaggistica ( , , , <xref:System.ServiceModel.Activities.ReceiveReply>) vengono utilizzate per inviare e ricevere messaggi WCF dal flusso di lavoro. <xref:System.ServiceModel.Activities.Receive>e <xref:System.ServiceModel.Activities.SendReply> le attività vengono utilizzate per formare un'operazione del servizio Windows Communication Foundation (WCF) che viene esposta tramite WSDL proprio come i servizi Web WCF standard. <xref:System.ServiceModel.Activities.Send>e <xref:System.ServiceModel.Activities.ReceiveReply> vengono utilizzati per utilizzare un <xref:System.ServiceModel.ChannelFactory>servizio web simile a un WCF ; Esiste anche un'esperienza **Aggiungi riferimento al servizio** per Workflow Foundation che genera attività preconfigurate.

### <a name="getting-started-with-messaging-activities"></a>Introduzione alle attività di messaggistica

- In Visual Studio 2012, creare un progetto di applicazione di servizio flusso di lavoro WCF. Nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.

- Fare clic con il pulsante destro del mouse sul progetto e **scegliere Aggiungi riferimento al servizio**. Scegliere un servizio Web WSDL esistente e fare clic su **OK**. Compilare il progetto per visualizzare <xref:System.ServiceModel.Activities.Send> le <xref:System.ServiceModel.Activities.ReceiveReply>attività generate (implementate tramite e ) nella casella degli strumenti.

- [Documentazione sui servizi del flusso di lavoro](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>Scenario di esempio relativo alle attività di messaggistica

Un `BestPriceFinder` servizio chiama a più servizi aerei per trovare il miglior prezzo del biglietto per una particolare rotta. L'implementazione di questo scenario richiederebbe l'utilizzo delle attività di messaggio per ricevere la richiesta di prezzo, recuperare i prezzi dai servizi back-end e rispondere alla richiesta di prezzo con il prezzo migliore. È inoltre necessario utilizzare altre attività out-of-box per creare la logica di business per calcolare il miglior prezzo.

## <a name="workflowservicehost"></a>WorkflowServiceHost

Il <xref:System.ServiceModel.WorkflowServiceHost> è l'host del flusso di lavoro out-of-box che supporta più istanze, configurazione e messaggistica WCF (anche se i flussi di lavoro non sono necessari per utilizzare la messaggistica per essere ospitati). Inoltre si integra con la persistenza, il rilevamento e il controllo dell'istanza tramite un set di comportamenti del servizio. Proprio come WCF <xref:System.ServiceModel.ServiceHost>, <xref:System.ServiceModel.WorkflowServiceHost> l'oggetto può essere self-hosted in un'applicazione console/WinForms/WPF o in un servizio Windows oppure ospitato in Modalità Web (come file con estensione xamlx) in IIS o WAS.

### <a name="getting-started-with-workflow-service-host"></a>Guida introduttiva all'host del servizio del flusso di lavoro

- In Visual Studio 2010, creare un progetto di applicazione di <xref:System.ServiceModel.WorkflowServiceHost> servizio flusso di lavoro WCF: questo progetto verrà impostato per l'utilizzo in un ambiente host web.

- Per ospitare un flusso di lavoro non di messaggistica, aggiungere un <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> personalizzato che creerà l'istanza basata su un messaggio.

- Per controllare le istanze del flusso di lavoro (ad esempio sospeso o terminato), è possibile aggiungere un oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> a <xref:System.ServiceModel.WorkflowServiceHost> e successivamente utilizzare un <xref:System.ServiceModel.Activities.WorkflowControlClient>.

- Esempi di <xref:System.ServiceModel.WorkflowServiceHost> sono disponibili nelle sezioni seguenti:

  - [Esecuzione](./samples/execution.md)

  - Applicazione: [Gestione delle istanze sospeseApplication: Suspended Instance Management](./samples/suspended-instance-management.md)

- [Panoramica dei servizi flusso di lavoro di hostingHosting Workflow services overview](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>Scenario relativo a WorkflowServiceHost

Un servizio BestPriceFinder chiama a più servizi aerei per trovare il miglior prezzo del biglietto per una particolare rotta. L'implementazione di questo scenario <xref:System.ServiceModel.WorkflowServiceHost>richiederebbe l'hosting del flusso di lavoro in . Userebbe anche le attività di messaggio per ricevere la richiesta di prezzo, recuperare i prezzi dai servizi back-end e rispondere alla richiesta di prezzo con il miglior prezzo.

## <a name="correlation"></a>Correlation

Una correlazione è una delle modalità seguenti:

- Una modalità di raggruppamento dei messaggi, ovvero la relazione tra un messaggio di richiesta e la sua risposta.

- Una modalità di mapping di un dato a un'istanza del servizio.

### <a name="getting-started"></a>Introduzione

- Per iniziare a usare la correlazione, creare un nuovo progetto in Visual Studio. Creare una variabile di tipo <xref:System.ServiceModel.Activities.CorrelationHandle>.

- Un esempio di correlazione usata per raggruppare i messaggi è una correlazione Request-Reply che raggruppa i messaggi.

  - In <xref:System.ServiceModel.Activities.Receive> un'attività, <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> fare clic <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> sulla proprietà e aggiungere un utilizzando il CorrelationHandle creato nel primo passaggio precedente.

  - Creare <xref:System.ServiceModel.Activities.SendReply> un'attività facendo clic <xref:System.ServiceModel.Activities.Receive> con il pulsante destro del mouse su e scegliendo "Crea SendReply". Incollarla nel flusso di lavoro dopo l'attività <xref:System.ServiceModel.Activities.Receive>.

- Un esempio di mapping di un dato a un'istanza del servizio è una correlazione basata sul contenuto che associa un dato (ad esempio un ID ordine) a una determinata istanza del flusso di lavoro.

  - In un'attività di messaggistica qualsiasi, fare clic sulla proprietà `CorrelationInitializers` e aggiungere un <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> usando la variabile <xref:System.ServiceModel.Activities.CorrelationHandle> creata in precedenza. Nel messaggio fare doppio clic sulla proprietà desiderata (ad es. OrderID) dal menu a discesa. Impostare la proprietà `CorrelatesWith` sulla variabile <xref:System.ServiceModel.Activities.CorrelationHandle> usata in precedenza.

- [Documentazione concettuale sulla correlazione](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>Scenario relativo alla correlazione

Un flusso di lavoro di elaborazione degli ordini viene utilizzato per gestire la creazione di nuovi ordini e l'aggiornamento degli ordini esistenti in corso. L'implementazione di questo scenario <xref:System.ServiceModel.WorkflowServiceHost> richiederebbe l'hosting del flusso di lavoro e l'utilizzo delle attività di messaggistica. Richiederebbe inoltre una correlazione basata su `orderId` per garantire che vengano apportati aggiornamenti al flusso di lavoro corretto.

## <a name="simplified-configuration"></a>Configurazione semplificata

Lo schema di configurazione WCF è complesso e fornisce agli utenti molte funzionalità difficili da trovare. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], ci siamo concentrati sull'aiutare gli utenti WCF a configurare i servizi con le funzionalità seguenti:In , we have focused on helping WCF users configure their services with the following features:

- Eliminare la necessità della configurazione esplicita di ogni singolo servizio. Se non si \<configura alcun servizio> elementi per il servizio e il servizio non definisce alcun endpoint a livello di codice, verrà aggiunto automaticamente un set di endpoint al servizio, uno per indirizzo di base del servizio e per contratto implementato dal servizio.

- Consentire all'utente di definire valori predefiniti per le associazioni e i comportamenti di WCF che verranno applicati ai servizi senza configurazione esplicita.

- Gli endpoint standard definiscono endpoint preconfigurati riutilizzabili, che dispongono di valori fissi per una o più delle proprietà dell'endpoint (indirizzo, associazione e contratto) e consentono la definizione di proprietà personalizzate.

- Infine, <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> consente di eseguire la gestione centrale della configurazione del client WCF, utile negli scenari in cui la configurazione viene selezionata o modificata dopo il tempo di caricamento del dominio applicazione.

### <a name="getting-started"></a>Introduzione

- [Guida per gli sviluppatori di WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))

- [Configurazione di una channel factory](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [Elemento endpoint standard](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [Miglioramenti della configurazione dei servizi in .NET Framework 4Service configuration improvements in .NET Framework 4](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [Errore comune dell'utente in .NET 4: errata digitazione del nome della configurazione di un servizio WF/WCF](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a>Scenari di configurazione semplificati

- Uno sviluppatore ASMX esperto desidera iniziare a utilizzare WCF. Tuttavia, WCF sembra troppo complicato! In particolare per tutte le informazioni da scrivere in un file di configurazione. In .NET 4, è anche possibile decidere di non avere un file di configurazione.

- È molto difficile configurare e gestire un set di servizi WCF già esistente. Il file di configurazione è composto da migliaia di righe di codice XML ed è molto pericoloso modificarle. È necessario aiutare gli utenti a ridurre la quantità di codice per renderlo più maneggevole.

## <a name="data-contract-resolver"></a>Resolver del contratto dati

In .NET 3.5, esistevano alcune limitazioni nella progettazione di tipi noti:

- Non era possibile aggiungere in modo dinamico tipi noti durante la serializzazione o la deserializzazione.

- I serializzatori non erano in grado di gestire le informazioni sconosciute su xsi:type.

- Gli utenti non potevano specificare quale xsi:type visualizzare sulla rete per ridurre, ad esempio, le dimensioni di un'istanza di serializzazione.

[Il DataContractResolver](../wcf/samples/datacontractresolver.md) risolve questi problemi in .NET 4.5.The DataContractResolver solves these issues in .NET 4.5.

### <a name="getting-started"></a>Introduzione

- [Documentazione sull'API del resolver del contratto dati](xref:System.Runtime.Serialization.DataContractResolver)

- [Introduzione al resolver del contratto dati](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- Esempi:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>Scenari relativi al resolver del contratto dati

- Evitare di dichiarare decine di oggetti <xref:System.Runtime.Serialization.KnownTypeAttribute> in un servizio.

- Ridurre la dimensione del blob XML.

## <a name="flowchart"></a>Diagramma di flusso

Il diagramma di flusso è uno noto paradigma per rappresentare visivamente i problemi di un dominio. Si tratta di un nuovo stile di flusso di controllo che stiamo introducendo in .NET 4.It is a new control flow style we're introduce in .NET 4. Una delle caratteristiche principali del diagramma di flusso è quella di eseguire solo un'attività alla volta. I diagrammi di flusso possono rappresentare cicli e risultati alternativi, ma non possono rappresentare a livello nativo l'esecuzione simultanea di più nodi.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, creare un'applicazione console del flusso di lavoro. Aggiungere un diagramma di flusso nella finestra di progettazione.

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

  - [Finestre di progettazione attività diagramma di flussoFlowchart Activity Designers](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>Scenari relativi al diagramma di flusso

Un'attività del diagramma di flusso può essere usata per implementare un gioco per indovinare un numero. Il gioco è molto semplice: il computer seleziona un numero casuale e il giocatore deve indovinare il numero. Quando il giocatore invia ogni ipotesi, il computer mostra loro un suggerimento (cioè "provare un numero inferiore"). Se il giocatore trova il numero in meno di 7 tentativi, riceve un complimento speciale dal computer. È possibile implementare questo gioco con una combinazione delle attività procedurali seguenti:

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Attività procedurali (Sequence, If, ForEach, Switch, Assign, DoWhile, While)

Le attività procedurali forniscono un meccanismo per modellare il flusso di controllo sequenziale usando concetti noti ai programmatori. Queste attività consentono costrutti del linguaggio di programmazione tradizionalmente strutturati e, se appropriato, forniscono la parità del linguaggio con linguaggi procedurali comuni, ad esempio C .

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, creare un'applicazione console del flusso di lavoro. Aggiungere le attività procedurali nella finestra di progettazione del flusso di lavoro.

- Esempi:

  - [Processo di assunzione](./samples/hiring-process.md)

  - [Processo di acquisto aziendale](./samples/corporate-purchase-process.md)

- Documentazione della finestra di progettazione:

  - [Activity Designer Parallel](/visualstudio/workflow-designer/parallel-activity-designer)

  - [ParallelForEach\<T> Activity Designer](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>Scenari relativi alle attività procedurali

- <xref:System.Activities.Statements.Parallel>: un sistema di gestione dei documenti intranet dispone di un flusso di lavoro di approvazione dei documenti. Prima di poter essere pubblicati nella rete Intranet, i documenti devono essere approvati dai responsabili dei diversi reparti. Non esiste un ordine stabilito per le approvazioni; possono verificarsi in qualsiasi momento mentre il documento è in fase di "approvazione in sospeso". Quando un utente invia un documento per la revisione, deve essere approvato dal responsabile diretto, dall'amministratore della rete Intranet e dal responsabile delle comunicazioni interne.

- <xref:System.Activities.Statements.ParallelForEach%601>: Un'applicazione WF gestisce gli acquisti di una grande società. In base a quanto definito nei regolamenti aziendali, prima di pianificare qualsiasi operazione di acquisto è necessario valutare tre fornitori diversi. Un dipendente del reparto acquisti seleziona tre fornitori dall'elenco dei fornitori della società. Una volta selezionati e informati i fornitori, la società attenderà le proposte economiche. Le proposte possono pervenire in qualsiasi ordine. Per implementare questo scenario in WF, viene usato <xref:System.Activities.Statements.ParallelForEach%601> per scorrere l'elenco dei fornitori e richiedere le proposte economiche. Una volta raccolte tutte le offerte, viene scelta e visualizzata la migliore.

## <a name="invokemethod"></a>InvokeMethod

L'attività <xref:System.Activities.Statements.InvokeMethod> consente di richiamare metodi pubblici in oggetti o tipi nell'ambito. Supporta il richiamo di metodi di istanza e statici con o senza parametri (incluse le matrici di parametri) e metodi generici. Consente inoltre l'esecuzione del metodo in modo sincrono e asincrono.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, creare un'applicazione console del flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.InvokeMethod> nella finestra di progettazione del flusso di lavoro e configurare i metodi di istanza e statici.

- Documentazione della finestra di progettazione: [Progettazione attività InvokeMethod](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>Scenari relativi a InvokeMethod

- È necessario richiamare un metodo in un oggetto nell'ambito. Ad esempio, è necessario aggiungere un valore a un dizionario. Viene richiamato il metodo Add dell'istanza del dizionario e vengono forniti la chiave e il valore.

- È necessario richiamare un metodo su un oggetto CLR legacy. Anziché creare un'attività personalizzata per eseguire il wrapping della chiamata a quella classe legacy, è possibile usare <xref:System.Activities.Statements.InvokeMethod>, se rientra nell'ambito durante l'esecuzione del flusso di lavoro.

## <a name="error-handling-activities"></a>Attività di gestione degli errori

L'attività <xref:System.Activities.Statements.TryCatch> fornisce un meccanismo per l'intercettazione delle eccezioni che si verificano durante l'esecuzione di un set di attività contenute (simile al costrutto Try/Catch in C . <xref:System.Activities.Statements.TryCatch> fornisce la gestione delle eccezioni a livello di flusso di lavoro. Quando viene generata un'eccezione non gestita, il flusso di lavoro viene interrotto e il Finally blocco non verrà eseguito. Questo comportamento è coerente con C#.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, creare un'applicazione console del flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.TryCatch> nella finestra di progettazione del flusso di lavoro.

- Esempio: [gestione degli errori in un'attività del diagramma di flusso tramite TryCatchSample: Fault Handling in a Flowchart Activity Using TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- Documentazione di Designer: [Progettazione degli ActivityDesigner per la gestione degli errori](/visualstudio/workflow-designer/error-handling-activity-designers)

### <a name="error-handling-scenarios"></a>Scenari relativi alla gestione degli errori

È necessario eseguire un set di attività e, quando si verifica un errore, è necessario eseguire una logica specifica. Se durante l'esecuzione della logica di gestione degli errori si scopre che l'errore non è risolvibile, viene rigenerata l'eccezione e il problema viene gestito dall'attività padre (o dall'host).

## <a name="pick-activity"></a>Attività Pick

L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di flusso di controllo basato sugli eventi in WF. L'attività <xref:System.Activities.Statements.Pick> contiene molti branch, la cui esecuzione è condizionata dal verificarsi di un particolare evento. In questa impostazione, <xref:System.Activities.Statements.Pick> si comporta in modo analogo a <xref:System.Activities.Statements.Switch%601>, ovvero l'attività esegue solo uno dei set di eventi in ascolto. Ogni ramo è basato sugli eventi e l'evento che si verifica per primo determina l'esecuzione del ramo corrispondente. Tutti gli altri rami vengono annullati e interrompono l'ascolto di altri eventi.

### <a name="getting-started"></a>Introduzione

- In Visual Studio 2012, creare un'applicazione console del flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.Pick> nella finestra di progettazione del flusso di lavoro.

- Esempio: [utilizzo dell'attività di prelievo](./samples/using-the-pick-activity.md)

- Documentazione di Progettazione: [Selezionare Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Scenario relativo all'attività Pick

È necessario richiedere l'input di un utente. In circostanze normali, lo sviluppatore <xref:System.Console.ReadLine%2A> utilizzerebbe una chiamata al metodo per richiedere l'input di un utente. Il problema di questa impostazione è che il programma attende fino a quando l'utente non immette un valore. In questo scenario, è necessario un timeout per sbloccare un'attività di blocco. Un scenario comune è quello in cui è necessario completare un'attività entro un periodo di tempo specificato. Il timeout di un'attività di blocco è uno scenario in cui l'attività Pick rappresenta un valore aggiunto.

## <a name="wcf-routing-service"></a>Servizio di routing di WCF

Il servizio di routing è progettato per essere un router software generico che consente di controllare il flusso dei messaggi WCF tra i client e i servizi. Il servizio di routing consente di separare i client dai servizi, il che offre molta più libertà in termini di configurazioni che è possibile supportare e la flessibilità di cui si dispone quando si considera come ospitare i servizi. In .NET 3.5, i client e i servizi erano strettamente accoppiati; un cliente doveva conoscere tutti i servizi con cui doveva parlare e dove si trovava. Inoltre, WCF in .NET Framework 3.5 aveva le limitazioni seguenti:

- La gestione degli errori era complessa, in quanto la logica doveva essere impostata come hardcoded nel client.

- I client e i servizi dovevano usare sempre le stesse associazioni.

- I servizi venivano adeguatamente diversificati molto raramente: è più facile far comunicare il client con un servizio che implementa tutto piuttosto che dover scegliere tra più servizi.

Il servizio di routing in .NET 4 è progettato per semplificare la risoluzione di questi problemi. Il nuovo servizio di routing offre le funzionalità seguenti:

1. Routing basato sul contenuto (gli oggetti<xref:System.ServiceModel.Dispatcher.MessageFilter> esaminano un messaggio per stabilire dove deve essere inviato).

2. Bridging di protocollo (trasporto & messaggio)

3. Gestione degli errori (il router intercetta le eccezioni di comunicazione ed esegue il failover sugli endpoint di backup)

4. Aggiornamento dinamico (in memoria) di <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> e configurazione del routing.

### <a name="getting-started"></a>Introduzione

1. Documentazione: [Routing](../wcf/feature-details/routing.md)

2. Esempi:&#93;di esempi di [servizi di routing &#91;WCFSamples: Routing Services for WCF Samples&#93;](../wcf/samples/routing-services.md)

3. Blog: [Regole di routing!](https://docs.microsoft.com/archive/blogs/RoutingRules/)

### <a name="routing-scenarios"></a>Scenari di routing

Il servizio di routing è utile negli scenari seguenti:

- I client possono comunicare con più servizi senza doverli indirizzare tutti direttamente.

- I client possono eseguire una logica aggiuntiva su una richiesta del client per determinare dove indirizzarlo.

- È possibile decomporre le operazioni eseguite da un client in più implementazioni del servizio senza eseguire il refactoring del client.

- I client e i servizi possono supportare associazioni diverse con impostazioni di sicurezza diverse.

- È possibile rendere i client più affidabili in caso di guasto o indisponibilità dei servizi.

## <a name="wcf-discovery"></a>WCF Discovery

Individuazione WCF è una tecnologia del framework che consente di incorporare un meccanismo di individuazione per l'infrastruttura dell'applicazione. È possibile usarlo per rendere individuabile il servizio e configura i client per la ricerca dei servizi. Non è più necessario impostare i clienti come hardcoded con gli endpoint, pertanto l'applicazione è più affidabile e garantisce una maggiore tolleranza agli errori. Discovery è la piattaforma ideale per integrare funzionalità di configurazione automatica nell'applicazione.

Il prodotto si basa sullo standard WS-Discovery È progettato per essere interoperabile, estensibile e generico. Il prodotto supporta due modalità di funzionamento:

1. Gestito: se sulla rete esiste un'entità informata sui servizi esistenti, i client eseguono direttamente una query per ottenere le informazioni. È analogo ad Active Directory.

2. Ad hoc: in questa modalità i client usano messaggi multicast per individuare i servizi.

Inoltre, i messaggi di individuazione non riconoscono il protocollo di rete; è possibile usarli in aggiunta a qualsiasi protocollo che supporta i requisiti della modalità. Ad esempio, i messaggi multicast di individuazione possono essere inviati tramite il canale UDP o qualsiasi altra rete che supporta la messaggistica multicast. Questi punti di progettazione, combinati con la flessibilità delle funzionalità, consentono di adattare la scoperta in modo specifico alla soluzione.

### <a name="getting-started"></a>Introduzione

- Documentazione: [Individuazione WCFDocumentation: WCF Discovery](../wcf/feature-details/wcf-discovery.md)

- Esempi: [Individuazione (campioni)Samples: Discovery (Samples)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Scenari relativi all'individuazione

Un sviluppatore non desidera impostare gli endpoint come hardcoded, in quanto non è possibile sapere quando sarà disponibile il servizio. Al contrario, lo sviluppatore desidera scegliere un servizio in fase di runtime. I componenti dell'applicazione devono essere più separabili, più affidabili e autoconfigurabili.

## <a name="tracking"></a>Rilevamento

Il rilevamento del flusso di lavoro fornisce informazioni dettagliate sull'esecuzione di un'istanza del flusso di lavoro. Gli eventi di rilevamento vengono generati da un flusso di lavoro a livello di istanza del flusso di lavoro e quando vengono eseguite le attività all'interno del flusso di lavoro. Per sottoscrivere i record di rilevamento, è necessario aggiungere all'host del flusso di lavoro un partecipante del rilevamento del flusso di lavoro. I record di rilevamento vengono filtrati usando un profilo di rilevamento. .NET Framework fornisce un partecipante di rilevamento ETW (Event Tracing for Windows) e un profilo di base viene installato nel file machine.config.

### <a name="getting-started"></a>Introduzione

1. In Visual Studio 2010, creare un progetto Applicazione di servizi flusso di lavoro WCF. Inizialmente, nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.

2. Aprire web.config e aggiungere un comportamento di rilevamento ETW senza profilo.

    1. Viene usato il profilo predefinito.

    2. Aprire il Visualizzatore eventi e abilitare il canale analitico nel nodo seguente: **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**, Applicazioni server **applicazioni .** Fare clic con il pulsante destro del mouse su **Analitica** e selezionare **Abilita registro**.

    3. Eseguire il servizio del flusso di lavoro.

    4. Osservare gli eventi di rilevamento del flusso di lavoro nel visualizzatore eventi.

3. Esempi: [tracciamento](./samples/tracking.md)

4. Documentazione concettuale: [Rilevamento e traccia del flusso di lavoroConceptual](workflow-tracking-and-tracing.md) documentation: Workflow Tracking and Tracing

## <a name="sql-workflow-instance-store"></a>Archivio di istanze del flusso di lavoro SQL

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> è un'implementazione basata su server SQL di un archivio di istanze. In un archivio di istanze è memorizzato lo stato di un'istanza in esecuzione nonché tutti i dati necessari per caricare e riprendere l'esecuzione di quell'istanza. L'host del servizio indica all'archivio di istanze di salvare lo stato dell'istanza se il flusso di lavoro è persistente e di caricare lo stato dell'istanza all'arrivo di un messaggio per quell'istanza o alla scadenza di un'attività di ritardo.

### <a name="getting-started"></a>Introduzione

1. In Visual Studio 2012, creare un flusso <xref:System.Activities.Statements.Persist> di lavoro che contiene un'attività implicita o esplicita. Aggiungere il comportamento <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> all'host del servizio del flusso di lavoro. Questa operazione può essere eseguita nel codice o nel file di configurazione dell'applicazione.

2. Esempi: [persistenzaSamples: Persistence](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. Documentazione concettuale: [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md).
