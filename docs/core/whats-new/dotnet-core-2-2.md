---
title: Novità di .NET Core 2.2
description: Informazioni sulle nuove funzionalità in .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 9495288658fa102df8f0fbd643e2fcdf49d8f3b3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451980"
---
# <a name="whats-new-in-net-core-22"></a>Novità di .NET Core 2.2

.NET Core 2.2 include miglioramenti alla distribuzione delle applicazioni, alla gestione degli eventi per i servizi di runtime, all'autenticazione ai database SQL di Azure, alle prestazioni del compilatore JIT e all'inserimento di codice prima dell'esecuzione del metodo `Main`.

## <a name="new-deployment-mode"></a>Nuova modalità di distribuzione

A partire da .NET Core 2.2, è possibile distribuire [file eseguibili dipendenti dal framework](../deploying/index.md#publish-runtime-dependent), che sono file **EXE** invece di file **DLL**. I file eseguibili dipendenti dal framework, pur avendo funzionalità simili a quelle delle distribuzioni dipendenti dal framework, per l'esecuzione si basano tuttavia sulla presenza di una versione di .NET Core condivisa a livello di sistema. L'app contiene solo il codice e le dipendenze di terze parti. Diversamente dalle distribuzioni dipendenti dal framework, i file eseguibili dipendenti dal framework sono specifici della piattaforma.

Questa nuova modalità di distribuzione offre il particolare vantaggio di compilare un file eseguibile invece di una libreria ed è quindi possibile eseguire l'app direttamente senza richiamare prima `dotnet`.

## <a name="core"></a>Base

**Gestione degli eventi nei servizi di runtime**

Potrebbe essere necessario monitorare spesso l'uso da parte dell'applicazione dei servizi di runtime, ad esempio GC, JIT e ThreadPool, per conoscerne l'impatto sull'applicazione. Nei sistemi Windows, questa operazione viene eseguita in genere monitorando gli eventi ETW del processo corrente. Sebbene questo continui a funzionare correttamente, non è sempre possibile usare ETW se si esegue in un ambiente con privilegi limitati o in Linux o macOS. 

A partire da .NET Core 2.2, gli eventi CoreCLR possono essere utilizzati con la classe <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>. Questi eventi descrivono il comportamento di servizi di runtime come GC, JIT, ThreadPool e interop. Si tratta degli stessi eventi esposti come parte del provider ETW CoreCLR.  In questo modo, le applicazioni possono utilizzare questi eventi o utilizzare un meccanismo di trasporto per inviarli a un servizio di aggregazione dei dati di telemetria. È possibile vedere come sottoscrivere gli eventi nell'esempio di codice seguente:

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

.NET Core 2.2 aggiunge anche le due proprietà seguenti alla classe <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> per fornire informazioni aggiuntive sugli eventi ETW:

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a>Data

**Autenticazione AAD ai database SQL di Azure con la proprietà SqlConnection.AccessToken**

A partire da .NET Core 2.2, un token di accesso rilasciato da Azure Active Directory può essere usato per l'autenticazione a un database SQL di Azure. Per supportare i token di accesso, è stata aggiunta la proprietà <xref:System.Data.SqlClient.SqlConnection.AccessToken> alla classe <xref:System.Data.SqlClient.SqlConnection>. Per sfruttare l'autenticazione AAD, scaricare la versione 4.6 del pacchetto NuGet System.Data.SqlClient. Per usare la funzionalità, è possibile ottenere il valore del token di accesso usando lo strumento [Active Directory Authentication Library per .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contenuto nel pacchetto NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

## <a name="jit-compiler-improvements"></a>Miglioramenti del compilatore JIT

**La compilazione a livelli rimane una funzionalità con consenso esplicito**

In .NET Core 2.1 il compilatore JIT ha implementato una nuova tecnologia, la *compilazione a livelli*, come funzionalità con consenso esplicito. L'obiettivo della compilazione a livelli è il miglioramento delle prestazioni. Una delle attività importanti eseguite dal compilatore JIT è l'ottimizzazione dell'esecuzione del codice. Per i percorsi del codice poco usati, tuttavia, il compilatore può richiedere più tempo per l'ottimizzazione del codice rispetto a quanto impiegato dal runtime per l'esecuzione del codice non ottimizzato. La compilazione a livelli introduce due fasi nella compilazione JIT:

- Un **primo livello**, che genera il codice il più rapidamente possibile.

- Un **secondo livello**, che genera codice ottimizzato per i metodi che vengono eseguiti frequentemente. Il secondo livello di compilazione viene eseguito in parallelo per prestazioni migliorate.

Per informazioni sul miglioramento delle prestazioni che può derivare dalla compilazione a livelli, vedere [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/) (Annuncio di .NET Core 2.2 Preview 2).

In .NET Core 2.2 Preview 2 la compilazione a livelli era abilitata per impostazione predefinita. È stato tuttavia deciso che non è ancora il momento opportuno per abilitare la compilazione a livelli per impostazione predefinita, quindi in .NET Core 2.2 la compilazione a livelli è ancora una funzionalità con consenso esplicito. Per informazioni sul consenso esplicito alla compilazione a livelli, vedere [Miglioramenti del compilatore JIT](dotnet-core-2-1.md#jit-compiler-improvements) in [Novità di .NET Core 2.1](dotnet-core-2-1.md).

## <a name="runtime"></a>Tipo

**Inserimento di codice prima dell'esecuzione del metodo Main**

A partire da .NET Core 2.2, è possibile usare un hook di avvio per inserire il codice prima di eseguire il metodo Main dell'applicazione. Gli hook di avvio consentono a un host di personalizzare il comportamento delle applicazioni dopo che sono state distribuite senza doverle ricompilare o modificare.

Si prevede che i provider di hosting definiscano la configurazione e i criteri personalizzati, incluse le impostazioni che potrebbero influenzare il comportamento di caricamento del punto di ingresso principale, ad esempio il comportamento  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> . L'hook può essere usato per configurare l'analisi o l'inserimento dei dati di telemetria, per configurare i callback per la gestione o per definire altri comportamenti dipendenti dall'ambiente. L'hook è separato dal punto di ingresso, quindi il codice utente non deve essere modificato.

Per altre informazioni, vedere [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) (Hook di avvio degli host).

## <a name="see-also"></a>Vedere anche

- [What's new in .NET Core](index.md) (Novità di .NET Core)
- [Novità di ASP.NET Core 2.2](/aspnet/core/release-notes/aspnetcore-2.2)
- [Nuove funzionalità di EF Core 2.2](/ef/core/what-is-new/ef-core-2.2)
