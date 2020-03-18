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
# <a name="net-core-logging-and-tracing"></a><span data-ttu-id="32f83-103">Registrazione e traccia di .NET Core</span><span class="sxs-lookup"><span data-stu-id="32f83-103">.NET Core logging and tracing</span></span>

<span data-ttu-id="32f83-104">La registrazione e la traccia sono in realtà due nomi per la stessa tecnica.</span><span class="sxs-lookup"><span data-stu-id="32f83-104">Logging and tracing are really two names for the same technique.</span></span> <span data-ttu-id="32f83-105">La tecnica semplice è stata utilizzata fin dai primi giorni dei computer.</span><span class="sxs-lookup"><span data-stu-id="32f83-105">The simple technique has been used since the early days of computers.</span></span> <span data-ttu-id="32f83-106">Si tratta semplicemente di instrumentare un'applicazione per scrivere l'output da utilizzare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="32f83-106">It simply involves instrumenting an application to write output to be consumed later.</span></span>

## <a name="reasons-to-use-logging-and-tracing"></a><span data-ttu-id="32f83-107">Motivi per utilizzare la registrazione e la traccia</span><span class="sxs-lookup"><span data-stu-id="32f83-107">Reasons to use logging and tracing</span></span>

<span data-ttu-id="32f83-108">Questa semplice tecnica è sorprendentemente potente.</span><span class="sxs-lookup"><span data-stu-id="32f83-108">This simple technique is surprisingly powerful.</span></span> <span data-ttu-id="32f83-109">Può essere utilizzato in situazioni in cui un debugger non riesce:It can be used in situations where a debugger fails:</span><span class="sxs-lookup"><span data-stu-id="32f83-109">It can be used in situations where a debugger fails:</span></span>

- <span data-ttu-id="32f83-110">Problemi che si verificano per lunghi periodi di tempo, può essere difficile eseguire il debug con un debugger tradizionale.</span><span class="sxs-lookup"><span data-stu-id="32f83-110">Issues occurring over long periods of time, can be difficult to debug with a traditional debugger.</span></span> <span data-ttu-id="32f83-111">I registri consentono una revisione post-mortem dettagliata che si estende su lunghi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="32f83-111">Logs allow for detailed post-mortem review spanning long periods of time.</span></span> <span data-ttu-id="32f83-112">Al contrario, i debugger sono vincolati all'analisi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="32f83-112">In contrast, debuggers are constrained to real-time analysis.</span></span>
- <span data-ttu-id="32f83-113">Le applicazioni multithread e le applicazioni distribuite sono spesso difficili da eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="32f83-113">Multi-threaded applications and distributed applications are often difficult to debug.</span></span>  <span data-ttu-id="32f83-114">La connessione di un debugger tende a modificare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="32f83-114">Attaching a debugger tends to modify behaviors.</span></span> <span data-ttu-id="32f83-115">I log dettagliati possono essere analizzati in base alle esigenze per comprendere i sistemi complessi.</span><span class="sxs-lookup"><span data-stu-id="32f83-115">Detailed logs can be analyzed as needed to understand complex systems.</span></span>
- <span data-ttu-id="32f83-116">Possono derivare problemi nelle applicazioni distribuite da un'interazione complessa tra molti componenti e potrebbe non essere ragionevole connettere un debugger a ogni parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="32f83-116">Issues in distributed applications may arise from a complex interaction between many components and it may not be reasonable to connect a debugger to every part of the system.</span></span>
- <span data-ttu-id="32f83-117">Molti servizi non dovrebbero essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="32f83-117">Many services shouldn't be stalled.</span></span> <span data-ttu-id="32f83-118">La connessione di un debugger causa spesso errori di timeout.</span><span class="sxs-lookup"><span data-stu-id="32f83-118">Attaching a debugger often causes timeout failures.</span></span>
- <span data-ttu-id="32f83-119">I problemi non sono sempre previsti.</span><span class="sxs-lookup"><span data-stu-id="32f83-119">Issues aren't always foreseen.</span></span> <span data-ttu-id="32f83-120">La registrazione e la traccia sono progettate per un overhead ridotto in modo che i programmi possano sempre registrare nel caso in cui si verifichi un problema.</span><span class="sxs-lookup"><span data-stu-id="32f83-120">Logging and tracing are designed for low overhead so that programs can always be recording in case an issue occurs.</span></span>

## <a name="net-core-apis"></a><span data-ttu-id="32f83-121">API .NET Core</span><span class="sxs-lookup"><span data-stu-id="32f83-121">.NET Core APIs</span></span>

### <a name="print-style-apis"></a><span data-ttu-id="32f83-122">API in stile di stampa</span><span class="sxs-lookup"><span data-stu-id="32f83-122">Print style APIs</span></span>

<span data-ttu-id="32f83-123">Le <xref:System.Console?displayProperty=nameWithType> <xref:System.Diagnostics.Trace?displayProperty=nameWithType> <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classi , e forniscono ciascuna API di stile di stampa simili utili per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="32f83-123">The <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes each provide similar print style APIs convenient for logging.</span></span>

<span data-ttu-id="32f83-124">La scelta dell'API dello stile di stampa da utilizzare è a te.</span><span class="sxs-lookup"><span data-stu-id="32f83-124">The choice of which print style API to use is up to you.</span></span> <span data-ttu-id="32f83-125">Le differenze principali sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="32f83-125">The key differences are:</span></span>

- <xref:System.Console?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-126">Sempre abilitato e scrive sempre nella console.</span><span class="sxs-lookup"><span data-stu-id="32f83-126">Always enabled and always writes to the console.</span></span>
  - <span data-ttu-id="32f83-127">Utile per le informazioni che il cliente potrebbe aver bisogno di vedere nella versione.</span><span class="sxs-lookup"><span data-stu-id="32f83-127">Useful for information that your customer may need to see in the release.</span></span>
  - <span data-ttu-id="32f83-128">Poiché è l'approccio più semplice, viene spesso utilizzato per il debug temporaneo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="32f83-128">Because it's the simplest approach, it's often used for ad-hoc temporary debugging.</span></span> <span data-ttu-id="32f83-129">Questo codice di debug spesso non viene mai archiviato nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="32f83-129">This debug code is often never checked in to source control.</span></span>
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-130">Abilitato solo `TRACE` quando è definito.</span><span class="sxs-lookup"><span data-stu-id="32f83-130">Only enabled when `TRACE` is defined.</span></span>
  - <span data-ttu-id="32f83-131">Scrive su <xref:System.Diagnostics.Trace.Listeners>attached , <xref:System.Diagnostics.DefaultTraceListener>per impostazione predefinita il file .</span><span class="sxs-lookup"><span data-stu-id="32f83-131">Writes to attached <xref:System.Diagnostics.Trace.Listeners>, by default the <xref:System.Diagnostics.DefaultTraceListener>.</span></span>
  - <span data-ttu-id="32f83-132">Usare questa API quando si creano log che verranno abilitati nella maggior parte delle compilazioni.</span><span class="sxs-lookup"><span data-stu-id="32f83-132">Use this API when creating logs that will be enabled in most builds.</span></span>
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-133">Abilitato solo `DEBUG` quando è definito.</span><span class="sxs-lookup"><span data-stu-id="32f83-133">Only enabled when `DEBUG` is defined.</span></span>
  - <span data-ttu-id="32f83-134">Scrive in un debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="32f83-134">Writes to an attached debugger.</span></span>
  - <span data-ttu-id="32f83-135">Su `*nix` scrive in stderr se `COMPlus_DebugWriteToStdErr` è impostato.</span><span class="sxs-lookup"><span data-stu-id="32f83-135">On `*nix` writes to stderr if `COMPlus_DebugWriteToStdErr` is set.</span></span>
  - <span data-ttu-id="32f83-136">Utilizzare questa API quando si creano log che verranno abilitati solo nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="32f83-136">Use this API when creating logs that will be enabled only in debug builds.</span></span>

### <a name="logging-events"></a><span data-ttu-id="32f83-137">Registrazione degli eventiLogging events</span><span class="sxs-lookup"><span data-stu-id="32f83-137">Logging events</span></span>

<span data-ttu-id="32f83-138">Le API seguenti sono più orientate agli eventi.</span><span class="sxs-lookup"><span data-stu-id="32f83-138">The following APIs are more event oriented.</span></span> <span data-ttu-id="32f83-139">Anziché registrare stringhe semplici registrano gli oggetti evento.</span><span class="sxs-lookup"><span data-stu-id="32f83-139">Rather than logging simple strings they log event objects.</span></span>

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-140">EventSource è l'API di traccia di .NET Core radice principale.</span><span class="sxs-lookup"><span data-stu-id="32f83-140">EventSource is the primary root .NET Core tracing API.</span></span>
  - <span data-ttu-id="32f83-141">Disponibile in tutte le versioni di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="32f83-141">Available in all .NET Standard versions.</span></span>
  - <span data-ttu-id="32f83-142">Consente solo il tracciamento di oggetti serializzabili.</span><span class="sxs-lookup"><span data-stu-id="32f83-142">Only allows tracing serializable objects.</span></span>
  - <span data-ttu-id="32f83-143">Scrive nei [listener di eventi](xref:System.Diagnostics.Tracing.EventListener)associati.</span><span class="sxs-lookup"><span data-stu-id="32f83-143">Writes to the attached [event listeners](xref:System.Diagnostics.Tracing.EventListener).</span></span>
  - <span data-ttu-id="32f83-144">.NET Core fornisce listener per:</span><span class="sxs-lookup"><span data-stu-id="32f83-144">.NET Core provides listeners for:</span></span>
    - <span data-ttu-id="32f83-145">EventPipe di .NET Core su tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="32f83-145">.NET Core's EventPipe on all platforms</span></span>
    - [<span data-ttu-id="32f83-146">Analisi eventi per Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="32f83-146">Event Tracing for Windows (ETW)</span></span>](/windows/win32/etw/event-tracing-portal)
    - [<span data-ttu-id="32f83-147">LTTng tracing framework for Linux</span><span class="sxs-lookup"><span data-stu-id="32f83-147">LTTng tracing framework for Linux</span></span>](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-148">Incluso in .NET Core e come [pacchetto NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="32f83-148">Included in .NET Core and as a [NuGet package](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) for .NET Framework.</span></span>
  - <span data-ttu-id="32f83-149">Consente la traccia in-process di oggetti non serializzabili.</span><span class="sxs-lookup"><span data-stu-id="32f83-149">Allows in-process tracing of non-serializable objects.</span></span>
  - <span data-ttu-id="32f83-150">Include un bridge per consentire la scrittura in <xref:System.Diagnostics.Tracing.EventSource>un file .</span><span class="sxs-lookup"><span data-stu-id="32f83-150">Includes a bridge to allow selected fields of logged objects to be written to an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-151">Fornisce un modo definitivo per identificare i messaggi di log risultanti da un'attività o una transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="32f83-151">Provides a definitive way to identify log messages resulting from a specific activity or transaction.</span></span> <span data-ttu-id="32f83-152">Questo oggetto può essere utilizzato per correlare i log tra servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="32f83-152">This object can be used to correlate logs across different services.</span></span>

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - <span data-ttu-id="32f83-153">Solo Windows.</span><span class="sxs-lookup"><span data-stu-id="32f83-153">Windows only.</span></span>
  - <span data-ttu-id="32f83-154">Scrive i messaggi nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="32f83-154">Writes messages to the Windows Event Log.</span></span>
  - <span data-ttu-id="32f83-155">Gli amministratori di sistema si aspettano che nel registro eventi di Windows vengano visualizzati messaggi di errore irreversibili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32f83-155">System administrators expect fatal application error messages to appear in the Windows Event Log.</span></span>

## <a name="ilogger-and-logging-frameworks"></a><span data-ttu-id="32f83-156">ILogger e framework di registrazione</span><span class="sxs-lookup"><span data-stu-id="32f83-156">ILogger and logging frameworks</span></span>

<span data-ttu-id="32f83-157">Le API di basso livello potrebbero non essere la scelta giusta per le esigenze di registrazione.</span><span class="sxs-lookup"><span data-stu-id="32f83-157">The low-level APIs may not be the right choice for your logging needs.</span></span> <span data-ttu-id="32f83-158">È possibile prendere in considerazione un framework di registrazione.</span><span class="sxs-lookup"><span data-stu-id="32f83-158">You may want to consider a logging framework.</span></span>

<span data-ttu-id="32f83-159">L'interfaccia <xref:Microsoft.Extensions.Logging.ILogger> è stata utilizzata per creare un'interfaccia di registrazione comune in cui i logger possono essere inseriti tramite inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="32f83-159">The <xref:Microsoft.Extensions.Logging.ILogger> interface has been used to create a common logging interface where the loggers can be inserted through dependency injection.</span></span>

<span data-ttu-id="32f83-160">Ad esempio, per consentire di effettuare `ASP.NET` la scelta migliore per l'applicazione offre il supporto per una selezione di framework incorporati e di terze parti:</span><span class="sxs-lookup"><span data-stu-id="32f83-160">For instance, to allow you to make the best choice for your application `ASP.NET` offers support for a selection of built-in and third-party frameworks:</span></span>

- [<span data-ttu-id="32f83-161">ASP.NET provider di registrazione incorporati</span><span class="sxs-lookup"><span data-stu-id="32f83-161">ASP.NET built in logging providers</span></span>](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [<span data-ttu-id="32f83-162">ASP.NET provider di registrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="32f83-162">ASP.NET Third-party logging providers</span></span>](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a><span data-ttu-id="32f83-163">Registrazione dei riferimenti correlatiLogging related references</span><span class="sxs-lookup"><span data-stu-id="32f83-163">Logging related references</span></span>

- [<span data-ttu-id="32f83-164">Procedura: compilare in modo condizionale con traccia e debug</span><span class="sxs-lookup"><span data-stu-id="32f83-164">How to: Compile Conditionally with Trace and Debug</span></span>](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [<span data-ttu-id="32f83-165">Procedura: aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="32f83-165">How to: Add Trace Statements to Application Code</span></span>](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- <span data-ttu-id="32f83-166">[ASP.NET la](/aspnet/core/fundamentals/logging) registrazione fornisce una panoramica delle tecniche di registrazione supportate.</span><span class="sxs-lookup"><span data-stu-id="32f83-166">[ASP.NET Logging](/aspnet/core/fundamentals/logging) provides an overview of the logging techniques it supports.</span></span>

- <span data-ttu-id="32f83-167">[L'interpolazione di](../../csharp/language-reference/tokens/interpolated.md) stringhe in Cè può semplificare la scrittura del codice di registrazione.</span><span class="sxs-lookup"><span data-stu-id="32f83-167">[C# String Interpolation](../../csharp/language-reference/tokens/interpolated.md) can simplify writing logging code.</span></span>

- <span data-ttu-id="32f83-168">La <xref:System.Exception.Message?displayProperty=nameWithType> proprietà è utile per registrare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="32f83-168">The <xref:System.Exception.Message?displayProperty=nameWithType> property is useful for logging exceptions.</span></span>

- <span data-ttu-id="32f83-169">La <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> classe può essere utile per fornire informazioni sullo stack nei log.</span><span class="sxs-lookup"><span data-stu-id="32f83-169">The <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> class can be useful to provide stack info in your logs.</span></span>

## <a name="performance-considerations"></a><span data-ttu-id="32f83-170">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="32f83-170">Performance considerations</span></span>

<span data-ttu-id="32f83-171">La formattazione delle stringhe può richiedere un notevole tempo di elaborazione della CPU.</span><span class="sxs-lookup"><span data-stu-id="32f83-171">String formatting can take noticeable CPU processing time.</span></span>

<span data-ttu-id="32f83-172">Nelle applicazioni critiche per le prestazioni, è consigliabile:In performance critical applications, it's recommended that you:</span><span class="sxs-lookup"><span data-stu-id="32f83-172">In performance critical applications, it's recommended that you:</span></span>

- <span data-ttu-id="32f83-173">Evitare un sacco di registrazione quando nessuno è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="32f83-173">Avoid lots of logging when no one is listening.</span></span> <span data-ttu-id="32f83-174">Evitare di creare costosi messaggi di registrazione controllando se la registrazione è abilitata per prima.</span><span class="sxs-lookup"><span data-stu-id="32f83-174">Avoid constructing costly logging messages by checking if logging is enabled first.</span></span>
- <span data-ttu-id="32f83-175">Registra solo ciò che è utile.</span><span class="sxs-lookup"><span data-stu-id="32f83-175">Only log what's useful.</span></span>
- <span data-ttu-id="32f83-176">Posticipare la formattazione di fantasia alla fase di analisi.</span><span class="sxs-lookup"><span data-stu-id="32f83-176">Defer fancy formatting to the analysis stage.</span></span>
