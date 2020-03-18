---
title: Generare e usare flussi asincroni
description: Questa esercitazione avanzata illustra gli scenari in cui la generazione e l'uso di flussi asincroni rappresenta un modo più naturale di lavorare con sequenze di dati che potrebbero essere generate in modo asincrono.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: de090eb9cc1e8b511956313ab5169ee4d07a492f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156740"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a>Esercitazione: Generare e utilizzare flussi asincroni con C .

C# 8.0 introduce i **flussi asincroni**, che modellano un'origine di dati di flusso quando gli elementi nel flusso di dati possono essere recuperati o generati in modo asincrono. I flussi asincroni si basano sulle nuove interfacce introdotte in .NET Standard 2.1 e implementate in .NET Core 3.0 per fornire un modello di programmazione naturale per origini dati di flusso asincrone.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Creare un'origine dati che genera una sequenza di elementi di dati in modo asincrono.
> - Utilizzare tale origine dati in modo asincrono.
> - Riconoscere quando la nuova interfaccia e l'origine dati sono da preferire rispetto alle sequenze di dati sincrone precedenti.

## <a name="prerequisites"></a>Prerequisites

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore c'è 8.0. Il compilatore di C'è 8 è disponibile a partire da [Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o [.NET Core 3.0 SDK.](https://dotnet.microsoft.com/download)

È necessario creare un [token di accesso di GitHub](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) per poter accedere all'endpoint GraphQL di GitHub. Selezionare le autorizzazioni seguenti per il token di accesso di GitHub:

- repo:status
- public_repo

Salvare il token di accesso in un luogo sicuro in modo da poterlo usare per ottenere l'accesso all'endpoint dell'API GitHub.

> [!WARNING]
> Mantenere protetto il token di accesso personale. Qualsiasi software con il token di accesso personale può effettuare chiamate API GitHub tramite i diritti di accesso.

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="run-the-starter-application"></a>Eseguire l'applicazione iniziale

È possibile ottenere il codice per l'applicazione iniziale usato in questa esercitazione dal repository [dotnet/samples](https://github.com/dotnet/samples) nella cartella [csharp/esercitazioni/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start).

L'applicazione iniziale è un'applicazione console che usa l'interfaccia [GraphQL di GitHub](https://developer.github.com/v4/) per recuperare i problemi recenti scritti nel repository [dotnet/docs](https://github.com/dotnet/docs). Per iniziare, esaminare il codice seguente per il metodo `Main` dell'app iniziale:

[!code-csharp[StarterAppMain](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

È possibile impostare una variabile di ambiente `GitHubKey` per il token di accesso personale oppure è possibile sostituire l'ultimo argomento nella chiamata a `GenEnvVariable` con il token di accesso personale. Non inserire il codice di accesso nel codice sorgente se l'origine verrà salvata insieme ad altre oppure inserirlo in un repository di codice sorgente condiviso.

Dopo aver creato il client di GitHub, il codice in `Main` crea un oggetto di segnalazione dello stato e un token di annullamento. Dopo aver creato questi oggetti, `Main` chiama `runPagedQueryAsync` per recuperare i 250 problemi creati più di recente. Al termine di tale attività, vengono visualizzati i risultati.

Quando si esegue l'applicazione iniziale, è possibile notare alcuni aspetti importanti della modalità di esecuzione di questa applicazione.  Lo stato viene segnalato per ogni pagina restituita da GitHub. È possibile notare una notevole pausa prima che GitHub restituisca ogni nuova pagina di problemi. Infine, i problemi vengono visualizzati solo dopo aver recuperato tutte e 10 le pagine da GitHub.

## <a name="examine-the-implementation"></a>Esaminare l'implementazione

L'implementazione spiega il comportamento evidenziato nella sezione precedente. Esaminare il codice per `runPagedQueryAsync`:

[!code-csharp[RunPagedQueryStarter](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

Concentrarsi sull'algoritmo per la suddivisione in pagine e sulla struttura asincrona del codice precedente. (È possibile consultare la documentazione di [GitHub GraphQL](https://developer.github.com/v4/guides/) per informazioni dettagliate sull'API GraphQL GitHub.) Il `runPagedQueryAsync` metodo enumera i problemi dal più recente al meno recente. Richiede 25 problemi per ogni pagina ed esamina la struttura `pageInfo` della risposta per continuare con la pagina precedente. Viene rispettato il supporto della suddivisione in pagine standard di GraphQL per le risposte a più pagine. La risposta include un oggetto `pageInfo` che include un valore `hasPreviousPages` e un valore `startCursor` usato per richiedere la pagina precedente. I problemi sono nella matrice `nodes`. Il metodo `runPagedQueryAsync` aggiunge questi nodi in una matrice che contiene tutti i risultati da tutte le pagine.

Dopo il recupero e il ripristino di una pagina di risultati, `runPagedQueryAsync` segnala lo stato e verifica se è presente una richiesta di annullamento. In caso affermativo, `runPagedQueryAsync` genera un'eccezione <xref:System.OperationCanceledException>.

Esistono diversi elementi in questo codice che possono essere migliorati. Soprattutto, `runPagedQueryAsync` deve allocare spazio di archiviazione per tutti i problemi restituiti. Questo esempio si arresta dopo 250 problemi, perché il recupero di tutti i problemi richiede molta più memoria per archiviare tutti i problemi recuperati. Inoltre, i protocolli per supportare lo stato di avanzamento e l'annullamento rendono l'algoritmo più difficile da comprendere a una prima lettura. È necessario cercare la classe dello stato per scoprire dove viene segnalato lo stato di avanzamento. Occorre anche analizzare le comunicazioni con <xref:System.Threading.CancellationTokenSource> e l'identificatore associato <xref:System.Threading.CancellationToken> per comprendere dove viene richiesto l'annullamento e dove viene concesso.

## <a name="async-streams-provide-a-better-way"></a>I flussi asincroni sono più efficaci

I flussi asincroni e il supporto del linguaggio associato offrono una risposta a tutte queste problematiche. Il codice che genera la sequenza può ora usare `yield return` per restituire gli elementi in un metodo dichiarato con il modificatore `async`. È possibile utilizzare un flusso asincrono con un ciclo `await foreach`, proprio come si utilizza qualsiasi sequenza con un ciclo `foreach`.

Queste nuove funzionalità del linguaggio dipendono da tre nuove interfacce aggiunte a .NET 2.1 Standard e implementate in .NET Core 3.0:

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

Queste tre interfacce dovrebbero risultare familiari alla maggior parte degli sviluppatori C#. Il comportamento è simile a quello delle relative controparti sincrone:

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

Un tipo che potrebbe essere poco noto è <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>. Lo struct `ValueTask` fornisce un'API simile alla classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>. `ValueTask` viene usato in queste interfacce per motivi di prestazioni.

## <a name="convert-to-async-streams"></a>Convertire in flussi asincroni

A questo punto, il metodo `runPagedQueryAsync` verrà convertito per generare un flusso asincrono. In primo luogo, modificare la firma di `runPagedQueryAsync` per restituire `IAsyncEnumerable<JToken>` e rimuovere il token di annullamento e gli oggetti di stato dall'elenco di parametri, come illustrato nel codice seguente:

[!code-csharp[FinishedSignature](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

Il codice iniziale elabora ogni pagina quando viene recuperata, come illustrato nel codice seguente:

[!code-csharp[StarterPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

Sostituire queste tre righe con il codice seguente:

[!code-csharp[FinishedPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

È anche possibile rimuovere la dichiarazione di `finalResults` più indietro in questo metodo e l'istruzione `return` che segue il ciclo modificato.

Sono state completate le modifiche per generare un flusso asincrono. Il metodo completato deve assomigliare al codice riportato di seguito:

[!code-csharp[FinishedGenerate](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

Verrà ora modificato il codice che utilizza la raccolta per utilizzare il flusso asincrono. Trovare il codice seguente in `Main` che elabora la raccolta dei problemi:

[!code-csharp[EnumerateOldStyle](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

Sostituire il codice con il ciclo `await foreach` seguente:

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

Per impostazione predefinita, gli elementi di flusso vengono elaborati nel contesto acquisito. Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione. Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo [sull'utilizzo del modello asincrono basato su attività](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

È possibile ottenere il codice per l'esercitazione completata dal repository [dotnet/samples](https://github.com/dotnet/samples) nella cartella [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished).

## <a name="run-the-finished-application"></a>Eseguire l'applicazione completata

Eseguire di nuovo l'applicazione. Confrontare il comportamento con il comportamento dell'applicazione iniziale. La prima pagina di risultati viene enumerata non appena è disponibile. Esiste una pausa osservabile quando viene richiesta e recuperata ogni nuova pagina, poi i risultati della pagina successiva vengono enumerati rapidamente. Il blocco `try` / `catch` non è necessario per gestire l'annullamento: il chiamante può interrompere l'enumerazione della raccolta. Lo stato viene segnalato in modo chiaro perché il flusso asincrono genera i risultati quando viene scaricata ogni pagina. Lo stato di ogni problema restituito è `await foreach` incluso senza problemi nel ciclo. Non è necessario un oggetto callback per tenere traccia dello stato di avanzamento.

È possibile notare miglioramenti per l'uso della memoria esaminando il codice. Non è più necessario allocare una raccolta per archiviare tutti i risultati prima che vengano enumerati. Il chiamante può determinare come utilizzare i risultati e se è necessaria una raccolta di archiviazione.

Eseguire sia l'applicazione iniziale che quella finita per osservare in autonomia le differenze tra le implementazioni. Al termine, è possibile eliminare il token di accesso di GitHub creato all'inizio di questa esercitazione. Se un utente malintenzionato riesce ad accedere al token, potrebbe ottenere l'accesso alle a API di GitHub usando le credenziali.
