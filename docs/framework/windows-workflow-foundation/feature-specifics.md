---
title: Specifiche delle funzionalità di Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: b18c6dd76762f4495ac475cd3dfa4e1995733b59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884484"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Specifiche delle funzionalità di Windows Workflow Foundation
[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] aggiunge una serie di funzionalità a Windows Workflow Foundation. Questo documento descrive alcune delle nuove funzionalità e fornisce informazioni dettagliate sugli scenari nei quali potrebbero essere utili.  
  
## <a name="messaging-activities"></a>Attività di messaggistica  
 Le attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) vengono usati per inviare e ricevere messaggi WCF dal flusso di lavoro.  <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> attività incluse vengono usate per formare un'operazione del servizio Windows Communication Foundation (WCF) che viene esposta tramite WSDL esattamente come servizi web WCF standard.  <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> consentono di utilizzare un servizio web simile a un WCF <xref:System.ServiceModel.ChannelFactory>; un **Aggiungi riferimento al servizio** esperienza è disponibile anche per Workflow Foundation che genera attività preconfigurate.  
  
### <a name="getting-started-with-messaging-activities"></a>Introduzione alle attività di messaggistica  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un progetto Applicazione di servizi flusso di lavoro WCF. Nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Pulsante destro del mouse sul progetto e scegliere **Aggiungi riferimento al servizio**.  Quindi fare clic su un servizio web esistente WSDL **OK**.  Compilare il progetto per mostrare le attività generate (implementate usando <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply>) nella casella degli strumenti.  
  
-   Esempi di queste attività sono disponibili nelle sezioni seguenti:  
  
    -   Basic: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Scenari: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
-   [Documentazione concettuale](https://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [Documentazione della finestra di progettazione di attività di messaggistica](https://go.microsoft.com/fwlink/?LinkId=204802)  
  
### <a name="messaging-activities-example-scenario"></a>Scenario di esempio relativo alle attività di messaggistica  
 Oggetto `BestPriceFinder` servizio chiama più servizi di compagnie aeree per trovare il prezzo migliore del biglietto per una route specifica.  Implementazione di questo scenario sarebbe necessario usare le attività di messaggistica per ricevere la richiesta di prezzo, recuperare i prezzi dai servizi di back-end e rispondere alla richiesta di prezzo con il prezzo migliore.  Sarebbe inoltre necessario utilizzare altre attività out-of-box per creare la logica di business per calcolare il prezzo migliore.  
  
## <a name="workflowservicehost"></a>WorkflowServiceHost  
 Il <xref:System.ServiceModel.WorkflowServiceHost> è l'host del flusso di lavoro out-of-box che supporta più istanze, configurazione e messaggistica WCF (anche se i flussi di lavoro non è necessari usare la messaggistica per consentire l'hosting).  Inoltre si integra con la persistenza, il rilevamento e il controllo dell'istanza tramite un set di comportamenti del servizio.  Analogamente di WCF <xref:System.ServiceModel.ServiceHost>, il <xref:System.ServiceModel.WorkflowServiceHost> possono essere self-hosted in un servizio di Windows o applicazione console/WinForms/WPF o ospitati su web (come file con estensione xamlx) in IIS o WAS.  
  
### <a name="getting-started-with-workflow-service-host"></a>Guida introduttiva all'host del servizio del flusso di lavoro  
  
-   In Visual Studio 2010, creare un progetto di applicazione del servizio del flusso di lavoro WCF: il progetto verrà impostato per usare <xref:System.ServiceModel.WorkflowServiceHost> in un ambiente host web.  
  
-   Per ospitare un flusso di lavoro non di messaggistica, aggiungere un <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> personalizzato che creerà l'istanza basata su un messaggio.  
  
-   Per controllare le istanze del flusso di lavoro (ad esempio sospeso o terminato), è possibile aggiungere un oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> a <xref:System.ServiceModel.WorkflowServiceHost> e successivamente utilizzare un <xref:System.ServiceModel.Activities.WorkflowControlClient>.  
  
-   Esempi di <xref:System.ServiceModel.WorkflowServiceHost> sono disponibili nelle sezioni seguenti:  
  
    -   [Esecuzione](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   Basic: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Scenari: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Applicazione: [sospesa la gestione delle istanze](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)  
  
-   [Documentazione concettuale su WorkflowServiceHost](https://go.microsoft.com/fwlink/?LinkId=204807)  
  
### <a name="workflowservicehost-scenario"></a>Scenario relativo a WorkflowServiceHost  
 Un servizio BestPriceFinder chiama più servizi di compagnie aeree per trovare il prezzo migliore del biglietto per una route specifica.  Implementazione di questo scenario sarebbe necessario ospitare il flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost>.  Utilizza inoltre le attività di messaggistica per ricevere la richiesta di prezzo, recuperare i prezzi dai servizi di back-end e rispondere alla richiesta di prezzo con il prezzo migliore.  
  
## <a name="correlation"></a>Correlazione  
 Una correlazione è una delle modalità seguenti:  
  
-   Una modalità di raggruppamento dei messaggi, ovvero la relazione tra un messaggio di richiesta e la sua risposta.  
  
-   Una modalità di mapping di un dato a un'istanza del servizio.  
  
### <a name="getting-started"></a>Introduzione  
  
-   Per iniziare a usare la correlazione, creare un nuovo progetto in Visual Studio. Creare una variabile di tipo <xref:System.ServiceModel.Activities.CorrelationHandle>.  
  
-   Un esempio di correlazione usata per raggruppare i messaggi è una correlazione Request-Reply che raggruppa i messaggi.  
  
    -   In un <xref:System.ServiceModel.Activities.Receive> attività, fare clic sui <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> proprietà e aggiungere un <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> usando il CorrelationHandle creato nel primo passaggio precedente.  
  
    -   Crea una <xref:System.ServiceModel.Activities.SendReply> attività facendo clic su di <xref:System.ServiceModel.Activities.Receive> e facendo clic su "Crea SendReply". Incollarla nel flusso di lavoro dopo l'attività <xref:System.ServiceModel.Activities.Receive>.  
  
-   Un esempio di mapping di un dato a un'istanza del servizio è una correlazione basata sul contenuto che associa un dato (ad esempio un ID ordine) a una determinata istanza del flusso di lavoro.  
  
    -   In un'attività di messaggistica qualsiasi, fare clic sulla proprietà `CorrelationInitializers` e aggiungere un <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> usando la variabile <xref:System.ServiceModel.Activities.CorrelationHandle> creata in precedenza. Nel messaggio fare doppio clic sulla proprietà desiderata (ad es. OrderID) dal menu a discesa. Impostare la proprietà `CorrelatesWith` sulla variabile <xref:System.ServiceModel.Activities.CorrelationHandle> usata in precedenza.  
  
-   Esempi:  
  
    -   Basic: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Scenari: [servizi](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   [Documentazione concettuale sulla correlazione](https://go.microsoft.com/fwlink/?LinkId=204939)  
  
### <a name="correlation-scenario"></a>Scenario relativo alla correlazione  
 Un flusso di lavoro di elaborazione ordini viene utilizzato per gestire la creazione di nuovi ordini e l'aggiornamento degli ordini esistenti nel processo.  Implementazione di questo scenario sarebbe necessario ospitare il flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> e usare le attività di messaggistica.  Sarebbe inoltre necessaria la correlazione basata sul `orderId` per garantire che gli aggiornamenti vengono eseguiti nel flusso di lavoro corretta.  
  
## <a name="simplified-configuration"></a>Configurazione semplificata  
 Lo schema di configurazione di WCF è complesso e fornisce agli utenti molte funzionalità difficilmente reperibili. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], Microsoft si è concentrata sull'aiutare gli utenti WCF configurare i servizi con le funzionalità seguenti:  
  
-   Eliminare la necessità della configurazione esplicita di ogni singolo servizio. Se non si configura qualsiasi \<servizio > elementi per il servizio e il servizio non definisce a livello di codice Nessun endpoint, quindi verrà aggiunto automaticamente un set di endpoint al servizio, uno per ogni indirizzo di base del servizio e per ogni contratto implementato dal servizio.  
  
-   Consentire all'utente di definire valori predefiniti per le associazioni e i comportamenti di WCF che verranno applicati ai servizi senza configurazione esplicita.  
  
-   Gli endpoint standard definiscono endpoint preconfigurati riutilizzabili, che dispongono di valori fissi per una o più delle proprietà dell'endpoint (indirizzo, associazione e contratto) e consentono la definizione di proprietà personalizzate.  
  
-   Infine, il <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> consente di eseguire operazioni di gestione centrale della configurazione del client WCF, utile in scenari in cui configurazione viene selezionata o modificata dopo il tempo di caricamento del dominio applicazione.  
  
### <a name="getting-started"></a>Introduzione  
  
-   [Una Guida per sviluppatori di WCF 4.0](https://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [Configurazione di una channel factory](https://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [Elemento Endpoint standard](https://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [Miglioramenti dei servizi configurazione in .net Framework 4](https://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [Errore comune dell'utente in .NET 4: errata digitazione del nome di configurazione del servizio WF/WCF](https://go.microsoft.com/fwlink/?LinkId=204944)  
  
### <a name="simplified-configuration-scenarios"></a>Scenari di configurazione semplificati  
  
-   Un sviluppatore ASMX esperto desidera iniziare a usare WCF. Tuttavia, WCF sembra essere molto complicato. In particolare per tutte le informazioni da scrivere in un file di configurazione. In .NET 4, è anche possibile decidere di non avere un file di configurazione.  
  
-   È molto difficile configurare e gestire un set di servizi WCF già esistente. Il file di configurazione è composto da migliaia di righe di codice XML ed è molto pericoloso modificarle. È necessario aiutare gli utenti a ridurre la quantità di codice per renderlo più maneggevole.  
  
## <a name="data-contract-resolver"></a>Resolver del contratto dati  
 In .NET 3.5, esistevano alcune limitazioni nella progettazione di tipi noti:  
  
-   Non era possibile aggiungere in modo dinamico tipi noti durante la serializzazione o la deserializzazione.  
  
-   I serializzatori non erano in grado di gestire le informazioni sconosciute su xsi:type.  
  
-   Gli utenti non potevano specificare quale xsi:type visualizzare sulla rete per ridurre, ad esempio, le dimensioni di un'istanza di serializzazione.  
  
 Il [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) risolve questi problemi in .NET 4.5.  
  
### <a name="getting-started"></a>Introduzione  
  
-   [Documentazione dell'API del Resolver di contratto dati](https://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [Introduzione al Resolver del contratto dati](https://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   Esempi:  
  
    -   [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [KnownAssemblyAttribute](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### <a name="data-contract-resolver-scenarios"></a>Scenari relativi al resolver del contratto dati  
  
-   Evitare di dichiarare decine di oggetti <xref:System.Runtime.Serialization.KnownTypeAttribute> in un servizio.  
  
-   Ridurre la dimensione del blob XML.  
  
## <a name="flowchart"></a>Diagramma di flusso  
 Il diagramma di flusso è uno noto paradigma per rappresentare visivamente i problemi di un dominio. In .NET 4 è stato introdotto un nuovo stile del flusso di controllo. Una delle caratteristiche principali del diagramma di flusso è quella di eseguire solo un'attività alla volta. I diagrammi di flusso possono rappresentare cicli e risultati alternativi, ma non possono rappresentare a livello nativo l'esecuzione simultanea di più nodi.  
  
### <a name="getting-started"></a>Introduzione  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un'applicazione console flusso di lavoro. Aggiungere un diagramma di flusso nella finestra di progettazione.  
  
-   La funzionalità diagramma di flusso usa le classi seguenti:  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   Esempi:  
  
    -   [Gestione errori in un'attività Flowchart usando TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [Scenario StateMachine usando una combinazione attività FlowChart e Pick](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [Processo di assunzione](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   Documentazione della finestra di progettazione:  
  
    -   [Activity Designer Flowchart](/visualstudio/workflow-designer/flowchart-activity-designers)  
  
### <a name="flowchart-scenarios"></a>Scenari relativi al diagramma di flusso  
 Un'attività del diagramma di flusso può essere usata per implementare un gioco per indovinare un numero. Il gioco è molto semplice: il computer seleziona un numero casuale e il giocatore deve indovinare il numero. Quando il giocatore invia ogni tentativo, il computer mostra un suggerimento (vale a dire "prova con un numero inferiore"). Se il giocatore indovina il numero in meno di 7 tentativi, viene visualizzato un messaggio di congratulazioni speciali. È possibile implementare questo gioco con una combinazione delle attività procedurali seguenti:  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Attività procedurali (Sequence, If, ForEach, Switch, Assign, DoWhile, While)  
 Le attività procedurali forniscono un meccanismo per modellare il flusso di controllo sequenziale usando concetti noti ai programmatori. Queste attività abilitano i costrutti del linguaggio di programmazione strutturati in modo tradizionale e, se opportuno, forniscono la parità di linguaggio con linguaggi procedurali comuni, ad esempio C#/VB.  
  
### <a name="getting-started"></a>Introduzione  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un'applicazione console flusso di lavoro. Aggiungere le attività procedurali nella finestra di progettazione del flusso di lavoro.  
  
-   Esempi:  
  
    -   [Processo di assunzione](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [Processo di acquisto aziendale](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   Documentazione della finestra di progettazione:  
  
    -   [Activity Designer Parallel](/visualstudio/workflow-designer/parallel-activity-designer)  
  
    -   [Attività ParallelForEach\<T > ActivityDesigner](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)  
  
### <a name="procedural-activity-scenarios"></a>Scenari relativi alle attività procedurali  
  
-   <xref:System.Activities.Statements.Parallel>: Un sistema di gestione intranet documento ha un flusso di lavoro di approvazione di documenti. Prima di poter essere pubblicati nella rete Intranet, i documenti devono essere approvati dai responsabili dei diversi reparti. Non c'è un ordine prestabilito per le approvazioni; possono verificarsi in qualsiasi momento mentre il documento è nella fase di "approvazione in sospeso". Quando un utente manda in revisione un documento, deve essere approvato dal suo responsabile diretto, dall'amministratore della rete Intranet e dal responsabile delle comunicazioni interne.  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>: Un'applicazione WF gestisce gli acquisti di una grande società. In base a quanto definito nei regolamenti aziendali, prima di pianificare qualsiasi operazione di acquisto è necessario valutare tre fornitori diversi. Un dipendente dell'ufficio acquisti seleziona tre fornitori dall'elenco fornitori della società. Una volta selezionati e informati i fornitori, la società attenderà le proposte economiche. Le proposte possono pervenire in qualsiasi ordine. Per implementare questo scenario in WF, viene usato <xref:System.Activities.Statements.ParallelForEach%601> per scorrere l'elenco dei fornitori e richiedere le proposte economiche. Una volta raccolte tutte le offerte, viene scelta e visualizzata la migliore.  
  
## <a name="invokemethod"></a>InvokeMethod  
 L'attività <xref:System.Activities.Statements.InvokeMethod> consente di richiamare metodi pubblici in oggetti o tipi nell'ambito. Supporta il richiamo di metodi di istanza e statici con o senza parametri (incluse le matrici di parametri) e metodi generici. Consente inoltre l'esecuzione del metodo in modo sincrono e asincrono.  
  
### <a name="getting-started"></a>Introduzione  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un'applicazione console flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.InvokeMethod> nella finestra di progettazione del flusso di lavoro e configurare i metodi di istanza e statici.  
  
-   Esempi:  
  
    -   [InvokeMethod](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   Documentazione della finestra di progettazione: [ActivityDesigner InvokeMethod](/visualstudio/workflow-designer/invokemethod-activity-designer)  
  
### <a name="invokemethod-scenarios"></a>Scenari relativi a InvokeMethod  
  
-   È necessario richiamare un metodo in un oggetto nell'ambito. Ad esempio, è necessario aggiungere un valore a un dizionario. Viene richiamato il metodo Add dell'istanza del dizionario e vengono forniti la chiave e il valore.  
  
-   È necessario richiamare un metodo su un oggetto CLR legacy. Anziché creare un'attività personalizzata per eseguire il wrapping della chiamata a quella classe legacy, è possibile usare <xref:System.Activities.Statements.InvokeMethod>, se rientra nell'ambito durante l'esecuzione del flusso di lavoro.  
  
## <a name="error-handling-activities"></a>Attività di gestione degli errori  
 L'attività <xref:System.Activities.Statements.TryCatch> fornisce un meccanismo per il rilevamento delle eccezioni che si verificano durante l'esecuzione di un set di attività contenute (simile al costrutto Try/Catch in C#/VB). <xref:System.Activities.Statements.TryCatch> fornisce la gestione delle eccezioni a livello di flusso di lavoro. Quando viene generata un'eccezione non gestita, il flusso di lavoro viene interrotto e non viene eseguito il blocco Finally. Questo comportamento è coerente con C#.  
  
### <a name="getting-started"></a>Introduzione  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un'applicazione console flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.TryCatch> nella finestra di progettazione del flusso di lavoro.  
  
-   Esempi:  
  
    1.  [Gestione errori in un'attività Flowchart usando TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [Uso di attività procedurali](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   Documentazione della finestra di progettazione: [Activity Designer Error Handling](/visualstudio/workflow-designer/error-handling-activity-designers)  
  
### <a name="error-handling-scenarios"></a>Scenari relativi alla gestione degli errori  
 È necessario eseguire un set di attività e, quando si verifica un errore, è necessario eseguire una logica specifica. Se durante l'esecuzione della logica di gestione degli errori si scopre che l'errore non è risolvibile, viene rigenerata l'eccezione e il problema viene gestito dall'attività padre (o dall'host).  
  
## <a name="pick-activity"></a>Attività Pick  
 L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di flusso di controllo basato sugli eventi in WF. L'attività <xref:System.Activities.Statements.Pick> contiene molti branch, la cui esecuzione è condizionata dal verificarsi di un particolare evento. In questa impostazione, <xref:System.Activities.Statements.Pick> si comporta in modo analogo a <xref:System.Activities.Statements.Switch%601>, ovvero l'attività esegue solo uno dei set di eventi in ascolto. Ogni ramo è basato sugli eventi e l'evento che si verifica per primo determina l'esecuzione del ramo corrispondente. Tutti gli altri rami vengono annullati e interrompono l'ascolto di altri eventi.  
  
### <a name="getting-started"></a>Introduzione  
  
-   In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un'applicazione console flusso di lavoro. Aggiungere un'attività <xref:System.Activities.Statements.Pick> nella finestra di progettazione del flusso di lavoro.  
  
-   Esempio: [utilizzo dell'attività Pick](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)  
  
-   Documentazione della finestra di progettazione: [ActivityDesigner Pick](/visualstudio/workflow-designer/pick-activity-designer)  
  
### <a name="pick-scenario"></a>Scenario relativo all'attività Pick  
 È necessario richiedere l'input di un utente. In circostanze normali, lo sviluppatore utilizzerebbe una chiamata al metodo come <xref:System.Console.ReadLine%2A> per richiedere l'input di un utente. Il problema di questa impostazione è che il programma attende fino a quando l'utente non immette un valore. In questo scenario, è necessario un timeout per sbloccare un'attività di blocco. Un scenario comune è quello in cui è necessario completare un'attività entro un periodo di tempo specificato. Il timeout di un'attività di blocco è uno scenario in cui l'attività Pick rappresenta un valore aggiunto.  
  
## <a name="wcf-routing-service"></a>Servizio di routing di WCF  
 Il servizio di Routing è progettato per essere un Router che è possibile controllare il flusso del WCFmessages tra i client e servizi software generiche.  Il servizio di Routing consente di disaccoppiare i client dai servizi, che ti offre maggiore libertà in termini di configurazioni che è possibile supportare e la flessibilità è necessario quando si considera come ospitare i servizi.  In .NET 3.5, i client e i servizi erano strettamente collegati; un client doveva conoscere tutti i servizi necessari per comunicare con e in cui è stati individuati. WCF in .NET Framework 3.5 aveva inoltre le limitazioni seguenti:  
  
-   La gestione degli errori era complessa, in quanto la logica doveva essere impostata come hardcoded nel client.  
  
-   I client e i servizi dovevano usare sempre le stesse associazioni.  
  
-   I servizi venivano adeguatamente diversificati molto raramente: è più facile far comunicare il client con un servizio che implementa tutto piuttosto che dover scegliere tra più servizi.  
  
 Il servizio di routing in .NET 4 è progettato per semplificare la risoluzione di questi problemi. Il nuovo servizio di routing offre le funzionalità seguenti:  
  
1.  Routing basato sul contenuto (gli oggetti<xref:System.ServiceModel.Dispatcher.MessageFilter> esaminano un messaggio per stabilire dove deve essere inviato).  
  
2.  Bridging del protocollo (trasporto e messaggio)  
  
3.  Gestione degli errori (il router intercetta le eccezioni di comunicazione ed esegue il failover sugli endpoint di backup)  
  
4.  Aggiornamento dinamico (in memoria) di <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> e configurazione del routing.  
  
### <a name="getting-started"></a>Introduzione  
  
1.  Documentazione: [Routing](../../../docs/framework/wcf/feature-details/routing.md)  
  
2.  Esempi: [servizi di Routing &#91;esempi di WCF&#93;](../../../docs/framework/wcf/samples/routing-services.md)  
  
3.  Blog: [le regole di Routing.](https://go.microsoft.com/fwlink/?LinkId=204956)  
  
### <a name="routing-scenarios"></a>Scenari di routing  
 Il servizio di routing è utile negli scenari seguenti:  
  
-   I client possono comunicare con più servizi senza doverli indirizzare tutti direttamente.  
  
-   I client possono eseguire una logica aggiuntiva su una richiesta del client per determinare dove indirizzarlo.  
  
-   È possibile decomporre le operazioni eseguite da un client in più implementazioni del servizio senza eseguire il refactoring del client.  
  
-   I client e i servizi possono supportare associazioni diverse con impostazioni di sicurezza diverse.  
  
-   È possibile rendere i client più affidabili in caso di guasto o indisponibilità dei servizi.  
  
## <a name="wcf-discovery"></a>WCF Discovery  
 WCF Discovery è una tecnologia di framework che consente di incorporare un meccanismo di individuazione per l'infrastruttura dell'applicazione. È possibile usarlo per rendere individuabile il servizio e configura i client per la ricerca dei servizi. Non è più necessario impostare i clienti come hardcoded con gli endpoint, pertanto l'applicazione è più affidabile e garantisce una maggiore tolleranza agli errori. Discovery è la piattaforma ideale per integrare funzionalità di configurazione automatica nell'applicazione.  
  
 Il prodotto si basa sullo standard WS-Discovery ed è progettato per essere interoperativo, estendibile e generico. Il prodotto supporta due modalità di funzionamento:  
  
1.  Gestito: se sulla rete esiste un'entità informata sui servizi esistenti, i client eseguono direttamente una query per ottenere le informazioni. È analogo ad Active Directory.  
  
2.  Ad hoc: in questa modalità i client usano messaggi multicast per individuare i servizi.  
  
 Inoltre, i messaggi di individuazione non riconoscono il protocollo di rete; è possibile usarli in aggiunta a qualsiasi protocollo che supporta i requisiti della modalità. Ad esempio, il rilevamento messaggi multicast possono essere inviati tramite il canale UDP o qualsiasi altra rete che supporta la messaggistica multicast.  Questi punti, combinati con flessibilità della funzionalità, è possibili adattare l'individuazione in modo specifico alla soluzione di progettazione.  
  
### <a name="getting-started"></a>Introduzione  
  
-   Documentazione: [WCF Discovery](../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
  
-   Esempi: [individuazione (esempi)](../../../docs/framework/wcf/samples/discovery-samples.md)  
  
### <a name="discovery-scenarios"></a>Scenari relativi all'individuazione  
 Un sviluppatore non desidera impostare gli endpoint come hardcoded, in quanto non è possibile sapere quando sarà disponibile il servizio. Al contrario, lo sviluppatore desidera scegliere un servizio in fase di runtime. I componenti dell'applicazione devono essere più separabili, più affidabili e autoconfigurabili.  
  
## <a name="tracking"></a>Rilevamento  
 Flusso di lavoro di rilevamento fornisce approfondimenti l'esecuzione di un'istanza del flusso di lavoro.  Gli eventi di rilevamento vengono generati da un flusso di lavoro a livello di istanza del flusso di lavoro e quando eseguono le attività all'interno del flusso di lavoro. Per sottoscrivere i record di rilevamento, è necessario aggiungere all'host del flusso di lavoro un partecipante del rilevamento del flusso di lavoro. I record di rilevamento vengono filtrati usando un profilo di rilevamento. .NET Framework fornisce un partecipante del rilevamento ETW (Event Tracing for Windows) e nel file machine.config. viene installato un profilo di base.  
  
### <a name="getting-started"></a>Introduzione  
  
1.  In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], creare un progetto Applicazione di servizi flusso di lavoro WCF. Inizialmente, nel canvas verrà posizionata la coppia <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.  
  
2.  Aprire web.config e aggiungere un comportamento di rilevamento ETW senza profilo.  
  
    1.  Viene usato il profilo predefinito.  
  
    2.  Aprire il Visualizzatore eventi e abilitare il canale analitico nel nodo seguente: **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows** , **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Attiva registro**.  
  
    3.  Eseguire il servizio del flusso di lavoro.  
  
    4.  Osservare gli eventi di rilevamento del flusso di lavoro nel visualizzatore eventi.  
  
3.  Esempi: [rilevamento](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)  
  
4.  Documentazione concettuale: [flusso di lavoro di rilevamento e traccia](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
  
## <a name="sql-workflow-instance-store"></a>Archivio di istanze del flusso di lavoro SQL  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> è un'implementazione basata su server SQL di un archivio di istanze. In un archivio di istanze è memorizzato lo stato di un'istanza in esecuzione nonché tutti i dati necessari per caricare e riprendere l'esecuzione di quell'istanza. L'host del servizio indica all'archivio di istanze di salvare lo stato dell'istanza se il flusso di lavoro è persistente e di caricare lo stato dell'istanza all'arrivo di un messaggio per quell'istanza o alla scadenza di un'attività di ritardo.  
  
### <a name="getting-started"></a>Introduzione  
  
1.  In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], creare un flusso di lavoro che contiene un'attività <xref:System.Activities.Statements.Persist> implicita o esplicita. Aggiungere il comportamento <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> all'host del servizio del flusso di lavoro. Questa operazione può essere eseguita nel codice o nel file di configurazione dell'applicazione.  
  
2.  Esempi: [persistenza](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)  
  
3.  Documentazione concettuale: [Store di istanza del flusso di lavoro SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).
