---
title: Creare un client REST usando .NET Core
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: c7b7e9803b0c05f4956f5c007bca8aa4b200cfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208020"
---
# <a name="rest-client"></a>Client REST

Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#. Verranno affrontati gli argomenti seguenti:

* Nozioni di base del interfaccia della riga di comando di .NET Core.
* Panoramica delle funzionalità del linguaggio C#
* Gestione delle dipendenze con NuGet
* Comunicazioni HTTP
* Elaborazione delle informazioni JSON
* Gestione della configurazione con attributi

Si creerà un'applicazione che invia richieste HTTP a un servizio REST su GitHub, si leggeranno informazioni in formato JSON e si convertirà il pacchetto JSON in oggetti C#. Si imparerà infine a usare e gestire oggetti C#.

Questa esercitazione include molte funzionalità. numerose funzionalità.

Se si vuole proseguire, è possibile scaricare l'[esempio finale](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) di questo argomento. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET core. È possibile trovare le istruzioni di installazione nella pagina di [download di .NET Core](https://dotnet.microsoft.com/download) . Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.
È necessario installare l'editor di codice preferito. Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma, ma è possibile usare gli strumenti con cui si ha maggiore familiarità.

## <a name="create-the-application"></a>Creare l'applicazione

Il primo passaggio consiste nel creare una nuova applicazione. Aprire un prompt dei comandi e creare una nuova directory per l'applicazione, impostandola come directory corrente. Immettere il comando seguente in una finestra della console:

```dotnetcli
dotnet new console --name WebApiClient
```

Questa operazione crea i file iniziali per un'applicazione "Hello World" di base. Il nome del progetto è "WebApiClient". Poiché si tratta di un nuovo progetto, non è presente alcuna dipendenza. La prima esecuzione consente di scaricare il Framework .NET Core, installare un certificato di sviluppo ed eseguire Gestione pacchetti NuGet per ripristinare le dipendenze mancanti.

Prima di iniziare ad apportare modifiche, digitare `dotnet run` ([vedere la nota](#dotnet-restore-note)) al prompt dei comandi per eseguire l'applicazione. `dotnet run` esegue automaticamente `dotnet restore` se nell'ambiente mancano dipendenze. Esegue anche `dotnet build` se l'applicazione deve essere ricompilata.
Dopo l'installazione iniziale, sarà necessario solo eseguire `dotnet restore` o `dotnet build` quando ha senso per il progetto.

## <a name="adding-new-dependencies"></a>Aggiunta di nuove dipendenze

Uno degli obiettivi di progettazione principali di .NET Core è ridurre al minimo le dimensioni dell'installazione di .NET. Se per alcune delle funzionalità di un'applicazione sono necessarie altre librerie, è possibile aggiungere tali dipendenze al file di progetto C# (\*.csproj). Per questo esempio, è necessario aggiungere il `System.Runtime.Serialization.Json` pacchetto, in modo che l'applicazione possa elaborare le risposte JSON.

È necessario il `System.Runtime.Serialization.Json` pacchetto per questa applicazione. Aggiungerlo al progetto eseguendo il comando seguente dell' [interfaccia](../../core/tools/dotnet-add-package.md) della riga di comando di .NET:

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a>Esecuzione di richieste Web

Si è ora pronti per iniziare a recuperare dati dal Web. In questa applicazione si leggeranno informazioni dall'[API GitHub](https://developer.github.com/v3/). In particolare, si leggeranno informazioni sui progetti nell'ambito di [.NET Foundation](https://www.dotnetfoundation.org/). Si inizierà inviando all'API GitHub la richiesta di recuperare informazioni sui progetti. L'endpoint che verrà usato è: <https://api.github.com/orgs/dotnet/repos>. Poiché si vuole recuperare tutte le informazioni su questi progetti, si userà una richiesta HTTP GET.
Anche il browser usa richieste HTTP GET ed è quindi possibile incollare l'URL nel browser per visualizzare le informazioni che si riceveranno ed elaboreranno.

Per eseguire richieste Web, usare la classe <xref:System.Net.Http.HttpClient>. Come tutte le API .NET moderne, <xref:System.Net.Http.HttpClient> supporta solo metodi asincroni per le API a esecuzione prolungata.
È quindi necessario iniziare creando un metodo asincrono, che verrà inserito nell'implementazione mentre si compila la funzionalità dell'applicazione. Iniziare aprendo il file `program.cs` nella directory del progetto e aggiungendo il metodo seguente alla classe `Program`:

```csharp
private static async Task ProcessRepositories()
{
}
```

È necessario aggiungere una `using` direttiva all'inizio del `Main` metodo, in modo che il compilatore C# riconosca il <xref:System.Threading.Tasks.Task> tipo:

```csharp
using System.Threading.Tasks;
```

Se si compila il progetto in questo momento, viene generato un avviso per indicare che il metodo non contiene alcun operatore `await` e verrà quindi eseguito in modo sincrono. Ignorare temporaneamente il messaggio. Si aggiungeranno operatori `await` durante la compilazione del metodo.

Aggiornare quindi il `Main` metodo per chiamare il `ProcessRepositories` metodo. Il `ProcessRepositories` metodo restituisce un'attività e non è necessario uscire dal programma prima del completamento dell'attività. Pertanto, è necessario modificare la firma di `Main` . Aggiungere il `async` modificatore e modificare il tipo restituito in `Task` . Quindi, nel corpo del metodo, aggiungere una chiamata a `ProcessRepositories` . Aggiungere la `await` parola chiave alla chiamata al metodo:

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

Si dispone a questo punto di un programma che, pur non eseguendo alcuna operazione, opera in modo asincrono. È ora possibile migliorarlo.

È necessario innanzitutto un oggetto in grado di recuperare i dati dal Web; a tale scopo è possibile usare <xref:System.Net.Http.HttpClient>. per gestire la richiesta e le risposte. Creare un'istanza di una singola istanza di quel tipo nella `Program` classe all'interno del file *Program.cs* .

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

Tornare quindi al metodo `ProcessRepositories` e compilarne una prima versione:

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

È necessario aggiungere anche due nuove `using` direttive all'inizio del file affinché questo venga compilato:

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

Questa prima versione esegue una richiesta Web per leggere l'elenco di tutti i repository presenti nell'organizzazione DotNet Foundation. L'ID di GitHub per .NET Foundation è 'dotnet'. Nelle prime righe l'oggetto <xref:System.Net.Http.HttpClient> viene impostato per questa richiesta, ma prima viene configurato per accettare le risposte JSON di GitHub.
Questo formato è semplicemente JSON. Nella riga successiva viene aggiunta un'intestazione Agente utente a tutte le richieste provenienti da questo oggetto. Queste due intestazioni vengono controllate dal codice server di GitHub e sono necessarie per recuperare informazioni da GitHub.

Dopo aver configurato l'oggetto <xref:System.Net.Http.HttpClient>, si eseguirà una richiesta Web e si recupererà la risposta. In questa prima versione viene usato il metodo pratico <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>. Questo metodo avvia un'attività che esegue la richiesta Web e, quando la richiesta viene restituita, legge il flusso di risposta e ne estrae il contenuto. Il corpo della risposta viene restituito come <xref:System.String>. La stringa è disponibile quando l'attività viene completata.

Le ultime due righe di questo metodo attendono che l'attività sia completata e visualizzano la risposta nella console.
Compilare l'app ed eseguirla. Il messaggio di avviso non viene più visualizzato perché `ProcessRepositories` contiene ora un operatore `await`. Verrà visualizzata una lunga schermata di testo JSON formattato.

## <a name="processing-the-json-result"></a>Elaborazione del risultato JSON

A questo punto è stato scritto il codice per recuperare una risposta da un server Web e visualizzare il testo contenuto nella risposta. Si convertirà ora la risposta JSON in oggetti C#.

La <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> classe serializza gli oggetti in JSON e DESERIALIZZA JSON in oggetti. Per iniziare, definire una classe per rappresentare l' `repo` oggetto JSON restituito dall'API GitHub:

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

Inserire il codice precedente in un nuovo file denominato 'repo.cs'. Questa versione della classe rappresenta il percorso più semplice per elaborare dati JSON. Il nome della classe e il nome del membro corrispondono ai nomi usati nel pacchetto JSON, anziché alle convenzioni C# seguenti. Questo errore verrà risolto in un secondo momento specificando alcuni attributi di configurazione. Questa classe dimostra un'altra caratteristica importante delle funzioni di serializzazione e deserializzazione JSON: non tutti i campi del pacchetto JSON fanno parte della classe.
Il serializzatore JSON ignorerà le informazioni non incluse nel tipo di classe in uso.
In questo modo sarà più semplice creare tipi compatibili con un solo subset dei campi presenti nel pacchetto JSON.

Dopo aver creato il tipo, è possibile deserializzarlo.

Si userà infine il serializzatore per convertire i dati JSON in oggetti C#. Sostituire la chiamata a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> nel `ProcessRepositories` metodo con le righe seguenti:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

Si sta usando un nuovo spazio dei nomi, quindi è necessario aggiungerlo anche all'inizio del file:

```csharp
using System.Text.Json;
```

Si noti che ora viene usato <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anziché <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>. Il serializzatore usa un flusso anziché una stringa come origine. Verranno ora illustrate alcune funzionalità del linguaggio C# utilizzate nella seconda riga del frammento di codice precedente. Il primo argomento per <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> è un' `await` espressione. Gli altri due parametri sono facoltativi e vengono omessi nel frammento di codice. Le espressioni await possono apparire praticamente in qualsiasi punto del codice, anche se fino a questo momento sono state viste solo come parte di un'istruzione di assegnazione. Il `Deserialize` metodo è *generico*, pertanto è necessario fornire gli argomenti di tipo per il tipo di oggetti che devono essere creati dal testo JSON. In questo esempio si esegue la deserializzazione in un `List<Repository>` oggetto, ovvero un altro oggetto generico, il <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> . La `List<>` classe archivia una raccolta di oggetti. L'argomento tipo dichiara il tipo di oggetti archiviati in `List<>` . Il testo JSON rappresenta una raccolta di oggetti repository, quindi l'argomento di tipo è `Repository` .

Questa sezione è quasi completata. Ora che i dati JSON sono stati convertiti in oggetti C#, verrà visualizzato il nome di ogni repository. Sostituire le righe seguenti:

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

con il codice seguente:

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

Compilare l'applicazione ed eseguirla. Verranno stampati i nomi dei repository che fanno parte di .NET Foundation.

## <a name="controlling-serialization"></a>Controllo della serializzazione

Prima di aggiungere altre funzionalità, è possibile indirizzare la `name` proprietà tramite l' `[JsonPropertyName]` attributo. A questo scopo, eseguire le modifiche seguenti alla dichiarazione del campo `name` in repo.cs:

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

Per utilizzare l' `[JsonPropertyName]` attributo, sarà necessario aggiungere lo <xref:System.Text.Json.Serialization> spazio dei nomi alle `using` direttive:

```csharp
using System.Text.Json.Serialization;
```

Con questa operazione si modifica il codice che scrive il nome di ogni repository in program.cs:

```csharp
Console.WriteLine(repo.Name);
```

Eseguire `dotnet run` per assicurarsi che i mapping siano corretti. L'output ottenuto dovrebbe essere uguale a quello precedente.

Si apporterà di seguito un'ultima modifica prima di aggiungere nuove funzionalità. Il metodo `ProcessRepositories` può operare in modo asincrono e restituire una raccolta di repository. È ora necessario fare in modo che il metodo restituisca `List<Repository>` e spostare il codice che scrive le informazioni nel metodo `Main`.

Modificare la firma di `ProcessRepositories` in modo da restituire un'attività il cui risultato sia un elenco di oggetti `Repository`:

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

Restituire quindi i repository dopo aver elaborato la risposta JSON:

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

Il compilatore genera l'oggetto `Task<T>` come elemento restituito perché il metodo è stato contrassegnato come `async`.
Si modificherà ora il metodo `Main` in modo che acquisisca i risultati e scriva ogni nome di repository nella console. Il metodo `Main` avrà ora un aspetto simile al seguente:

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a>Lettura di altre informazioni

Per completare l'esercitazione si elaboreranno ora altre proprietà del pacchetto JSON inviato dall'API di GitHub. Non si intende acquisire tutte le informazioni possibili ma, aggiungendo alcune proprietà, sarà possibile illustrare qualche altra funzionalità del linguaggio C#.

Si inizierà aggiungendo altri tipi semplici alla definizione di classe `Repository`. Aggiungere quindi alla classe le proprietà seguenti:

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

In queste proprietà sono incorporate conversioni dal tipo stringa (il contenuto dei pacchetti JSON) al tipo di destinazione. Il tipo <xref:System.Uri>, che per alcuni utenti può essere nuovo, rappresenta un URI o, come in questo caso, un URL. Nel caso dei tipi `Uri` e `int`, se il pacchetto JSON contiene dati che non possono essere convertiti nel tipo di destinazione, l'azione di serializzazione genererà un'eccezione.

Dopo aver aggiunto queste proprietà, aggiornare il metodo `Main` per visualizzare gli elementi seguenti:

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

Come passaggio conclusivo si aggiungeranno le informazioni necessarie per l'ultima operazione push, formattate nella risposta JSON come illustrato di seguito:

```json
2016-02-08T21:27:00Z
```

Tale formato è nell'ora UTC (Coordinated Universal Time), in modo da ottenere un <xref:System.DateTime> valore la cui <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc> . Se si preferisce una data rappresentata nel fuso orario, è necessario scrivere un metodo di conversione personalizzato. Definire innanzitutto una `public` proprietà che conterrà la rappresentazione UTC della data e dell'ora nella `Repository` classe e una `LastPush` `readonly` proprietà che restituisca la data convertita nell'ora locale:

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

Verranno ora esaminati i nuovi costrutti appena definiti. La `LastPush` proprietà viene definita utilizzando un *membro con corpo di espressione* per la `get` funzione di accesso. Non è presente alcuna funzione di accesso `set`. L'omissione della `set` funzione di accesso è la modalità di definizione di una proprietà di *sola lettura* in C#. È possibile creare anche proprietà di *sola scrittura* in C#, ma con un valore limitato.

Dopo aver aggiunto un'altra istruzione di output alla console, sarà possibile compilare ed eseguire nuovamente l'app:

```csharp
Console.WriteLine(repo.LastPush);
```

La versione dell'app dovrebbe ora corrispondere all'[esempio completo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).

## <a name="conclusion"></a>Conclusioni

In questa esercitazione sono state descritte le procedure necessarie per eseguire richieste Web, analizzare i risultati e visualizzare le proprietà dei risultati. Sono stati inoltre aggiunti nuovi pacchetti come dipendenze del progetto e sono state illustrate alcune delle funzionalità del linguaggio C# che supportano tecniche orientate agli oggetti.

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
