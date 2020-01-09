---
title: Registrazione e traccia-.NET Core
description: Introduzione alla registrazione e alla traccia di .NET Core.
ms.date: 08/05/2019
ms.openlocfilehash: 392b88c9ea3c31c919a605ac0a5c886f7d63f79a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714416"
---
# <a name="net-core-logging-and-tracing"></a>Registrazione e traccia di .NET Core

La registrazione e la traccia sono in realtà due nomi per la stessa tecnica. La tecnica semplice è stata usata sin dai primi giorni dei computer. Implica semplicemente la strumentazione di un'applicazione per la scrittura dell'output da utilizzare in un secondo momento.

## <a name="reasons-to-use-logging-and-tracing"></a>Motivi per usare la registrazione e la traccia

Questa semplice tecnica è sorprendentemente potente. Può essere usato in situazioni in cui un debugger ha esito negativo:

- Per i problemi che si verificano in lunghi periodi di tempo, può essere difficile eseguire il debug con un debugger tradizionale. I log consentono di esaminare in modo dettagliato i lunghi periodi di tempo. Al contrario, i debugger sono limitati all'analisi in tempo reale.
- Le applicazioni multithreading e le applicazioni distribuite sono spesso difficili da eseguire il debug.  Il montaggio di un debugger tende a modificare i comportamenti. I log dettagliati possono essere analizzati in base alle esigenze per comprendere sistemi complessi.
- I problemi nelle applicazioni distribuite possono derivare da un'interazione complessa tra molti componenti e potrebbe non essere ragionevole connettere un debugger a ogni parte del sistema.
- Molti servizi non devono essere bloccati. Il fissaggio di un debugger causa spesso errori di timeout.
- I problemi non sono sempre previsti. La registrazione e la traccia sono progettate per un sovraccarico ridotto, in modo che i programmi possano sempre essere registrati in caso di problemi.

## <a name="net-core-apis"></a>API .NET Core

### <a name="print-style-apis"></a>API stile di stampa

Le classi <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>e <xref:System.Diagnostics.Debug?displayProperty=nameWithType> offrono API simili per lo stile di stampa utili per la registrazione.

La scelta dell'API dello stile di stampa da usare dipende dall'utente. Le differenze principali sono le seguenti:

- <xref:System.Console?displayProperty=nameWithType>
  - Sempre abilitato e scrive sempre nella console.
  - Utile per le informazioni che il cliente potrebbe dover visualizzare nella versione.
  - Poiché è l'approccio più semplice, viene spesso usato per il debug temporaneo ad hoc. Questo codice di debug spesso non viene mai archiviato nel controllo del codice sorgente.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - Abilitato solo quando viene definito `TRACE`.
  - Scrive nel <xref:System.Diagnostics.Trace.Listeners>allegato, per impostazione predefinita il <xref:System.Diagnostics.DefaultTraceListener>.
  - Usare questa API durante la creazione di log che verranno abilitati nella maggior parte delle compilazioni.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - Abilitato solo quando viene definito `DEBUG`.
  - Scrive in un debugger collegato.
  - In `*nix` scrive in stderr se è impostato `COMPlus_DebugWriteToStdErr`.
  - Usare questa API durante la creazione di log che saranno abilitati solo nelle build di debug.

### <a name="logging-events"></a>Registrazione di eventi

Le API seguenti sono più orientate agli eventi. Anziché registrare semplici stringhe, registrano gli oggetti evento.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource è l'API di traccia principale principale di .NET Core.
  - Disponibile in tutte le versioni .NET Standard.
  - Consente solo la traccia degli oggetti serializzabili.
  - Scrive nei listener di [eventi](xref:System.Diagnostics.Tracing.EventListener)collegati.
  - .NET Core fornisce i listener per:
    - EventPipe di .NET Core su tutte le piattaforme
    - [Event Tracing for Windows (ETW)](/windows/win32/etw/event-tracing-portal)
    - [Framework di traccia LTTng per Linux](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - Incluso in .NET Core e come [pacchetto NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) per .NET Framework.
  - Consente la traccia in-process di oggetti non serializzabili.
  - Include un Bridge per consentire la scrittura dei campi selezionati degli oggetti registrati in un <xref:System.Diagnostics.Tracing.EventSource>.

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - Consente di identificare in modo definitivo i messaggi di log derivanti da un'attività o una transazione specifica. Questo oggetto può essere utilizzato per correlare i log tra servizi diversi.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Solo Windows.
  - Scrive messaggi nel registro eventi di Windows.
  - Gli amministratori di sistema si aspettano che vengano visualizzati messaggi di errore irreversibili nell'applicazione nel registro eventi di Windows.

## <a name="ilogger-and-logging-frameworks"></a>ILogger e Framework di registrazione

Le API di basso livello potrebbero non essere la scelta migliore per le esigenze di registrazione. Si consiglia di prendere in considerazione un Framework di registrazione.

L'interfaccia <xref:Microsoft.Extensions.Logging.ILogger> è stata usata per creare un'interfaccia di registrazione comune in cui i logger possono essere inseriti tramite l'inserimento di dipendenze.

Ad esempio, per consentire all'utente di scegliere la scelta migliore per l'applicazione `ASP.NET` offre supporto per la selezione di Framework predefiniti e di terze parti:

- [ASP.NET incorporati nei provider di registrazione](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [ASP.NET provider di registrazione di terze parti](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a>Riferimenti relativi alla registrazione

- [Procedura: Compilare in modo condizionale con traccia e debug](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [Procedura: aggiungere istruzioni di traccia al codice dell'applicazione](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- La [registrazione ASP.NET](/aspnet/core/fundamentals/logging) offre una panoramica delle tecniche di registrazione supportate.

- L'interpolazione di stringhe può semplificare la scrittura del codice di registrazione. [ C# ](../../csharp/language-reference/tokens/interpolated.md)

- La proprietà <xref:System.Exception.Message?displayProperty=nameWithType> è utile per la registrazione delle eccezioni.

- La classe <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> può essere utile per fornire informazioni sullo stack nei log.

## <a name="performance-considerations"></a>Considerazioni sulle prestazioni

La formattazione della stringa può richiedere tempi di elaborazione della CPU evidenti.

Nelle applicazioni critiche per le prestazioni, è consigliabile:

- Evitare una grande quantità di registrazione quando nessuno è in ascolto. Evitare di creare costosi messaggi di registrazione controllando che la registrazione sia abilitata per prima.
- Registra solo le informazioni utili.
- Rinvia la formattazione in modo sofisticato alla fase di analisi.
