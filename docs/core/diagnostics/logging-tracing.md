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
# <a name="net-core-logging-and-tracing"></a><span data-ttu-id="ed5e4-103">Registrazione e traccia di .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed5e4-103">.NET Core logging and tracing</span></span>

<span data-ttu-id="ed5e4-104">La registrazione e la traccia sono in realtà due nomi per la stessa tecnica.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-104">Logging and tracing are really two names for the same technique.</span></span> <span data-ttu-id="ed5e4-105">La tecnica semplice è stata usata sin dai primi giorni dei computer.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-105">The simple technique has been used since the early days of computers.</span></span> <span data-ttu-id="ed5e4-106">Implica semplicemente la strumentazione di un'applicazione per la scrittura dell'output da utilizzare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-106">It simply involves instrumenting an application to write output to be consumed later.</span></span>

## <a name="reasons-to-use-logging-and-tracing"></a><span data-ttu-id="ed5e4-107">Motivi per usare la registrazione e la traccia</span><span class="sxs-lookup"><span data-stu-id="ed5e4-107">Reasons to use logging and tracing</span></span>

<span data-ttu-id="ed5e4-108">Questa semplice tecnica è sorprendentemente potente.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-108">This simple technique is surprisingly powerful.</span></span> <span data-ttu-id="ed5e4-109">Può essere usato in situazioni in cui un debugger ha esito negativo:</span><span class="sxs-lookup"><span data-stu-id="ed5e4-109">It can be used in situations where a debugger fails:</span></span>

- <span data-ttu-id="ed5e4-110">Per i problemi che si verificano in lunghi periodi di tempo, può essere difficile eseguire il debug con un debugger tradizionale.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-110">Issues occurring over long periods of time, can be difficult to debug with a traditional debugger.</span></span> <span data-ttu-id="ed5e4-111">I log consentono di esaminare in modo dettagliato i lunghi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-111">Logs allow for detailed post-mortem review spanning long periods of time.</span></span> <span data-ttu-id="ed5e4-112">Al contrario, i debugger sono limitati all'analisi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-112">In contrast, debuggers are constrained to real-time analysis.</span></span>
- <span data-ttu-id="ed5e4-113">Le applicazioni multithreading e le applicazioni distribuite sono spesso difficili da eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-113">Multi-threaded applications and distributed applications are often difficult to debug.</span></span>  <span data-ttu-id="ed5e4-114">Il montaggio di un debugger tende a modificare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-114">Attaching a debugger tends to modify behaviors.</span></span> <span data-ttu-id="ed5e4-115">I log dettagliati possono essere analizzati in base alle esigenze per comprendere sistemi complessi.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-115">Detailed logs can be analyzed as needed to understand complex systems.</span></span>
- <span data-ttu-id="ed5e4-116">I problemi nelle applicazioni distribuite possono derivare da un'interazione complessa tra molti componenti e potrebbe non essere ragionevole connettere un debugger a ogni parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-116">Issues in distributed applications may arise from a complex interaction between many components and it may not be reasonable to connect a debugger to every part of the system.</span></span>
- <span data-ttu-id="ed5e4-117">Molti servizi non devono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-117">Many services shouldn't be stalled.</span></span> <span data-ttu-id="ed5e4-118">Il fissaggio di un debugger causa spesso errori di timeout.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-118">Attaching a debugger often causes timeout failures.</span></span>
- <span data-ttu-id="ed5e4-119">I problemi non sono sempre previsti.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-119">Issues aren't always foreseen.</span></span> <span data-ttu-id="ed5e4-120">La registrazione e la traccia sono progettate per un sovraccarico ridotto, in modo che i programmi possano sempre essere registrati in caso di problemi.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-120">Logging and tracing are designed for low overhead so that programs can always be recording in case an issue occurs.</span></span>

## <a name="net-core-apis"></a><span data-ttu-id="ed5e4-121">API .NET Core</span><span class="sxs-lookup"><span data-stu-id="ed5e4-121">.NET Core APIs</span></span>

### <a name="print-style-apis"></a><span data-ttu-id="ed5e4-122">API stile di stampa</span><span class="sxs-lookup"><span data-stu-id="ed5e4-122">Print style APIs</span></span>

<span data-ttu-id="ed5e4-123">Le classi <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>e <xref:System.Diagnostics.Debug?displayProperty=nameWithType> offrono API simili per lo stile di stampa utili per la registrazione.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-123">The <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes each provide similar print style APIs convenient for logging.</span></span>

<span data-ttu-id="ed5e4-124">La scelta dell'API dello stile di stampa da usare dipende dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-124">The choice of which print style API to use is up to you.</span></span> <span data-ttu-id="ed5e4-125">Le differenze principali sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed5e4-125">The key differences are:</span></span>

- <xref:System.Console?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-126">Sempre abilitato e scrive sempre nella console.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-126">Always enabled and always writes to the console.</span></span>
  - <span data-ttu-id="ed5e4-127">Utile per le informazioni che il cliente potrebbe dover visualizzare nella versione.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-127">Useful for information that your customer may need to see in the release.</span></span>
  - <span data-ttu-id="ed5e4-128">Poiché è l'approccio più semplice, viene spesso usato per il debug temporaneo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-128">Because it's the simplest approach, it's often used for ad-hoc temporary debugging.</span></span> <span data-ttu-id="ed5e4-129">Questo codice di debug spesso non viene mai archiviato nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-129">This debug code is often never checked in to source control.</span></span>
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-130">Abilitato solo quando viene definito `TRACE`.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-130">Only enabled when `TRACE` is defined.</span></span>
  - <span data-ttu-id="ed5e4-131">Scrive nel <xref:System.Diagnostics.Trace.Listeners>allegato, per impostazione predefinita il <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-131">Writes to attached <xref:System.Diagnostics.Trace.Listeners>, by default the <xref:System.Diagnostics.DefaultTraceListener>.</span></span>
  - <span data-ttu-id="ed5e4-132">Usare questa API durante la creazione di log che verranno abilitati nella maggior parte delle compilazioni.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-132">Use this API when creating logs that will be enabled in most builds.</span></span>
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-133">Abilitato solo quando viene definito `DEBUG`.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-133">Only enabled when `DEBUG` is defined.</span></span>
  - <span data-ttu-id="ed5e4-134">Scrive in un debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-134">Writes to an attached debugger.</span></span>
  - <span data-ttu-id="ed5e4-135">In `*nix` scrive in stderr se è impostato `COMPlus_DebugWriteToStdErr`.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-135">On `*nix` writes to stderr if `COMPlus_DebugWriteToStdErr` is set.</span></span>
  - <span data-ttu-id="ed5e4-136">Usare questa API durante la creazione di log che saranno abilitati solo nelle build di debug.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-136">Use this API when creating logs that will be enabled only in debug builds.</span></span>

### <a name="logging-events"></a><span data-ttu-id="ed5e4-137">Registrazione di eventi</span><span class="sxs-lookup"><span data-stu-id="ed5e4-137">Logging events</span></span>

<span data-ttu-id="ed5e4-138">Le API seguenti sono più orientate agli eventi.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-138">The following APIs are more event oriented.</span></span> <span data-ttu-id="ed5e4-139">Anziché registrare semplici stringhe, registrano gli oggetti evento.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-139">Rather than logging simple strings they log event objects.</span></span>

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-140">EventSource è l'API di traccia principale principale di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-140">EventSource is the primary root .NET Core tracing API.</span></span>
  - <span data-ttu-id="ed5e4-141">Disponibile in tutte le versioni .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-141">Available in all .NET Standard versions.</span></span>
  - <span data-ttu-id="ed5e4-142">Consente solo la traccia degli oggetti serializzabili.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-142">Only allows tracing serializable objects.</span></span>
  - <span data-ttu-id="ed5e4-143">Scrive nei listener di [eventi](xref:System.Diagnostics.Tracing.EventListener)collegati.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-143">Writes to the attached [event listeners](xref:System.Diagnostics.Tracing.EventListener).</span></span>
  - <span data-ttu-id="ed5e4-144">.NET Core fornisce i listener per:</span><span class="sxs-lookup"><span data-stu-id="ed5e4-144">.NET Core provides listeners for:</span></span>
    - <span data-ttu-id="ed5e4-145">EventPipe di .NET Core su tutte le piattaforme</span><span class="sxs-lookup"><span data-stu-id="ed5e4-145">.NET Core's EventPipe on all platforms</span></span>
    - [<span data-ttu-id="ed5e4-146">Event Tracing for Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="ed5e4-146">Event Tracing for Windows (ETW)</span></span>](/windows/win32/etw/event-tracing-portal)
    - [<span data-ttu-id="ed5e4-147">Framework di traccia LTTng per Linux</span><span class="sxs-lookup"><span data-stu-id="ed5e4-147">LTTng tracing framework for Linux</span></span>](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-148">Incluso in .NET Core e come [pacchetto NuGet](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-148">Included in .NET Core and as a [NuGet package](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) for .NET Framework.</span></span>
  - <span data-ttu-id="ed5e4-149">Consente la traccia in-process di oggetti non serializzabili.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-149">Allows in-process tracing of non-serializable objects.</span></span>
  - <span data-ttu-id="ed5e4-150">Include un Bridge per consentire la scrittura dei campi selezionati degli oggetti registrati in un <xref:System.Diagnostics.Tracing.EventSource>.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-150">Includes a bridge to allow selected fields of logged objects to be written to an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-151">Consente di identificare in modo definitivo i messaggi di log derivanti da un'attività o una transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-151">Provides a definitive way to identify log messages resulting from a specific activity or transaction.</span></span> <span data-ttu-id="ed5e4-152">Questo oggetto può essere utilizzato per correlare i log tra servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-152">This object can be used to correlate logs across different services.</span></span>

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - <span data-ttu-id="ed5e4-153">Solo Windows.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-153">Windows only.</span></span>
  - <span data-ttu-id="ed5e4-154">Scrive messaggi nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-154">Writes messages to the Windows Event Log.</span></span>
  - <span data-ttu-id="ed5e4-155">Gli amministratori di sistema si aspettano che vengano visualizzati messaggi di errore irreversibili nell'applicazione nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-155">System administrators expect fatal application error messages to appear in the Windows Event Log.</span></span>

## <a name="ilogger-and-logging-frameworks"></a><span data-ttu-id="ed5e4-156">ILogger e Framework di registrazione</span><span class="sxs-lookup"><span data-stu-id="ed5e4-156">ILogger and logging frameworks</span></span>

<span data-ttu-id="ed5e4-157">Le API di basso livello potrebbero non essere la scelta migliore per le esigenze di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-157">The low-level APIs may not be the right choice for your logging needs.</span></span> <span data-ttu-id="ed5e4-158">Si consiglia di prendere in considerazione un Framework di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-158">You may want to consider a logging framework.</span></span>

<span data-ttu-id="ed5e4-159">L'interfaccia <xref:Microsoft.Extensions.Logging.ILogger> è stata usata per creare un'interfaccia di registrazione comune in cui i logger possono essere inseriti tramite l'inserimento di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-159">The <xref:Microsoft.Extensions.Logging.ILogger> interface has been used to create a common logging interface where the loggers can be inserted through dependency injection.</span></span>

<span data-ttu-id="ed5e4-160">Ad esempio, per consentire all'utente di scegliere la scelta migliore per l'applicazione `ASP.NET` offre supporto per la selezione di Framework predefiniti e di terze parti:</span><span class="sxs-lookup"><span data-stu-id="ed5e4-160">For instance, to allow you to make the best choice for your application `ASP.NET` offers support for a selection of built-in and third-party frameworks:</span></span>

- [<span data-ttu-id="ed5e4-161">ASP.NET incorporati nei provider di registrazione</span><span class="sxs-lookup"><span data-stu-id="ed5e4-161">ASP.NET built in logging providers</span></span>](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [<span data-ttu-id="ed5e4-162">ASP.NET provider di registrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="ed5e4-162">ASP.NET Third-party logging providers</span></span>](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a><span data-ttu-id="ed5e4-163">Riferimenti relativi alla registrazione</span><span class="sxs-lookup"><span data-stu-id="ed5e4-163">Logging related references</span></span>

- [<span data-ttu-id="ed5e4-164">Procedura: Compilare in modo condizionale con traccia e debug</span><span class="sxs-lookup"><span data-stu-id="ed5e4-164">How to: Compile Conditionally with Trace and Debug</span></span>](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [<span data-ttu-id="ed5e4-165">Procedura: aggiungere istruzioni di traccia al codice dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ed5e4-165">How to: Add Trace Statements to Application Code</span></span>](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- <span data-ttu-id="ed5e4-166">La [registrazione ASP.NET](/aspnet/core/fundamentals/logging) offre una panoramica delle tecniche di registrazione supportate.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-166">[ASP.NET Logging](/aspnet/core/fundamentals/logging) provides an overview of the logging techniques it supports.</span></span>

- <span data-ttu-id="ed5e4-167">L'interpolazione di stringhe può semplificare la scrittura del codice di registrazione. [ C# ](../../csharp/language-reference/tokens/interpolated.md)</span><span class="sxs-lookup"><span data-stu-id="ed5e4-167">[C# String Interpolation](../../csharp/language-reference/tokens/interpolated.md) can simplify writing logging code.</span></span>

- <span data-ttu-id="ed5e4-168">La proprietà <xref:System.Exception.Message?displayProperty=nameWithType> è utile per la registrazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-168">The <xref:System.Exception.Message?displayProperty=nameWithType> property is useful for logging exceptions.</span></span>

- <span data-ttu-id="ed5e4-169">La classe <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> può essere utile per fornire informazioni sullo stack nei log.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-169">The <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> class can be useful to provide stack info in your logs.</span></span>

## <a name="performance-considerations"></a><span data-ttu-id="ed5e4-170">Considerazioni sulle prestazioni</span><span class="sxs-lookup"><span data-stu-id="ed5e4-170">Performance considerations</span></span>

<span data-ttu-id="ed5e4-171">La formattazione della stringa può richiedere tempi di elaborazione della CPU evidenti.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-171">String formatting can take noticeable CPU processing time.</span></span>

<span data-ttu-id="ed5e4-172">Nelle applicazioni critiche per le prestazioni, è consigliabile:</span><span class="sxs-lookup"><span data-stu-id="ed5e4-172">In performance critical applications, it's recommended that you:</span></span>

- <span data-ttu-id="ed5e4-173">Evitare una grande quantità di registrazione quando nessuno è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-173">Avoid lots of logging when no one is listening.</span></span> <span data-ttu-id="ed5e4-174">Evitare di creare costosi messaggi di registrazione controllando che la registrazione sia abilitata per prima.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-174">Avoid constructing costly logging messages by checking if logging is enabled first.</span></span>
- <span data-ttu-id="ed5e4-175">Registra solo le informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-175">Only log what's useful.</span></span>
- <span data-ttu-id="ed5e4-176">Rinvia la formattazione in modo sofisticato alla fase di analisi.</span><span class="sxs-lookup"><span data-stu-id="ed5e4-176">Defer fancy formatting to the analysis stage.</span></span>
