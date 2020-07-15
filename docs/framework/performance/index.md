---
title: Prestazioni di .NET Framework
description: Progettare e pianificare le prestazioni delle applicazioni .NET. Usare gli strumenti forniti da Microsoft per misurare le prestazioni dell'app e apportare miglioramenti.
ms.date: 03/30/2017
helpviewer_keywords:
- performance [.NET Framework]
- reliability [.NET Framework]
ms.assetid: c1676cca-3f1a-41ec-b469-9029566074fc
ms.openlocfilehash: ee8260056bd87dfc66d96e394f9b93bb9427afd8
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309755"
---
# <a name="net-framework-performance"></a>Prestazioni di .NET Framework
Per garantire prestazioni ottimali, le prestazioni devono essere progettate e pianificate come qualsiasi altra funzionalità delle app. Gli strumenti messi a disposizione da Microsoft consentono di misurare le prestazioni delle app e, se necessario, migliorare l'uso della memoria, la velocità effettiva del codice e la velocità di risposta. Questo argomento contiene un elenco degli strumenti per l'analisi delle prestazioni forniti da Microsoft e collegamenti ad altri argomenti relativi alle prestazioni per aree specifiche dello sviluppo di applicazioni.  
  
## <a name="designing-and-planning-for-performance"></a>Progettazione e pianificazione per le prestazioni  
 Per creare un'app con prestazioni ottimali, è necessario progettare le prestazioni procedendo come per qualsiasi altra funzionalità. È opportuno identificare gli scenari che prevedono prestazioni elevate, definire gli obiettivi in termini di prestazioni e misurare le prestazioni dell'app negli scenari identificati in modo tempestivo e frequente. Poiché ogni app è diversa dalle altre ed è caratterizzata da uno specifico percorso di esecuzione cruciale, identificare tempestivamente questi percorsi e concentrare gli sforzi su di essi permette di massimizzare la produttività.  
  
 Non è necessario conoscere a fondo la piattaforma di destinazione per creare un'app con prestazioni elevate. È però necessario capire quali parti delle parti della piattaforma di destinazione abbiano requisiti elevati in termini di prestazioni. Per fare questo, occorre misurare le prestazioni nelle prime fasi del processo di sviluppo.  
  
 Per individuare le aree cruciali per le prestazioni e definire gli obiettivi di prestazioni, tenere sempre presente l'esperienza utente. Tempi di avvio e velocità di risposta sono due aree chiave che incideranno sulla percezione dell'app da parte degli utenti. Se l'app usa molta memoria può sembrare lenta, incidere negativamente su altre app in esecuzione nel sistema o, in alcuni casi, provocare errori nel processo di invio di Windows Store o Windows Phone Store. Inoltre, individuando le parti del codice eseguite più spesso, ci si può assicurare che siano ottimizzate.  
  
## <a name="analyzing-performance"></a>Analisi delle prestazioni  
 Come parte del piano di sviluppo complessivo, stabilire dei punti in cui si misureranno le prestazioni dell'app e si confronteranno i risultati con gli obiettivi stabiliti in precedenza. Misurare l'app nell'ambiente e con l'hardware presumibilmente usato dagli utenti. Analizzando le prestazioni dell'app in modo tempestivo e frequente, è possibile modificare alcune decisioni architetturali che sarebbe costoso e dispendioso correggere più avanti nel ciclo di sviluppo. Le sezioni seguenti descrivono gli strumenti per le prestazioni che è possibile usare per analizzare le app e illustrano la funzionalità di traccia degli eventi usata da questi strumenti.  
  
### <a name="performance-tools"></a>Strumenti per le prestazioni  
 Di seguito sono elencati alcuni strumenti per le prestazioni che è possibile usare con le app .NET Framework.  
  
|Strumento|Descrizione|  
|----------|-----------------|  
|Analisi prestazioni di Visual Studio|Consente di analizzare l'uso di CPU delle app .NET Framework che verranno distribuite in computer che eseguono il sistema operativo Windows.<br /><br /> Questo strumento è disponibile nel menu **Debug** di Visual Studio dopo l'apertura di un progetto. Per altre informazioni, vedere [Esplora prestazioni](/visualstudio/profiling/performance-explorer). **Nota:** usare l'analisi applicazione di Windows Phone (vedere la riga seguente) per dispositivi Windows Phone.|  
|Analisi applicazione di Windows Phone|Consente di analizzare l'uso di CPU e memoria, la velocità di trasferimento dati della rete, la velocità di risposta dell'app e il consumo di batteria delle app Windows Phone.<br /><br /> Questo strumento è disponibile nel menu **Debug** per un progetto Windows Phone in Visual Studio dopo l'installazione di [Windows Phone SDK](https://go.microsoft.com/fwlink/?LinkId=265773). Per altre informazioni, vedere [profilatura delle app per Windows Phone 8](https://docs.microsoft.com/previous-versions/windows/apps/jj215908(v=vs.105)).|  
|[PerfView](https://www.microsoft.com/download/details.aspx?id=28567)|Consente di identificare i problemi prestazionali correlati alla CPU e alla memoria. Questo strumento usa le API di profilatura di Event Tracing for Windows (ETW) e CLR per offrire analisi avanzate sulla CPU e la memoria, oltre a informazioni su Garbage Collection e compilazione del codice JIT. Per altre informazioni su come usare PerfView, vedere l'esercitazione e i file della Guida inclusi con l'app, le [esercitazioni video di Channel 9](https://channel9.msdn.com/Series/PerfView-Tutorial) e i [post di blog](https://docs.microsoft.com/archive/blogs/vancem/).<br /><br /> Per problemi specifici della memoria, vedere [Using PerfView for Memory Investigations](https://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-9-NET-Memory-Investigation-Basics-of-GC-Heap-Snapshots) (Uso di PerfView per le analisi della memoria).|  
|[Windows Performance Analyzer](https://www.microsoft.com/download/details.aspx?id=30652)|Consente di determinare le prestazioni complessive del sistema, ad esempio l'uso di memoria e risorse di archiviazione da parte dell'app quando più applicazioni sono in esecuzione nello stesso computer. Questo strumento è disponibile nell'area download come parte di Windows Assessment and Deployment Kit (ADK) per Windows 8. Per altre informazioni, vedere [Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer).|
  
### <a name="event-tracing-for-windows-etw"></a>Event Tracing for Windows (ETW)  
 ETW è una tecnica che consente di ottenere informazioni diagnostiche sul codice in esecuzione ed è essenziale per molti degli strumenti per le prestazioni indicati in precedenza. ETW crea log per particolari eventi generati dalle app .NET Framework e da Windows. Con ETW è possibile abilitare e disabilitare la registrazione in modo dinamico e dunque eseguire analisi dettagliate negli ambienti di produzione senza riavviare l'app. .NET Framework offre supporto per gli eventi ETW ed ETW è usato da numerosi strumenti per la profilatura e le prestazioni per generare dati sulle prestazioni. Spesso questi strumenti abilitano e disabilitano gli eventi ETW, quindi è utile conoscerli. È possibile usare specifici eventi ETW per raccogliere informazioni sulle prestazioni relative a particolari componenti dell'app. Per altre informazioni sul supporto ETW in .NET Framework, vedere [ETW Events in the Common Language Runtime](etw-events-in-the-common-language-runtime.md) (Eventi ETW in Common Language Runtime) e [Eventi ETW nella libreria TPL (Task Parallel Library) e PLINQ](etw-events-in-task-parallel-library-and-plinq.md).  
  
## <a name="performance-by-app-type"></a>Prestazioni per tipo di applicazione  
 Per ogni tipo di app .NET Framework esistono procedure consigliate, considerazioni e strumenti per la valutazione delle prestazioni diversi. La tabella seguente contiene collegamenti ad argomenti relativi alle prestazioni per specifici tipi di app .NET Framework.  
  
|Tipo di app|Vedere|  
|--------------|---------|  
|App .NET Framework per tutte le piattaforme|[Garbage Collection e prestazioni](../../standard/garbage-collection/performance.md)<br /><br /> [Suggerimenti sulle prestazioni](performance-tips.md)|  
|App di Windows 8. x Store scritte in C++, C# e Visual Basic|[Procedure consigliate per app di Windows Store scritte in C++, C# e Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/hh750313%28v=win.10%29)|  
|Windows Presentation Foundation (WPF)|[Famiglia di prodotti per l'analisi delle prestazioni WPF](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100))|  
|ASP.NET|[Cenni preliminari sulle prestazioni di ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668225(v=vs.100))|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Memorizzazione nella cache in applicazioni .NET Framework](caching-in-net-framework-applications.md)|Descrive tecniche per la memorizzazione nella cache dei dati per migliorare le prestazioni dell'app.|  
|[Inizializzazione differita](lazy-initialization.md)|Descrive come inizializzare gli oggetti quando necessario per migliorare le prestazioni, in particolare all'avvio dell'app.|  
|[Affidabilità](reliability.md)|Contiene informazioni su come evitare eccezioni asincrone in un ambiente server.|  
|[Scrittura di app grandi e reattive in .NET Framework](writing-large-responsive-apps.md)|Offre suggerimenti sulle prestazioni che derivano dalla riscrittura di compilatori C# e Visual Basic nel codice gestito e include diversi esempi concreti tratti dal compilatore C#.|
