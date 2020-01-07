---
title: Aggiornare i tipi di riferimento Nullable
description: Questa esercitazione avanzata illustra come eseguire la migrazione di codice esistente con tipi di riferimento Nullable.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 75bc8d278efb66363212e3e000154ffc70f373bf
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634911"
---
# <a name="tutorial-migrate-existing-code-with-nullable-reference-types"></a>Esercitazione: eseguire la migrazione di codice esistente con tipi di riferimento Nullable

In C# 8 sono ora disponibili i **tipi riferimento nullable**, che completano i tipi riferimento allo stesso modo in cui i tipi valore nullable completano i tipi valore. Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo. Ad esempio, `string?` rappresenta un tipo `string` nullable. È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*. Tutte le variabili esistenti di un tipo riferimento verrebbero interpretate come un tipo riferimento non nullable. 

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> - Abilitare i controlli dei riferimenti Null mentre si lavora con il codice.
> - Diagnosticare e correggere i diversi avvisi correlati ai valori Null.
> - Gestire l'interfaccia tra contesti abilitati per nullable e contesti disabilitati per nullable.
> - Controllare i contesti delle annotazioni nullable.

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il C# compilatore 8,0. Il C# compilatore 8 è disponibile a partire da [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o [.NET Core 3,0 SDK](https://dotnet.microsoft.com/download).

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="explore-the-sample-application"></a>Esplorare l'applicazione di esempio

L'applicazione di esempio di cui verrà eseguita la migrazione è un'app Web lettore di feed RSS. L'app consente di leggere da un singolo feed RSS e visualizzare riassunti per gli articoli più recenti. È possibile selezionare uno degli articoli per visitare il sito. L'applicazione è relativamente nuova, ma è stata scritta prima che diventassero disponibili i tipi riferimento nullable. Pur essendo rappresentative di solidi principi, le decisioni di progettazione non sfruttano questa importante funzionalità del linguaggio.

L'applicazione di esempio include una libreria di unit test che convalida le funzionalità principali dell'app. Tale progetto renderà più facile eseguire l'aggiornamento in modo sicuro, se si modifica qualsiasi implementazione in base agli avvisi generati. È possibile scaricare il codice iniziale dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/start).

L'obiettivo di migrazione del progetto dovrebbe essere di sfruttare le nuove funzionalità del linguaggio in modo da esprimere chiaramente le finalità per il supporto dei valori Null delle variabili e farlo in modo tale che il compilatore non generi avvisi quando il contesto delle annotazioni nullable e il contesto degli avvisi nullable è impostato su `enabled`.

## <a name="upgrade-the-projects-to-c-8"></a>Aggiornare i progetti a C# 8

Un buon primo passo è determinare l'ambito dell'attività di migrazione. Per iniziare, aggiornare il progetto a C# 8.0 (o versione successiva). Aggiungere l'elemento `LangVersion` sia ai file csproj per il progetto Web che al progetto di unit test:

```xml
<LangVersion>8.0</LangVersion>
```

L'aggiornamento della versione del linguaggio seleziona C# 8.0, ma non abilita il contesto delle annotazioni nullable e il contesto degli avvisi nullable. Ricompilare il progetto per assicurarsi che venga compilato senza avvisi.

Un buon passo successivo è attivare il contesto delle annotazioni nullable e vedere quanti avvisi vengono generati. Aggiungere l'elemento seguente sia ai file csproj nella soluzione, che direttamente nell'elemento `LangVersion`:

```xml
<Nullable>enable</Nullable>
```

Eseguire una compilazione di prova ed esaminare l'elenco degli avvisi. In questa piccola applicazione, il compilatore genera cinque avvisi, dunque è probabile che in un caso come questo si lasci abilitato il contesto delle annotazioni nullable e si inizi a risolvere gli avvisi per l'intero progetto.

Questa strategia funziona solo per i progetti più piccoli. Per qualsiasi progetto di dimensioni più grandi, il numero di avvisi generati abilitando il contesto delle annotazioni nullable per l'intera base di codice rende più difficile risolvere gli avvisi in modo sistematico. Per progetti aziendali più grandi, è spesso opportuno eseguire la migrazione di un progetto alla volta. In ogni progetto, eseguire la migrazione di una classe o un file alla volta.

## <a name="warnings-help-discover-original-design-intent"></a>Gli avvisi sono utili per individuare le finalità di progettazione originali

Esistono due classi che generano più avvisi. Prima di tutto la classe `NewsStoryViewModel`. Rimuovere l'elemento `Nullable` da entrambi i file csproj in modo da poter limitare l'ambito degli avvisi alle sezioni del codice su cui si sta lavorando. Aprire il file *NewsStoryViewModel.cs* e aggiungere le direttive seguenti per abilitare il contesto delle annotazioni nullable per `NewsStoryViewModel` e ripristinarlo seguendo tale definizione di classe:

```csharp
#nullable enable
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; }
    public string Uri { get; set; }
}
#nullable restore
```

Queste due direttive consentono di focalizzare le operazioni di migrazione. Gli avvisi nullable vengono generati per l'area del codice su cui si sta lavorando attivamente. Verranno lasciati attivi fino a quando non si è pronti per attivare gli avvisi per l'intero progetto. È consigliabile usare il valore `restore` invece di `disable`, in modo da evitare di disabilitare inavvertitamente il contesto in un secondo momento quando si attivano le annotazioni nullable per l'intero progetto. Dopo avere attivato il contesto delle annotazioni nullable per l'intero progetto, è possibile rimuovere tutti i pragma `#nullable` da tale progetto.

La classe `NewsStoryViewModel` è un oggetto di trasferimento dei dati (DTO) e due delle proprietà sono stringhe di lettura/scrittura:

[!code-csharp[InitialViewModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#StarterViewModel)]

Queste due proprietà causano l'avviso `CS8618` "Non-nullable property is uninitialized" (Proprietà non nullable non inizializzata). Il messaggio è chiaro: entrambe le proprietà `string` hanno il valore predefinito `null` quando viene costruito un `NewsStoryViewModel`. Quello che è importante scoprire è come vengono costruiti gli oggetti `NewsStoryViewModel`. Esaminando questa classe non è possibile stabilire se il valore `null` fa parte della progettazione o se questi oggetti sono impostati su valori non Null ogni volta che ne viene creato uno. Le storie delle notizie vengono create nel metodo `GetNews` della classe `NewsService`:

[!code-csharp[StarterCreateNewsItem](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#CreateNewsItem)]

Sono tanti gli aspetti interessanti nel blocco di codice precedente. Questa applicazione usa il pacchetto NuGet [AutoMapper](https://automapper.org/) per costruire un elemento di notizie da un `ISyndicationItem`. Si è scoperto che gli elementi della storia delle notizie vengono costruiti e le proprietà vengono impostate in tale singola istruzione. Questo significa che la progettazione per `NewsStoryViewModel` indica che queste proprietà non devono mai avere il valore `null`. Queste proprietà devono essere **tipi riferimento non nullable**. Questa è la migliore espressione della finalità di progettazione originale. In realtà, qualsiasi `NewsStoryViewModel` *viene* creata correttamente con i valori non null. Il codice di inizializzazione seguente rappresenta quindi una correzione valida:

```csharp
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; } = default!;
    public string Uri { get; set; } = default!;
}
```

L'assegnazione di `Title` e `Uri` a `default`, ovvero `null` per il tipo `string`, non cambia il comportamento di runtime del programma. `NewsStoryViewModel` viene ancora costruito con valori Null, ma ora il compilatore non segnala alcun avviso. L'**operatore per la tolleranza per i valori Null**, ovvero il carattere `!` dopo l'espressione `default`, indica al compilatore che l'espressione precedente non è Null. Questa tecnica può essere utile quando altre modifiche forzano modifiche molto più grandi in una codebase, ma in questa applicazione esiste una soluzione relativamente rapida e migliore: rendere il `NewsStoryViewModel` un tipo non modificabile in cui tutte le proprietà vengono impostate nel costruttore. Modificare `NewsStoryViewModel` nel modo seguente:

[!code-csharp[FinishedViewModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#FinishedViewModel)]

Al termine, è necessario aggiornare il codice che configura AutoMapper in modo che usi il costruttore anziché impostare proprietà. Aprire `NewsService.cs` e cercare il codice seguente nella parte inferiore del file:

[!code-csharp[StarterAutoMapper](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Tale codice esegue il mapping delle proprietà dell'oggetto `ISyndicationItem` con le proprietà `NewsStoryViewModel`. Si vuole invece che AutoMapper fornisca il mapping usando un costruttore. Sostituire il codice precedente con la configurazione di AutoMapper seguente:

[!code-csharp[FinishedViewModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Si noti che poiché questa classe è piccola e il codice è stato esaminato con attenzione, è necessario attivare la direttiva `#nullable enable` sopra questa dichiarazione di classe. La modifica al costruttore potrebbe aver introdotto errori, quindi è opportuno eseguire tutti i test e verificare l'applicazione prima di procedere.

Il primo set di modifiche ha illustrato come scoprire quando il progetto originale indica che le variabili non devono essere impostate su `null`. Questa tecnica è nota come **corretta per costruzione**. Si dichiara che un oggetto e le relative proprietà non possono essere `null` quando vengono costruiti. L'analisi di flusso del compilatore garantisce che tali proprietà non vengano impostate su `null` dopo la costruzione. Si noti che questo costruttore viene chiamato da codice esterno e che tale codice è **incurante dei valori Null**. La nuova sintassi non prevede controlli di runtime. Il codice esterno potrebbe aggirare l'analisi di flusso del compilatore. 

In altri casi, la struttura di una classe offre diverse indicazioni della finalità. Aprire il file *Error.cshtml.cs* nella cartella *Pages*. `ErrorViewModel` contiene il codice seguente:

[!code-csharp[StarterErrorModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Error.cshtml.cs#StartErrorModel)]

Aggiungere la direttiva `#nullable enable` prima della dichiarazione di classe e una direttiva `#nullable restore` dopo la dichiarazione. Si riceverà un avviso che `RequestId` non è inizializzato. Osservando la classe, è necessario decidere che la proprietà `RequestId` deve essere Null in alcuni casi. L'esistenza della proprietà `ShowRequestId` indica che sono possibili valori mancanti. Dato che `null` è valido, aggiungere `?` al tipo `string` per indicare che la proprietà `RequestId` è un *tipo riferimento nullable*. La classe finale è simile all'esempio seguente:

[!code-csharp[FinishedErrorModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Error.cshtml.cs#ErrorModel)]

Controllando gli usi della proprietà si noterà che nella pagina associata è previsto il controllo del valore Null per la proprietà prima di eseguirne il rendering nel markup. Questo è un uso sicuro di un tipo riferimento nullable, quindi è tutto per questa classe.

## <a name="fixing-nulls-causes-change"></a>La correzione dei valori Null causa modifiche

Spesso, la correzione per un set di avvisi crea nuovi avvisi nel codice correlato. È possibile visualizzare gli avvisi in azione correggendo la classe `index.cshtml.cs`. Aprire il file `index.cshtml.cs` ed esaminare il codice. Questo file contiene il code-behind per la pagina di indice:

[!code-csharp[StarterIndexModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Index.cshtml.cs#IndexModelStart)]

Aggiungere la direttiva `#nullable enable`. Verranno visualizzati due avvisi. Entrambe le proprietà `ErrorText` e `NewsItems` sono inizializzate. Un esame di questa classe porterebbe a credere che entrambe le proprietà devono essere tipi di riferimento Nullable: entrambi hanno Setter privati. Una sola viene assegnata nel metodo `OnGet`. Prima di apportare modifiche, esaminare i consumer di entrambe le proprietà. Nella pagina stessa, viene eseguito un controllo del valore Null per `ErrorText` prima della generazione del markup per eventuali errori. Viene eseguito un controllo di `null` per la raccolta `NewsItems`, che viene anche controllata per assicurarsi che contenga elementi. Una correzione rapida potrebbe consistere nell'impostare entrambe le proprietà come tipi riferimento nullable. Una correzione migliore sarebbe impostare la raccolta come tipo riferimento non nullable e aggiungere elementi alla raccolta esistente durante il recupero delle notizie. La prima correzione prevede l'aggiunta di `?` al tipo `string` per `ErrorText`:

[!code-csharp[UpdateErrorText](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#UpdateErrorText)]

Tale modifica non verrà propagata in altro codice, perché qualsiasi accesso alla proprietà `ErrorText` è già protetto dai controlli Null. Inizializzare quindi l'elenco `NewsItems` e rimuovere il setter della proprietà, rendendola una proprietà di sola lettura:

[!code-csharp[InitializeNewsItems](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#InitializeNewsItems)]

In questo modo è stato risolto l'avviso, ma è stato introdotto un errore. L'`NewsItems` elenco è ora **corretto per costruzione**, ma il codice che imposta l'elenco in `OnGet` deve essere modificato in modo che corrisponda alla nuova API. Invece di usare un'assegnazione, chiamare `AddRange` per aggiungere gli elementi delle notizie all'elenco esistente:

[!code-csharp[AddRange](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#AddRange)]

L'uso di `AddRange` al posto di un'assegnazione significa che il metodo `GetNews` può restituire `IEnumerable` invece di `List`. Si risparmia così un'allocazione. Modificare la firma del metodo e rimuovere la chiamata `ToList`, come illustrato nell'esempio di codice seguente:

[!code-csharp[GetNews](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#GetNewsFinished)]

Anche la modifica della firma causa errori per uno dei test. Aprire il file `NewsServiceTests.cs` nella cartella `Services` del progetto `SimpleFeedReader.Tests`. Passare al test `Returns_News_Stories_Given_Valid_Uri` e modificare il tipo della variabile `result` in `IEnumerable<NewsItem>`. La modifica del tipo significa che la proprietà `Count` non è più disponibile, quindi sostituire la proprietà `Count` in `Assert` con una chiamata a `Any()`:

[!code-csharp[FixTests](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader.Tests/Services/NewsServiceTests.cs#FixTestSignature)]

Sarà anche necessario aggiungere un'istruzione `using System.Linq` all'inizio del file.

Questo set di modifiche evidenzia quanto sia necessaria un'attenzione speciale quando si aggiorna codice che include creazioni di istanze generiche. Sia l'elenco che gli elementi nell'elenco di tipi non nullable. Uno o entrambi potrebbero essere tipi nullable. Tutte le dichiarazioni seguenti sono consentite:

- `List<NewsStoryViewModel>`: elenco non nullable di modelli di visualizzazione non nullable.
- `List<NewsStoryViewModel?>`: elenco non nullable di modelli di visualizzazione nullable.
- `List<NewsStoryViewModel>?`: elenco nullable di modelli di visualizzazione non nullable.
- `List<NewsStoryViewModel?>?`: elenco nullable di modelli di visualizzazione nullable.

## <a name="interfaces-with-external-code"></a>Interfacce con codice esterno

Sono state apportate modifiche alla classe `NewsService`, quindi attivare l'annotazione `#nullable enable` per tale classe. Non verranno generati nuovi avvisi. Tuttavia, un attento esame della classe è utile per illustrare alcune delle limitazioni dell'analisi di flusso del compilatore. Esaminare il costruttore:

[!code-csharp[ServiceConstructor](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ServiceConstructor)]

Il parametro `IMapper` è tipizzato come riferimento nullable. Viene chiamato dal codice dell'infrastruttura di ASP.NET Core, quindi il compilatore non sa che `IMapper` non sarà mai Null. Il contenitore di inserimento delle dipendenze di ASP.NET Core predefinito genera un'eccezione se non riesce a risolvere un servizio necessario, quindi il codice è corretto. Il compilatore non può convalidare tutte le chiamate alle API pubbliche, anche se il codice viene compilato con i contesti delle annotazioni nullable abilitati. Inoltre, le librerie potrebbero essere utilizzate da progetti per i quali non è ancora stato il consenso esplicito all'uso dei tipi riferimento nullable. Convalidare gli input per le API pubbliche, anche se sono stati dichiarati come tipi nullable.

## <a name="get-the-code"></a>Ottenere il codice

Gli avvisi identificati nella compilazione di prova iniziale sono stati corretti, quindi è ora possibile attivare il contesto delle annotazioni nullable per entrambi i progetti. Ricompilare i progetti. Il compilatore non segnala alcun avviso. È possibile ottenere il codice per il progetto completato nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/finished).

Le nuove funzionalità che supportano i tipi riferimento nullable consentono di trovare e correggere eventuali errori nel modo in cui si gestiscono i valori `null` nel codice. L'abilitazione del contesto delle annotazioni nullable consente di esprimere le finalità di progettazione: alcune variabili non devono mai essere Null e altre variabili possono contenere valori Null. Queste funzionalità rendono più semplice dichiarare le finalità della progettazione. Analogamente, il contesto degli avvisi nullable indica al compilatore di generare avvisi quando vengono violate le finalità. Questi avvisi sono utili per segnalare gli aggiornamenti che rendono il codice più resiliente e meno soggetto a generare eccezioni di tipo `NullReferenceException` durante l'esecuzione. È possibile controllare l'ambito di questi contesti in modo da potersi concentrare sulle aree locali del codice di cui eseguire la migrazione, mentre la base di codice rimanente rimane invariata. In pratica, è possibile eseguire questa attività di migrazione come parte delle normali attività di manutenzione delle classi. Questa esercitazione ha illustrato il processo per eseguire la migrazione di un'applicazione per l'uso dei tipi riferimento nullable. È possibile esplorare un esempio più esaustivo reale di questo processo, esaminando la richiesta pull effettuata da [Jon Skeet](https://github.com/jskeet) per incorporare i tipi riferimento nullable in [NodaTime](https://github.com/nodatime/nodatime/pull/1240/commits).
