---
title: Registrazione e traccia - .NET CoreLogging and tracing - .NET Core
description: Introduzione alla registrazione e alla traccia di .NET Core.An introduction to .NET Core logging and tracing.
ms.date: 08/05/2019
ms.openlocfilehash: 392b88c9ea3c31c919a605ac0a5c886f7d63f79a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714416"
---
# <a name="net-core-logging-and-tracing"></a>Registrazione e traccia di .NET Core

La registrazione e la traccia sono in realtà due nomi per la stessa tecnica. La tecnica semplice è stata utilizzata fin dai primi giorni dei computer. Si tratta semplicemente di instrumentare un'applicazione per scrivere l'output da utilizzare in un secondo momento.

## <a name="reasons-to-use-logging-and-tracing"></a>Motivi per utilizzare la registrazione e la traccia

Questa semplice tecnica è sorprendentemente potente. Può essere utilizzato in situazioni in cui un debugger non riesce:It can be used in situations where a debugger fails:

- Problemi che si verificano per lunghi periodi di tempo, può essere difficile eseguire il debug con un debugger tradizionale. I registri consentono una revisione post-mortem dettagliata che si estende su lunghi periodi di tempo. Al contrario, i debugger sono vincolati all'analisi in tempo reale.
- Le applicazioni multithread e le applicazioni distribuite sono spesso difficili da eseguire il debug.  La connessione di un debugger tende a modificare i comportamenti. I log dettagliati possono essere analizzati in base alle esigenze per comprendere i sistemi complessi.
- Possono derivare problemi nelle applicazioni distribuite da un'interazione complessa tra molti componenti e potrebbe non essere ragionevole connettere un debugger a ogni parte del sistema.
- Molti servizi non dovrebbero essere bloccati. La connessione di un debugger causa spesso errori di timeout.
- I problemi non sono sempre previsti. La registrazione e la traccia sono progettate per un overhead ridotto in modo che i programmi possano sempre registrare nel caso in cui si verifichi un problema.

## <a name="net-core-apis"></a>API .NET Core

### <a name="print-style-apis"></a>API in stile di stampa

Le <xref:System.Console?displayProperty=nameWithType> <xref:System.Diagnostics.Trace?displayProperty=nameWithType> <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classi , e forniscono ciascuna API di stile di stampa simili utili per la registrazione.

La scelta dell'API dello stile di stampa da utilizzare è a te. Le differenze principali sono le seguenti:

- <xref:System.Console?displayProperty=nameWithType>
  - Sempre abilitato e scrive sempre nella console.
  - Utile per le informazioni che il cliente potrebbe aver bisogno di vedere nella versione.
  - Poiché è l'approccio più semplice, viene spesso utilizzato per il debug temporaneo ad hoc. Questo codice di debug spesso non viene mai archiviato nel controllo del codice sorgente.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - Abilitato solo `TRACE` quando è definito.
  - Scrive su <xref:System.Diagnostics.Trace.Listeners>attached , <xref:System.Diagnostics.DefaultTraceListener>per impostazione predefinita il file .
  - Usare questa API quando si creano log che verranno abilitati nella maggior parte delle compilazioni.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - Abilitato solo `DEBUG` quando è definito.
  - Scrive in un debugger collegato.
  - Su `*nix` scrive in stderr se `COMPlus_DebugWriteToStdErr` è impostato.
  - Utilizzare questa API quando si creano log che verranno abilitati solo nelle build di debug.

### <a name="logging-events"></a>Registrazione degli eventiLogging events

Le API seguenti sono più orientate agli eventi. Anziché registrare stringhe semplici registrano gli oggetti evento.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource è l'API di traccia di .NET Core radice principale.
  - Disponibile in tutte le versioni di .NET Standard.
  - Consente solo il tracciamento di oggetti serializzabili.
  - Scrive nei [listener di eventi](xref:System.Diagnostics.Tracing.EventListener)associati.
  - .NET Core fornisce listener per:
    - EventPipe di .NET Core su tutte le piattaforme
    - [Analisi eventi per Windows (ETW)](/windows/win32/etw/event-tracing-portal)
    - [LTTng tracing framework for Linux](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - Incluso in .NET Core e come [pacchetto NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) per .NET Framework.
  - Consente la traccia in-process di oggetti non serializzabili.
  - Include un bridge per consentire la scrittura in <xref:System.Diagnostics.Tracing.EventSource>un file .

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - Fornisce un modo definitivo per identificare i messaggi di log risultanti da un'attività o una transazione specifica. Questo oggetto può essere utilizzato per correlare i log tra servizi diversi.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Solo Windows.
  - Scrive i messaggi nel registro eventi di Windows.
  - Gli amministratori di sistema si aspettano che nel registro eventi di Windows vengano visualizzati messaggi di errore irreversibili dell'applicazione.

## <a name="ilogger-and-logging-frameworks"></a>ILogger e framework di registrazione

Le API di basso livello potrebbero non essere la scelta giusta per le esigenze di registrazione. È possibile prendere in considerazione un framework di registrazione.

L'interfaccia <xref:Microsoft.Extensions.Logging.ILogger> è stata utilizzata per creare un'interfaccia di registrazione comune in cui i logger possono essere inseriti tramite inserimento delle dipendenze.

Ad esempio, per consentire di effettuare `ASP.NET` la scelta migliore per l'applicazione offre il supporto per una selezione di framework incorporati e di terze parti:

- [ASP.NET provider di registrazione incorporati](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [ASP.NET provider di registrazione di terze parti](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a>Registrazione dei riferimenti correlatiLogging related references

- [Procedura: compilare in modo condizionale con traccia e debug](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [Procedura: aggiungere istruzioni di traccia al codice dell'applicazione](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- [ASP.NET la](/aspnet/core/fundamentals/logging) registrazione fornisce una panoramica delle tecniche di registrazione supportate.

- [L'interpolazione di](../../csharp/language-reference/tokens/interpolated.md) stringhe in Cè può semplificare la scrittura del codice di registrazione.

- La <xref:System.Exception.Message?displayProperty=nameWithType> proprietà è utile per registrare le eccezioni.

- La <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> classe può essere utile per fornire informazioni sullo stack nei log.

## <a name="performance-considerations"></a>Considerazioni sulle prestazioni

La formattazione delle stringhe può richiedere un notevole tempo di elaborazione della CPU.

Nelle applicazioni critiche per le prestazioni, è consigliabile:In performance critical applications, it's recommended that you:

- Evitare un sacco di registrazione quando nessuno è in ascolto. Evitare di creare costosi messaggi di registrazione controllando se la registrazione è abilitata per prima.
- Registra solo ciò che è utile.
- Posticipare la formattazione di fantasia alla fase di analisi.
