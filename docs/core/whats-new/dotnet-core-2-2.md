---
title: Novità di .NET Core 2.2
description: Informazioni sulle nuove funzionalità in .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: e045c39240c99777d05ca86ee0a8cd1fa4309c4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156582"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="0529d-103">Novità di .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="0529d-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="0529d-104">.NET Core 2.2 include miglioramenti alla distribuzione delle applicazioni, alla gestione degli eventi per i servizi di runtime, all'autenticazione ai database SQL di Azure, alle prestazioni del compilatore JIT e all'inserimento di codice prima dell'esecuzione del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="0529d-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="0529d-105">Nuova modalità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="0529d-105">New deployment mode</span></span>

<span data-ttu-id="0529d-106">A partire da .NET Core 2.2, è possibile distribuire [file eseguibili dipendenti dal framework](../deploying/index.md#publish-runtime-dependent), che sono file **EXE** invece di file **DLL**.</span><span class="sxs-lookup"><span data-stu-id="0529d-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#publish-runtime-dependent), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="0529d-107">I file eseguibili dipendenti dal framework, pur avendo funzionalità simili a quelle delle distribuzioni dipendenti dal framework, per l'esecuzione si basano tuttavia sulla presenza di una versione di .NET Core condivisa a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="0529d-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="0529d-108">L'app contiene solo il codice e le dipendenze di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0529d-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="0529d-109">Diversamente dalle distribuzioni dipendenti dal framework, i file eseguibili dipendenti dal framework sono specifici della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="0529d-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="0529d-110">Questa nuova modalità di distribuzione offre il particolare vantaggio di compilare un file eseguibile invece di una libreria ed è quindi possibile eseguire l'app direttamente senza richiamare prima `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="0529d-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="0529d-111">Core</span><span class="sxs-lookup"><span data-stu-id="0529d-111">Core</span></span>

<span data-ttu-id="0529d-112">**Gestione degli eventi nei servizi di runtime**</span><span class="sxs-lookup"><span data-stu-id="0529d-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="0529d-113">Potrebbe essere necessario monitorare spesso l'uso da parte dell'applicazione dei servizi di runtime, ad esempio GC, JIT e ThreadPool, per conoscerne l'impatto sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0529d-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="0529d-114">Nei sistemi Windows questa operazione viene in genere eseguita monitorando gli eventi ETW del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="0529d-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="0529d-115">Anche se questa soluzione è ancora valida, non è sempre possibile usare ETW se si effettua l'esecuzione in un ambiente con privilegi limitati oppure in Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="0529d-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span>

<span data-ttu-id="0529d-116">A partire da .NET Core 2.2, gli eventi CoreCLR possono essere utilizzati con la classe <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0529d-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0529d-117">Questi eventi descrivono il comportamento di servizi di runtime come GC, JIT, ThreadPool e interop.</span><span class="sxs-lookup"><span data-stu-id="0529d-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="0529d-118">Si tratta degli stessi eventi esposti come parte del provider ETW CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0529d-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="0529d-119">In questo modo le applicazioni possono utilizzare gli eventi o usare un meccanismo di trasporto per inviarli a un servizio di aggregazione dei dati di telemetria.</span><span class="sxs-lookup"><span data-stu-id="0529d-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="0529d-120">È possibile vedere come sottoscrivere gli eventi nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0529d-120">You can see how to subscribe to events in the following code sample:</span></span>

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

<span data-ttu-id="0529d-121">.NET Core 2.2 aggiunge anche le due proprietà seguenti alla classe <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> per fornire informazioni aggiuntive sugli eventi ETW:</span><span class="sxs-lookup"><span data-stu-id="0529d-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="0529d-122">Data</span><span class="sxs-lookup"><span data-stu-id="0529d-122">Data</span></span>

<span data-ttu-id="0529d-123">**Autenticazione AAD ai database SQL di Azure con la proprietà SqlConnection.AccessToken**</span><span class="sxs-lookup"><span data-stu-id="0529d-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="0529d-124">A partire da .NET Core 2.2, un token di accesso rilasciato da Azure Active Directory può essere usato per l'autenticazione a un database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="0529d-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="0529d-125">Per supportare i token di accesso, è stata aggiunta la proprietà <xref:System.Data.SqlClient.SqlConnection.AccessToken> alla classe <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="0529d-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="0529d-126">Per sfruttare l'autenticazione AAD, scaricare la versione 4.6 del pacchetto NuGet System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="0529d-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="0529d-127">Per usare la funzionalità, è possibile ottenere il valore del token di accesso usando lo strumento [Active Directory Authentication Library per .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contenuto nel pacchetto NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="0529d-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="0529d-128">Miglioramenti del compilatore JIT</span><span class="sxs-lookup"><span data-stu-id="0529d-128">JIT compiler improvements</span></span>

<span data-ttu-id="0529d-129">**La compilazione a livelli rimane una funzionalità con consenso esplicito**</span><span class="sxs-lookup"><span data-stu-id="0529d-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="0529d-130">In .NET Core 2.1 il compilatore JIT ha implementato una nuova tecnologia, la *compilazione a livelli*, come funzionalità con consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="0529d-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="0529d-131">L'obiettivo della compilazione a livelli è il miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0529d-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="0529d-132">Una delle attività importanti eseguite dal compilatore JIT è l'ottimizzazione dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="0529d-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="0529d-133">Per i percorsi del codice poco usati, tuttavia, il compilatore può richiedere più tempo per l'ottimizzazione del codice rispetto a quanto impiegato dal runtime per l'esecuzione del codice non ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="0529d-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="0529d-134">La compilazione a livelli introduce due fasi nella compilazione JIT:</span><span class="sxs-lookup"><span data-stu-id="0529d-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="0529d-135">Un **primo livello**, che genera il codice il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="0529d-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="0529d-136">Un **secondo livello**, che genera codice ottimizzato per i metodi che vengono eseguiti frequentemente.</span><span class="sxs-lookup"><span data-stu-id="0529d-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="0529d-137">Il secondo livello di compilazione viene eseguito in parallelo per prestazioni migliorate.</span><span class="sxs-lookup"><span data-stu-id="0529d-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="0529d-138">Per informazioni sul miglioramento delle prestazioni che può derivare dalla compilazione a livelli, vedere [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/) (Annuncio di .NET Core 2.2 Preview 2).</span><span class="sxs-lookup"><span data-stu-id="0529d-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="0529d-139">In .NET Core 2.2 Preview 2 la compilazione a livelli era abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0529d-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="0529d-140">È stato tuttavia deciso che non è ancora il momento opportuno per abilitare la compilazione a livelli per impostazione predefinita,</span><span class="sxs-lookup"><span data-stu-id="0529d-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="0529d-141">quindi in .NET Core 2.2 la compilazione a livelli è ancora una funzionalità con consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="0529d-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="0529d-142">Per informazioni sul consenso esplicito alla compilazione a livelli, vedere [Miglioramenti del compilatore JIT](dotnet-core-2-1.md#jit-compiler-improvements) in [Novità di .NET Core 2.1](dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="0529d-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="0529d-143">Runtime</span><span class="sxs-lookup"><span data-stu-id="0529d-143">Runtime</span></span>

<span data-ttu-id="0529d-144">**Inserimento di codice prima dell'esecuzione del metodo Main**</span><span class="sxs-lookup"><span data-stu-id="0529d-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="0529d-145">A partire da .NET Core 2.2, è possibile usare un hook di avvio per inserire il codice prima di eseguire il metodo Main dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0529d-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="0529d-146">Gli hook di avvio consentono a un host di personalizzare il comportamento delle applicazioni dopo che sono state distribuite senza doverle ricompilare o modificare.</span><span class="sxs-lookup"><span data-stu-id="0529d-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="0529d-147">Si prevede che i provider di hosting definiscano la configurazione e i criteri personalizzati, incluse le impostazioni che potrebbero influenzare il comportamento di caricamento del punto di ingresso principale, ad esempio il comportamento  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0529d-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="0529d-148">L'hook può essere usato per configurare l'analisi o l'inserimento dei dati di telemetria, per configurare i callback per la gestione o per definire altri comportamenti dipendenti dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0529d-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="0529d-149">L'hook è separato dal punto di ingresso, quindi il codice utente non deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="0529d-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="0529d-150">Per altre informazioni, vedere [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) (Hook di avvio degli host).</span><span class="sxs-lookup"><span data-stu-id="0529d-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="0529d-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0529d-151">See also</span></span>

- [<span data-ttu-id="0529d-152">Novità di .NET Core</span><span class="sxs-lookup"><span data-stu-id="0529d-152">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="0529d-153">Novità di ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="0529d-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="0529d-154">Nuove funzionalità di EF Core 2.2</span><span class="sxs-lookup"><span data-stu-id="0529d-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
