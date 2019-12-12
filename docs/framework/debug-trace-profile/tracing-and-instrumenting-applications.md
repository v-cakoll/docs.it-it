---
title: Traccia e strumentazione di applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework]
- debugging [.NET Framework], instrumentation
- performance monitoring, instrumentation
- instrumentation, about instrumentation
- tracing [.NET Framework], about tracing
- performance monitoring, tracing code
- Trace class, instrumentation for .NET applications
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9e1b8d5cb25445ffc3ce08e8c73e1d3742067e21
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196715"
---
# <a name="tracing-and-instrumenting-applications"></a>Traccia e strumentazione di applicazioni
La traccia consente di monitorare l'esecuzione dell'applicazione mentre è in corso. È possibile aggiungere strumentazione di traccia e debug all'applicazione .NET Framework quando la si sviluppa e usare tale strumentazione sia mentre si sviluppa l'applicazione sia dopo la distribuzione. È possibile usare le classi <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug?displayProperty=nameWithType> e <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> per registrare le informazioni sugli errori e sull'esecuzione dell'applicazione in log, file di testo o altri dispositivi per un'analisi successiva.  
  
 Il termine *strumentazione* si riferisce alla possibilità di monitorare o misurare il livello di prestazioni di un prodotto e di diagnosticare gli errori. In programmazione, ciò significa la capacità di un'applicazione di incorporare:  
  
- **Traccia del codice** - Ricezione di messaggi informativi sull'esecuzione di un'applicazione in fase di esecuzione.  
  
- **Debug** - Rilevamento e correzione di errori di programmazione in un'applicazione in fase di sviluppo. Per altre informazioni, vedere [Debug](/visualstudio/debugger/debugger-feature-tour).  
  
- **Contatori delle prestazioni** - Componenti che consentono di tenere traccia delle prestazioni dell'applicazione. Per altre informazioni, vedere [Contatori delle prestazioni](performance-counters.md).  
  
- **Log eventi** - Componenti che consentono di ricevere e registrare i principali eventi durante l'esecuzione dell'applicazione. Per altre informazioni, vedere la classe <xref:System.Diagnostics.EventLog>.  
  
 La strumentazione dell'applicazione inserendo istruzioni di traccia in posizioni strategiche nel codice è particolarmente utile per le applicazioni distribuite. Usando istruzioni di traccia, è possibile instrumentare un'applicazione non solo per visualizzare informazioni in caso di problemi, ma anche per monitorare le prestazioni dell'applicazione.  
  
 La classe <xref:System.Diagnostics.TraceSource> fornisce funzionalità di traccia avanzate e può essere usata al posto dei metodi statici delle versioni precedenti delle classi di traccia <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug>. Le familiari classi <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug> vengono ancora ampiamente usate, ma la classe <xref:System.Diagnostics.TraceSource> è consigliata per i nuovi comandi di traccia, ad esempio <xref:System.Diagnostics.TraceSource.TraceEvent%2A> e <xref:System.Diagnostics.TraceSource.TraceData%2A>.  
  
 Le classi <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug> sono identiche, ad eccezione del fatto che le routine e le funzioni della classe <xref:System.Diagnostics.Trace> vengono compilate per impostazione predefinita nelle build di rilascio, mentre quelle della classe <xref:System.Diagnostics.Debug> no.  
  
 Le classi <xref:System.Diagnostics.Trace> e <xref:System.Diagnostics.Debug> consentono di monitorare ed esaminare le prestazioni dell'applicazione durante lo sviluppo o dopo la distribuzione. È ad esempio possibile utilizzare la classe <xref:System.Diagnostics.Trace> per tenere traccia di particolari tipi di azioni all'interno di un'applicazione distribuita man mano che si verificano (ad esempio la creazione di nuove connessioni a database) e monitorare quindi l'efficienza dell'applicazione.  
  
## <a name="code-tracing-and-debugging"></a>Traccia e debug del codice  
 Nella fase di sviluppo è possibile usare i metodi di output della classe <xref:System.Diagnostics.Debug> per visualizzare messaggi nella finestra di output dell'ambiente di sviluppo integrato (IDE) di Visual Studio. Ad esempio:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
```  
  
 In ciascuno di questi esempi viene visualizzato "Hello World!" nella finestra di output quando l'applicazione viene eseguita nel debugger.  
  
 Ciò consente di eseguire il debug delle applicazioni e ottimizzarne le prestazioni in base al relativo comportamento nell'ambiente di test. Il debug dell'applicazione può essere eseguito nella build di debug, attivando l'attributo condizionale <xref:System.Diagnostics.Debug> in modo da ricevere tutto l'output di debug. Quando l'applicazione è pronta per il rilascio, è possibile compilare la build di rilascio senza attivare l'attributo condizionale <xref:System.Diagnostics.Debug>, in modo che tramite il compilatore il codice di debug non venga incluso nell'eseguibile finale. Per altre informazioni, vedere [Procedura: Compilare in modo condizionale con traccia e debug](how-to-compile-conditionally-with-trace-and-debug.md). Per altre informazioni sulle diverse configurazioni di compilazione per l'applicazione, vedere [Compilazione e creazione](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
 È anche possibile tracciare l'esecuzione del codice in un'applicazione installata, usando i metodi della classe <xref:System.Diagnostics.Trace>. Inserendo [opzioni di traccia](trace-switches.md) nel codice, è possibile controllare l'esecuzione e l'entità della traccia. Ciò consente di monitorare lo stato dell'applicazione in un ambiente di produzione. Questo aspetto è particolarmente importante in un'applicazione aziendale che usa più componenti in esecuzione in più computer. È possibile controllare la modalità di utilizzo delle opzioni dopo la distribuzione tramite il file di configurazione. Per altre informazioni, vedere [Procedura: Creare, inizializzare e configurare opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Quando si sviluppa un'applicazione per la quale si prevede di usare la traccia, in genere si includono nel codice dell'applicazione sia i messaggi di traccia sia quelli di debug. Quando si è pronti per distribuire l'applicazione, è possibile compilare la build di rilascio senza attivare l'attributo condizionale **Debug**. È tuttavia possibile attivare l'attributo condizionale **Trace**, in modo che il compilatore includa il codice di traccia nel file eseguibile. Per altre informazioni, vedere [Procedura: Compilare in modo condizionale con traccia e debug](how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Fasi di traccia del codice  
 La traccia del codice comprende tre fasi:  
  
1. **Strumentazione**: il codice di traccia viene aggiunto all'applicazione.  
  
2. **Traccia**: il codice di traccia scrive le informazioni nella destinazione specificata.  
  
3. **Analisi**: le informazioni di traccia vengono valutate per identificare e comprendere i problemi dell'applicazione.  
  
 Durante lo sviluppo, tutti i metodi di output di traccia e debug scrivono informazioni nella finestra di output di Visual Studio per impostazione predefinita. In un'applicazione distribuita, i metodi scrivono le informazioni di traccia nelle destinazioni specificate. Per altre informazioni su come specificare una destinazione di output per la traccia o il debug, vedere [Listener di traccia](trace-listeners.md).  
  
 Di seguito è illustrata una panoramica dei passaggi principali eseguiti in genere per usare la traccia per analizzare e correggere i problemi potenziali nelle applicazioni distribuite. Per altre informazioni su come eseguire questi passaggi, fare clic sul collegamento appropriato.  
  
##### <a name="to-use-tracing-in-an-application"></a>Per usare la traccia in un'applicazione  
  
1. Determinare l'output di traccia che si desidera ricevere dopo aver distribuito l'applicazione.  
  
2. Creare un set di opzioni. Per altre informazioni, vedere [Procedura: Configurare le opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md).  
  
3. Aggiungere istruzioni di traccia al codice dell'applicazione.  
  
4. Determinare dove si desidera visualizzare l'output di traccia e aggiungere i listener appropriati. Per altre informazioni, vedere [Creazione e inizializzazione di listener di traccia](how-to-create-and-initialize-trace-listeners.md).  
  
5. Eseguire il test e il debug dell'applicazione e del codice di traccia contenuto.  
  
6. Compilare l'applicazione nel codice eseguibile usando una delle procedure seguenti:  
  
    - Usare il menu **Compila** con la pagina **Debug** della finestra di dialogo **Pagine delle proprietà** in **Esplora soluzioni**. Usare questa opzione quando si esegue la compilazione in Visual Studio.  
  
         \- oppure -  
  
    - Usare le direttive del compilatore **Trace** e **Debug** per il metodo di compilazione dalla riga di comando. Per altre informazioni, vedere [Compilazione condizionale con analisi e debug](how-to-compile-conditionally-with-trace-and-debug.md). Usare questa opzione quando si compila dalla riga di comando.  
  
7. Se si verifica un problema in fase di esecuzione, attivare l'opzione di traccia appropriata. Per altre informazioni, vedere [Configurazione delle opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md).  
  
     Il codice di traccia scrive i messaggi di traccia in una destinazione specificata, ad esempio sullo schermo, in un file di testo o in un log eventi. Il tipo di listener incluso nella raccolta **Trace.Listeners** determina la destinazione.  
  
8. Analizzare i messaggi di traccia per identificare e comprendere il problema nell'applicazione.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Strumentazione della traccia e applicazioni distribuite  
 Quando si crea un'applicazione distribuita, può risultare difficile testare l'applicazione nel modo in cui verrà usata. Pochi team di sviluppo sono in grado di verificare tutte le possibili combinazioni di sistemi operativi o Web browser (incluse tutte le opzioni di lingua localizzate) o di simulare l'elevato numero di utenti che accederanno all'applicazione contemporaneamente. In questi casi, non è possibile verificare in che modo risponderà un'applicazione distribuita in caso di volumi elevati, installazioni diverse e comportamenti univoci degli utenti finali. Numerose parti di un'applicazione distribuita, inoltre, non dispongono di un'interfaccia utente con cui è possibile interagire direttamente o visualizzare l'attività di tali parti.  
  
 È tuttavia possibile rimediare a questa mancanza consentendo alle applicazioni distribuite di descrivere determinati eventi di interesse per gli amministratori di sistema, in particolare in caso di problemi, tramite *strumentazione* dell'applicazione, ovvero inserendo istruzioni di traccia in posizioni strategiche nel codice. Se quindi si verifica un evento imprevisto in fase di esecuzione (ad esempio tempi di risposta eccessivamente lenti), è possibile determinare la causa più probabile.  
  
 Con le istruzioni di traccia, è possibile evitare le complesse attività di analisi del codice sorgente originale, modifica, ricompilazione e tentativo di generare l'errore di run-time all'interno nell'ambiente di debug. Tenere presente che è possibile instrumentare un'applicazione non solo per visualizzare gli errori, ma anche per monitorare le prestazioni.  
  
## <a name="strategic-placement-of-trace-statements"></a>Posizionamento strategico delle istruzioni di traccia  
 È necessario prestare particolare attenzione durante il posizionamento delle istruzioni di traccia da usare in fase di esecuzione. È necessario valutare quali informazioni di traccia saranno necessarie in un'applicazione distribuita, in modo da includere tutti gli scenari di traccia probabili. Poiché le applicazioni che usano la traccia variano notevolmente, tuttavia, non vi sono linee guida generali per il posizionamento strategico della traccia. Per ulteriori informazioni sull'inserimento delle istruzioni di traccia, vedere [procedura: Aggiungere istruzioni di traccia al codice dell'applicazione](how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Output della traccia  
 L'output di traccia viene raccolto da oggetti denominati *listener*. Un listener è un oggetto che riceve l'output di traccia e lo scrive in un dispositivo di output (in genere una finestra, un log o un file di testo). Quando viene creato un listener di traccia, viene in genere aggiunto alla raccolta di proprietà <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>, in modo che possa ricevere tutti gli output di traccia.  
  
 Le informazioni sulla traccia vengono sempre scritte almeno nella destinazione di output predefinita dell'oggetto <xref:System.Diagnostics.Trace>, cioè <xref:System.Diagnostics.DefaultTraceListener>. Se per qualche ragione è stato eliminato l'oggetto <xref:System.Diagnostics.DefaultTraceListener> senza aggiungere altri listener alla raccolta di proprietà <xref:System.Diagnostics.Trace.Listeners%2A>, non verrà ricevuto alcun messaggio di traccia. Per altre informazioni, vedere [Listener di traccia](trace-listeners.md).  
  
 I sei membri <xref:System.Diagnostics.Debug> e metodi <xref:System.Diagnostics.Trace> tramite i quali vengono scritte informazioni sulla traccia sono elencati nella tabella riportata di seguito.  
  
|Metodo|Output|  
|------------|------------|  
|**Assert**|Il testo specificato oppure, se non è specificato, lo stack di chiamate. L'output viene scritto solo se la condizione specificata come argomento nell'istruzione **Assert** è **false**.|  
|**Fail**|Il testo specificato oppure, se non è specificato, lo stack di chiamate.|  
|**Write**|Il testo specificato.|  
|**WriteIf**|Il testo specificato, se la condizione specificata come argomento nell'istruzione **WriteIf** viene soddisfatta.|  
|**WriteLine**|Il testo specificato e un ritorno a capo.|  
|**WriteLineIf**|Il testo specificato e un ritorno a capo, se la condizione specificata come argomento nell'istruzione **WriteLineIf** viene soddisfatta.|  
  
 I messaggi descritti nella tabella precedente vengono ricevuti da tutti i listener nella raccolta di proprietà <xref:System.Diagnostics.Trace.Listeners%2A>, ma le azioni intraprese possono variare in base al tipo di listener che riceve il messaggio. Ad esempio, nell'oggetto <xref:System.Diagnostics.DefaultTraceListener> viene visualizzata una finestra di dialogo di asserzione quando viene ricevuta una notifica **Fail** o **Assert** non riuscita, mentre un oggetto <xref:System.Diagnostics.TextWriterTraceListener> scrive semplicemente l'output nel relativo flusso.  
  
 È possibile produrre risultati personalizzati implementando un listener personalizzato. Un listener di traccia personalizzato potrebbe, ad esempio, visualizzare i messaggi in una finestra di messaggio o connettersi a un database per aggiungere messaggi a una tabella. Tutti i listener personalizzati devono supportare i sei metodi indicati in precedenza. Per altre informazioni sulla creazione di listener definiti dallo sviluppatore, vedere <xref:System.Diagnostics.TraceListener> negli argomenti di riferimento su .NET Framework.  
  
 I metodi **Write** e **WriteLine** scrivono sempre il testo specificato. Per **Assert**, **WriteIf** e **WriteLineIf** è richiesto un argomento booleano tramite cui viene controllato se viene scritto o meno il testo specificato. Questa operazione viene eseguita solo se l'espressione è **true** (per **WriteIf** e **WriteLineIf**) o **false** (per **Assert**). Il metodo **Fail** scrive sempre il testo specificato. Per altre informazioni, vedere [Procedura: Aggiungere istruzioni di traccia al codice dell'applicazione](how-to-add-trace-statements-to-application-code.md) e il riferimento .NET Framework.  
  
## <a name="security-concerns"></a>Problemi di sicurezza  
 Se non si disabilitano la traccia e il debug prima di distribuire un'applicazione ASP.NET, l'applicazione può rivelare informazioni su se stessa che potrebbero venire sfruttate da un programma dannoso. Per altre informazioni, vedere [Procedura: Compila in modo condizionale con traccia e debug](how-to-compile-conditionally-with-trace-and-debug.md), [compilazione e compilazione](/visualstudio/ide/compiling-and-building-in-visual-studio)e [procedura: Creare, inizializzare e configurare opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md). Il debug può essere configurato anche tramite Internet Information Services (IIS).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- [Contratti di codice](code-contracts.md)
- [Tipi di progetto C#, F# e Visual Basic](/visualstudio/debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types)
- [Procedura: Aggiungere istruzioni di traccia al codice dell'applicazione](how-to-add-trace-statements-to-application-code.md)
- [Procedura: Compilare in modo condizionale con traccia e debug](how-to-compile-conditionally-with-trace-and-debug.md)
- [Procedura: Creare, inizializzare e configurare opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md)
- [Procedura: Creare e inizializzare origini di traccia](how-to-create-and-initialize-trace-sources.md)
- [Procedura: Usare TraceSource e i filtri con i listener di traccia](how-to-use-tracesource-and-filters-with-trace-listeners.md)
- [Listener di traccia](trace-listeners.md)
- [Opzioni di traccia](trace-switches.md)
