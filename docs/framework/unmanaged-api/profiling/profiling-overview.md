---
title: Cenni preliminari sulla profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- managed code, profiling API support
- unmanaged code, combining with managed code in profiling
- notification threads [.NET Framework profiling]
- unmanaged code, profiling
- profiling API [.NET Framework], and COM
- profiling API [.NET Framework], unmanaged code profiling
- profilers, writing
- profiling API [.NET Framework], call stacks
- code profilers, writing
- profiling API [.NET Framework], security considerations
- profiling API [.NET Framework], managed code support
- common language runtime, profiling
- profiling API [.NET Framework], notification threads
- call stacks [.NET Framework profiling]
- profiling API [.NET Framework], stack depth
- common language runtime, writing a profiler
- profiling API [.NET Framework], information retrieval interfaces
- shadow stacks [.NET Framework profiling]
- COM, using in the profiling API
- stack snapshots [.NET Framework profiling]
- profiling API [.NET Framework], supported features
- profiling API [.NET Framework], overview
- security, profiling API considerations
- stack depth [.NET Framework profiling]
ms.assetid: 864c2344-71dc-46f9-96b2-ed59fb6427a8
ms.openlocfilehash: aa8bff374e9698d4b7e032428ec1bdc66901e05d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860915"
---
# <a name="profiling-overview"></a>Cenni preliminari sulla profilatura

Un profiler è un strumento che monitora l'esecuzione di un'altra applicazione. Un profiler CLR (Common Language Runtime) è una DLL costituita da funzioni che ricevono e inviano messaggi a CLR usando l'API di profilatura. La DLL del profiler viene caricata in fase di esecuzione da CLR.

Gli strumenti di profilatura tradizionali si basano sulla misurazione dell'esecuzione dell'applicazione, ovvero del tempo impiegato da ciascuna funzione oppure dell'utilizzo della memoria nel tempo da parte dell'applicazione. L'API di profilatura fa riferimento a una classe più ampia di strumenti di diagnostica, quali utilità di code coverage e persino supporti di debug avanzati, tutti usati per fini diagnostici. L'API di profilatura non si limita a misurare l'esecuzione di un'applicazione, ne esegue anche il monitoraggio. Per questa ragione, non deve mai essere usata dall'applicazione stessa e l'esecuzione dell'applicazione non deve dipendere dal profiler (né esserne influenzata).

La profilatura di un'applicazione CLR richiede un maggiore supporto rispetto all'analisi del codice macchina compilato in modo tradizionale, in quanto CLR introduce concetti quali domini applicazione, Garbage Collection, gestione delle eccezioni gestite, compilazione del codice JIT (tramite la conversione del codice MSIL in codice macchina nativo) e funzionalità simili. I meccanismi di profilatura convenzionali non sono in grado di identificare o fornire informazioni utili su queste funzionalità. L'API di profilatura fornisce queste informazioni mancanti in modo efficiente, con un impatto minimo sulle prestazioni di CLR e dell'applicazione sottoposta a profilatura.

La compilazione JIT in fase di esecuzione offre buone possibilità di profilatura. L'API di profilatura consente a un profiler di modificare il flusso di codice MSIL in memoria per una routine prima che venga compilato tramite JIT. In tal modo, il profiler può aggiungere dinamicamente codice di strumentazione a routine specifiche per le quali è richiesta un'indagine più approfondita. Sebbene questo approccio sia possibile negli scenari convenzionali, è molto più semplice da implementare per CLR usando l'API di profilatura.

## <a name="the-profiling-api"></a>API di profilatura

In genere, l'API di profilatura viene usata per scrivere una *Code Profiler*, ovvero un programma che monitora l'esecuzione di un'applicazione gestita.

L'API di profilatura viene usata da una DLL del profiler caricata nello stesso processo dell'applicazione che si sta profilando. La DLL del profiler implementa un'interfaccia di callback ([ICorProfilerCallback](icorprofilercallback-interface.md) in .NET Framework versione 1,0 e 1,1, [ICorProfilerCallback2](icorprofilercallback2-interface.md) nella versione 2,0 e successive). CLR chiama i metodi in tale interfaccia per notificare al profiler gli eventi nel processo profilato. Il profiler può richiamare il runtime usando i metodi nelle interfacce [ICorProfilerInfo](icorprofilerinfo-interface.md) e [ICorProfilerInfo2](icorprofilerinfo2-interface.md) per ottenere informazioni sullo stato dell'applicazione sottoposta a profilatura.

> [!NOTE]
> Solo la parte della soluzione del profiler relativa alla raccolta dei dati deve essere in esecuzione nello stesso processo dell'applicazione profilata. L'interfaccia utente e l'analisi dei dati devono essere eseguite in un processo separato.

La figura seguente mostra la modalità di interazione della DLL del profiler con l'applicazione che si sta profilando e con CLR.

![Screenshot che mostra l'architettura di profilatura.](./media/profiling-overview/profiling-architecture.png)

### <a name="the-notification-interfaces"></a>Interfacce di notifica

[ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback2](icorprofilercallback2-interface.md) possono essere considerati interfacce di notifica. Queste interfacce sono costituite da metodi come [ClassLoadStarted](icorprofilercallback-classloadstarted-method.md), [ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)e [JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md). Ogni volta che CLR carica o scarica una classe, compila una funzione e così via, chiama il metodo corrispondente nell'interfaccia `ICorProfilerCallback` o `ICorProfilerCallback2` del profiler.

Un profiler, ad esempio, può misurare le prestazioni del codice tramite due funzioni di notifica: [FunctionEnter2](functionenter2-function.md) e [FunctionLeave2](functionleave2-function.md). Il profiler imposta un timestamp per ogni notifica, accumula risultati e restituisce un elenco in cui sono indicate le funzioni che hanno usato maggiormente la CPU o che hanno richiesto più tempo durante l'esecuzione dell'applicazione.

### <a name="the-information-retrieval-interfaces"></a>Interfacce di recupero delle informazioni

Le altre interfacce principali necessarie per la profilatura sono [ICorProfilerInfo](icorprofilerinfo-interface.md) e [ICorProfilerInfo2](icorprofilerinfo2-interface.md). Il profiler chiama queste interfacce secondo necessità per ottenere una maggiore quantità di informazioni per l'analisi. Ad esempio, ogni volta che CLR chiama la funzione [FunctionEnter2](functionenter2-function.md) , fornisce un identificatore di funzione. Il profiler può ottenere altre informazioni su tale funzione chiamando il metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) per individuare la classe padre della funzione, il nome e così via.

## <a name="supported-features"></a>Funzionalità supportate

L'API di profilatura fornisce informazioni su diversi eventi e azioni che si verificano in Common Language Runtime. È possibile usare tali informazioni per monitorare il funzionamento interno dei processi e analizzare le prestazioni dell'applicazione .NET Framework in uso.

L'API di profilatura recupera le informazioni sulle azioni e sugli eventi che si verificano in CLR riportati di seguito:

- Eventi di avvio e arresto di CLR.

- Eventi di creazione e arresto di domini applicazione.

- Eventi di caricamento e scaricamento di assembly.

- Eventi di caricamento e scaricamento di moduli.

- Eventi di creazione e distruzione di vtable COM.

- Eventi di compilazione JIT e di code pitching.

- Eventi di caricamento e scaricamento di classi.

- Eventi di creazione e distruzione di thread.

- Eventi di entrata e uscita delle funzioni.

- Eccezioni.

- Transizioni tra l'esecuzione di codice gestito e non gestito.

- Transizioni tra contesti di runtime diversi.

- Informazioni sulle sospensioni del runtime.

- Informazioni sull'heap della memoria del runtime e sull'attività di Garbage Collection.

L'API di profilatura può essere chiamata da qualsiasi linguaggio compatibile con COM (non gestito).

Dal punto di vista del consumo di CPU e della memoria, l'API si rivela efficiente. La profilatura non comporta modifiche all'applicazione profilata di importanza tale da provocare risultati fuorvianti.

L'API di profilatura è utile sia per i profiler di campionamento, sia per i profiler non di campionamento. Un *Profiler di campionamento* controlla il profilo con tick di clock regolari, ad eccezione di 5 millisecondi. Un *Profiler non di campionamento* viene informato in modo sincrono di un evento con il thread che genera l'evento.

### <a name="unsupported-functionality"></a>Funzionalità non supportata

L'API di profilatura non supporta le funzionalità descritte di seguito:

- Codice non gestito, che deve essere profilato usando i metodi Win32 convenzionali. Tuttavia, il profiler CLR include eventi di transizione che consentono di determinare i limiti fra codice gestito e non gestito.

- Applicazioni automodificanti, che modificano il proprio codice per scopi quali la programmazione orientata agli aspetti.

- Verifica dei limiti, in quanto l'API di profilatura non fornisce queste informazioni. CLR fornisce il supporto intrinseco per la verifica dei limiti di tutto il codice gestito.

- Profilatura remota, non supportata per i motivi seguenti:

  - La profilatura remota estende il tempo di esecuzione. Quando si usano le interfacce di profilatura, è necessario ridurre al minimo il tempo di esecuzione in modo da non influire eccessivamente sui risultati, soprattutto durante il monitoraggio delle prestazioni di esecuzione. Tuttavia, la profilatura remota non costituisce una limitazione quando le interfacce di profilatura vengono usate per monitorare l'utilizzo della memoria o per ottenere informazioni di runtime sugli stack frame, sugli oggetti e così via.

  - Il Code Profiler di CLR deve registrare una o più interfacce di callback con il runtime sul computer locale su cui è in esecuzione l'applicazione profilata. In tal modo la capacità di creare un Code Profiler remoto viene limitata.

- Profilatura negli ambienti di produzione con requisiti di disponibilità elevata. L'API di profilatura è stata creata per supportare la diagnostica in fase di sviluppo. Non è stata sottoposta ai test accurati richiesti per il supporto degli ambienti di produzione.

## <a name="notification-threads"></a>Thread di notifica

Nella maggior parte dei casi, il thread che genera un evento esegue anche notifiche. Tali notifiche, ad esempio [FunctionEnter](functionenter-function.md) e [FunctionLeave](functionleave-function.md), non devono fornire il `ThreadID`esplicito. Inoltre, il profiler potrebbe usare la memoria locale del thread per archiviare e aggiornare i blocchi delle analisi anziché indicizzarli in un archivio globale, basato sul `ThreadID` del thread interessato.

Questi callback non sono serializzati. Gli utenti dovranno proteggere il codice creando strutture dei dati thread-safe e bloccando il codice del profiler dove necessario, per impedire l'accesso parallelo da più thread. Pertanto, in certi casi è possibile ricevere una sequenza insolita di callback. Ad esempio, si supponga che un'applicazione gestita generi due thread che eseguono codice identico. In questo caso, è possibile ricevere un evento [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) per alcune funzioni da un thread e un callback `FunctionEnter` dall'altro thread prima di ricevere il callback [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) . In questo caso, l'utente riceverà un callback `FunctionEnter` per una funzione che potrebbe non essere ancora stata completamente compilata tramite JIT.

## <a name="security"></a>Sicurezza -

Una DLL del profiler è una DLL non gestita che viene eseguita parte del motore di Common Language Runtime. Di conseguenza, il codice nella DLL del profiler non è soggetto alle restrizioni di sicurezza dall'accesso di codice gestito. Le uniche limitazioni relative alla DLL del profiler sono quelle imposte dal sistema operativo all'utente che sta eseguendo l'applicazione profilata.

Per evitare problemi relativi alla sicurezza, gli autori del profiler devono adottare le precauzioni appropriate. Ad esempio, durante l'installazione, è necessario aggiungere la DLL di un profiler a un elenco di controllo di accesso (ACL), in modo da renderne impossibile la modifica da parte di un utente malintenzionato.

## <a name="combining-managed-and-unmanaged-code-in-a-code-profiler"></a>Combinazione di codice gestito e non gestito in un Code Profiler

La scrittura non corretta di un profiler può provocare dei riferimenti circolari, che determinano un comportamento imprevedibile.

Una verifica dell'API di profilatura di CLR potrebbe dare l'impressione che sia possibile scrivere un profiler contenente componenti gestiti e non gestiti che comunicano tra loro mediante l'interoperabilità COM o chiamate indirette.

Sebbene sia possibile dal punto di vista della progettazione, l'API di profilatura non supporta i componenti gestiti. Un profiler CLR deve essere completamente non gestito. Tentativi di combinare codice gestito e codice non gestito in un profiler CLR possono provocare violazioni di accesso, errori di esecuzione del programma o deadlock. I componenti gestiti del profiler genererebbero eventi nei relativi componenti non gestiti, che a loro volta effettuerebbero chiamate ai componenti gestiti, dando origine a riferimenti circolari.

L'unico percorso in cui un profiler CLR può chiamare in modo sicuro il codice gestito è il corpo di un metodo in codice MSIL (Microsoft Intermediate Language). La procedura consigliata per modificare il corpo MSIL consiste nell'utilizzare i metodi di ricompilazione JIT nell'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) .

È anche possibile utilizzare i metodi di strumentazione precedenti per modificare MSIL. Prima che venga completata la compilazione JIT di una funzione, il profiler può inserire chiamate gestite nel corpo MSIL di un metodo e quindi compilarlo in modo JIT (vedere il metodo [ICorProfilerInfo:: GetILFunctionBody](icorprofilerinfo-getilfunctionbody-method.md) ). Questa tecnica può essere usata, con buoni risultati, per la strumentazione selettiva di codice gestito oppure per la raccolta di statistiche e dati sulle prestazioni relativi a JIT.

In alternativa, un Code Profiler può inserire hook nativi nel corpo MSIL di ogni funzione gestita che effettua chiamate nel codice non gestito. Questa tecnica può essere usata per la strumentazione e il code coverage. Ad esempio, un Code Profiler potrebbe inserire degli hook di strumentazione dopo ogni blocco di codice MSIL per garantire l'esecuzione del blocco. La modifica del corpo MSIL di un metodo è un'operazione molto delicata ed è necessario prendere in considerazione molteplici fattori.

## <a name="profiling-unmanaged-code"></a>Profilatura del codice non gestito

L'API di profilatura di Common Language Runtime fornisce il supporto minimo per la profilatura di codice non gestito. Sono disponibili le funzionalità seguenti:

- Enumerazione delle catene dello stack. Questa funzionalità consente a un Code Profiler di determinare il limite tra codice gestito e codice non gestito.

- Determinazione della corrispondenza di una catena dello stack a un codice gestito o a un codice nativo.

In .NET Framework versioni 1.0 e 1.1, questi metodi sono disponibili tramite il subset in-process dell'API di debug di Common Language Runtime. Sono definiti nel file CorDebug.idl.

In .NET Framework 2,0 e versioni successive, è possibile usare il metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) per questa funzionalità.

## <a name="using-com"></a>Uso di COM

Sebbene le interfacce di profilatura vengano definite come interfacce COM, Common Language Runtime non inizializza effettivamente COM per usarle. Il motivo è evitare di dover impostare il modello di threading utilizzando la funzione [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize) prima che l'applicazione gestita abbia la possibilità di specificare il modello di threading desiderato. Analogamente, il profiler non deve chiamare la funzione `CoInitialize`, perché potrebbe scegliere un modello di threading non compatibile con l'applicazione profilata e comprometterne l'esecuzione.

## <a name="call-stacks"></a>Stack di chiamate

L'API di profilatura fornisce due modalità per ottenere gli stack di chiamate: un metodo basato sullo snapshot dello stack, che consente la raccolta di tipo sparse degli stack di chiamate, e un metodo basato sullo shadow stack, che registra lo stack di chiamate in ogni istante.

### <a name="stack-snapshot"></a>Snapshot dello stack

Uno snapshot dello stack è una traccia dello stack di un thread in un istante di tempo. L'API di profilatura supporta l'analisi di funzioni gestite nello stack, ma lascia l'analisi delle funzioni non gestite alla funzione di verifica del percorso chiamate nello stack del profiler.

Per ulteriori informazioni sulla modalità di programmazione del profiler per l'analisi degli stack gestiti, vedere il metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) in questo set di documentazione e [analisi dello stack del profiler nel .NET Framework 2,0: Nozioni fondamentali e oltre](https://docs.microsoft.com/previous-versions/dotnet/articles/bb264782(v=msdn.10)).

### <a name="shadow-stack"></a>Shadow stack

Un uso troppo frequente del metodo basato sullo snapshot può creare rapidamente un problema di prestazioni. Se si desidera eseguire le analisi dello stack di frequente, è necessario che il Profiler crei uno shadow stack usando i callback di eccezione [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), [FunctionTailcall2](functiontailcall2-function.md)e [ICorProfilerCallback2](icorprofilercallback2-interface.md) . Lo shadow stack è sempre aggiornato e può essere rapidamente copiato in un'area di archiviazione quando è necessario uno snapshot dello stack.

Uno shadow stack può ottenere argomenti della funzione, valori restituiti e informazioni sulle creazioni di istanze generiche. Queste informazioni sono disponibili solo tramite lo shadow stack e possono essere ottenute quando il controllo viene passato a una funzione. Tuttavia, queste informazioni potrebbero non essere disponibili in un secondo momento, durante l'esecuzione della funzione.

## <a name="callbacks-and-stack-depth"></a>Callback e profondità dello stack

I callback del profiler possono essere generati in condizioni strettamente vincolate allo stack e un overflow dello stack nel callback di un profiler causerà l'uscita immediata dal processo. Come risposta ai callback, un profiler deve assicurarsi di usare uno stack di dimensioni ridotte. Se il profiler è destinato all'uso in processi affidabili in caso di overflow dello stack, dovrà evitare di causare un overflow dello stack.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Configurazione di un ambiente di profilatura](setting-up-a-profiling-environment.md)|Illustra come inizializzare un profiler, impostare le notifiche degli eventi e profilare un servizio di Windows.|
|[Interfacce di profilatura](profiling-interfaces.md)|Descrive le interfacce non gestite usate dall'API di profilatura.|
|[Funzioni statiche globali di profilatura](profiling-global-static-functions.md)|Descrive le funzioni statiche globali non gestite usate dall'API di profilatura.|
|[Enumerazioni di profilatura](profiling-enumerations.md)|Descrive le enumerazioni non gestite usate dall'API di profilatura.|
|[Strutture di profilatura](profiling-structures.md)|Descrive le strutture non gestite usate dall'API di profilatura.|
