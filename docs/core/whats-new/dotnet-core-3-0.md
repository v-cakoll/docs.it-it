---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: baaa2676865c475e331ec889e7b10ae326b552fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675088"
---
# <a name="whats-new-in-net-core-30-preview-2"></a>Novità di .NET Core 3.0 (Preview 2)

Questo articolo descrive le novità di .NET Core 3.0 (Preview 2). Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows). Utilizzando un componente di .NET Core 3.0 SDK denominato Windows Desktop, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation). Il componente Windows Desktop è dunque supportato e incluso solo in Windows. Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) riportata di seguito.

.NET Core 3.0 aggiunge il supporto per C# 8.0.

[Scaricare e iniziare subito a usare .NET Core 3 Preview 2](https://aka.ms/netcore3download) in Windows, Mac e Linux. È possibile visualizzare i dettagli completi della versione nelle [note sulla versione di .NET Core 3 Preview 2](https://aka.ms/netcore3releasenotes).

Per altre informazioni sulle funzionalità incluse nella versione di anteprima 1, vedere l'[annuncio per .NET Core 3.0 Preview 1](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

Per altre informazioni sulle funzionalità incluse nella versione di anteprima 2, vedere l'[annuncio per .NET Core 3.0 Preview 2]().

## <a name="c-8"></a>C# 8

.NET Core 3.0 supporta C# 8 e a partire da .NET Core 3.0 Preview 2 supporta queste nuove funzionalità. Per altre informazioni sulle funzionalità di C# 8.0, vedere i post di blog seguenti:

- [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/) (Nuove potenzialità con i modelli in C# 8.0)
- [Take C# 8.0 for a spin](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/) (Un giro di C# 8.0)
- [Building C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) (Sviluppo con C# 8.0)


### <a name="ranges-and-indices"></a>Gli intervalli e indici

Il nuovo tipo `Index` può essere usato per l'indicizzazione. È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Esiste anche un tipo `Range`, costituito da due valori `Index`, uno per l'inizio e uno per la fine, che può essere scritto con un'espressione intervallo `x..y` (C#). È quindi possibile eseguire l'indicizzazione con `Range` per generare una sezione:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a>Flussi asincroni

Il tipo `IAsyncEnumerable<T>` è una nuova versione asincrona di `IEnumerable<T>`. Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.

L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni. L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti. Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`. Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.

>[!NOTE]
>È necessario .NET Core 3.0 Preview 2 per usare flussi asincroni se si vuole sviluppare con Visual Studio 2019 Preview 2 o l'anteprima più recente dell'[estensione C# per Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5). Se si usa .NET Core 3.0 Preview 2 dalla riga di comando, tutto funzionerà come previsto.

### <a name="using-declarations"></a>Dichiarazioni using

Le *dichiarazioni using* sono un nuovo modo per assicurarsi che l'oggetto venga eliminato correttamente. Una *dichiarazione using* mantiene attivo l'oggetto mentre è ancora nell'ambito. Quando l'oggetto diventa esterno all'ambito, viene eliminato automaticamente. In questo modo si riducono le *istruzioni using* annidate e il codice diventa più chiaro.

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a>Espressioni switch

Le *espressioni switch* sono un modo più pulito per eseguire un'*istruzione switch* ma, trattandosi di un'espressione, restituisce un valore. Le *espressioni switch* sono anche completamente integrate con i criteri di ricerca e usano il criterio di rimozione `_` per rappresentare il valore `default`.

È possibile visualizzare la sintassi per le *espressioni switch* nell'esempio seguente:

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

In questo esempio entrano in gioco due criteri. `o` corrisponde prima di tutto al *criterio di tipo* `Point` e poi al *criterio di proprietà* all'interno delle *{parentesi graffe}*. `_` descrive `discard pattern`, uguale a `default` per le *istruzioni switch*.

I criteri consentono di scrivere codice dichiarativo che definisce la finalità anziché codice procedurale che implementa i test. Il compilatore diventa responsabile dell'implementazione di tale codice procedurale noioso e viene garantito che l'operazione sia sempre eseguita in modo corretto.

Esistono comunque casi in cui le *istruzioni switch* saranno preferibili rispetto alle *espressioni switch* e i criteri possono essere usati con entrambi gli stili di sintassi.

Per altre informazioni, vedere [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/) (Nuove potenzialità con i modelli in C# 8.0).

## <a name="ieee-floating-point-improvements"></a>Miglioramenti per le API a virgola mobile IEEE

Le API a virgola mobile sono in corso di aggiornamento per soddisfare i requisiti della [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision). L'obiettivo di queste modifiche è esporre tutte le operazioni "obbligatorie" e assicurarsi che siano compatibili a livello di comportamento con la specifica IEEE.

Correzioni per analisi e formattazione:

* Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.
* Analisi corretta e formattazione dello zero negativo.
* Analisi corretta di valori Infinity e NaN con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.

Le nuove API per operazioni matematiche:

* `BitIncrement/BitDecrement`\
Corrispondono alle operazioni IEEE `nextUp` e `nextDown`. Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente). Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.

* `MaxMagnitude/MinMagnitude`\
Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente). Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.

* `ILogB`\
Corrispondono all'operazione IEEE `logB` che restituisce il logaritmo in base 2 integrale del parametro di input. Equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.

* `ScaleB`\
Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.

* `Log2`\
Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2. Gli errori di arrotondamento sono ridotti al minimo.

* `FusedMultiplyAdd`\
Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add). Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento. Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)` che restituisce `1e308`. L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.

* `CopySign`\
Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.

## <a name="net-platform-dependent-intrinsics"></a>Intrinseci dipendenti dalla piattaforma .NET

Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**. Queste istruzioni consentono di ottenere miglioramenti delle prestazioni notevoli in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo. Oltre a esporre le API per i programmi, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.

Le richieste pull CoreCLR seguenti illustrano alcuni degli intrinseci, tramite implementazione o uso:

* [Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585) (Implementare intrinseci hardware SSE2 semplici)
* [Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538) (Implementare gli intrinseci hardware SSE)
* [Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822) (Intrinseci hardware base Arm64)
* [Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073) (Usare TZCNT e LZCNT per Locate{First|Last}Found{Byte|Char})

Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET), che definisce un approccio per la definizione di questa infrastruttura hardware, che consente a Microsoft, fornitori di chip o altre società o singoli di definire API per hardware/chip che devono essere esposte al codice .NET.

## <a name="default-executables"></a>File eseguibili predefiniti

Per impostazione predefinita .NET Core compilerà ora i [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde). Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale. Finora solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) producevano un file eseguibile.

Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile purché corrisponda all'ambiente e alla piattaforma dell'SDK usato. Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:

* È possibile fare doppio clic sul file eseguibile.
* È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.

## <a name="build-copies-dependencies"></a>Copia delle dipendenze tramite la compilazione

`dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet alla cartella di output per la compilazione. In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`. 

Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.


## <a name="local-dotnet-tools"></a>Strumenti dotnet locali

>[!WARNING]
>È stata introdotta una modifica per gli strumenti .NET Core locali tra .NET Core 3.0 Preview 1 e .NET Core 3.0 Preview 2.  Se sono stati provati gli strumenti locali nella versione Preview 1 eseguendo un comando come `dotnet tool restore` o `dotnet tool install`, è necessario eliminare la cartella della cache degli strumenti locali prima che gli strumenti locali funzionino correttamente nella versione Preview 2. Questa cartella si trova in:
>
>In Mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
>In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`
>
>Se non si elimina questa cartella, si riceverà un errore.

Mentre .NET Core 2.1 supportava strumenti globali, .NET Core 3.0 ha ora strumenti locali. Gli strumenti locali sono simili agli strumenti globali, ma sono associati a una determinata posizione sul disco. Ciò consente di usare strumenti specifici per ogni progetto e ogni repository. Gli strumenti installati in locale non sono disponibili a livello globale. Gli strumenti vengono distribuiti come pacchetti NuGet.

Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente. Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle. Creando questo file manifesto nella radice del repository, si ha la certezza che chiunque cloni il codice non possa ripristinare e usare gli strumenti necessari per lavorare in modo corretto con il codice.

Per creare un file manifesto `dotnet-tools.json`, usare:

```console
dotnet new tool-manifest
```

Aggiungere un nuovo strumento al manifesto locale con:

```console
dotnet tool install <packageId>
```

È anche possibile elencare gli strumenti nel manifesto locale con:

```console
dotnet tool list
```

Per vedere quali strumenti vengono installati a livello globale, usare:

```console
dotnet tool list -g
```

Quando il file manifesto degli strumenti locali è disponibile, ma gli strumenti definiti nel manifesto non sono stati installati, usare il comando seguente per scaricare e installare automaticamente tali strumenti in locale:

```console
dotnet tool restore
```

Eseguire uno strumento locale con il comando seguente:

```console
dotnet tool run <tool-command-name>
```

Quando viene eseguito uno strumento locale, dotnet cerca un manifesto nella struttura di directory corrente. Quando viene trovato un file manifesto degli strumenti, viene eseguita la ricerca dello strumento richiesto. Se lo strumento viene trovato nel manifesto, ma non la cache, l'utente riceve un errore e deve eseguire `dotnet tool restore`.

Per rimuovere uno strumento dal file manifesto dello strumento locale, eseguire il comando seguente:

```console
dotnet tool uninstall <packageId>
```

Il file manifesto dello strumento è progettato per consentire la modifica manuale, ad esempio per aggiornare la versione necessaria per usare il repository. Ecco un file `dotnet-tools.json` di esempio:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime. Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1. Per installarli a livello globale o locale, è ancora necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

## <a name="windows-desktop"></a>Desktop di Windows

A partire da .NET Core 3.0 Preview 1, è possibile compilare applicazioni desktop di Windows con WPF e Windows Form. Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).

Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.

È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:

```console
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 Preview 2 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF. Le finestre di progettazione non sono ancora supportate. È possibile aprire, avviare ed eseguire il debug di questi progetti in Visual Studio 2019.

Visual Studio 2017 15.9 aggiunge la possibilità di [abilitare le anteprime di .NET Core](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/), ma è necessario attivare questa funzionalità e non è uno scenario supportato.

I nuovi progetti sono uguali ai progetti .NET Core esistenti, con alcune aggiunte. Di seguito è riportato il confronto tra il progetto console .NET Core di base e un progetto Windows Form e WPF di base.

In un progetto console .NET Core il progetto usa l'SDK `Microsoft.NET.Sdk` e dichiara una dipendenza da .NET Core 3.0 tramite il framework di destinazione `netcoreapp3.0`. Per creare un'app desktop di Windows, usare l'SDK `Microsoft.NET.Sdk.WindowsDesktop` e scegliere quale framework interfaccia utente usare:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Per scegliere Windows Form invece di WPF, impostare `UseWindowsForms` invece che `UseWPF`:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

Sia `UseWPF` che `UseWindowsForms` possono essere impostati su `true` se l'app usa entrambi i framework, ad esempio quando una finestra di dialogo di Windows Form ospita un controllo WPF.

Condividere commenti e suggerimenti nei repository [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) e [dotnet/core](https://github.com/dotnet/core/issues).

## <a name="msix-deployment-for-windows-desktop"></a>Distribuzione MSIX per Windows Desktop

[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di app Windows. Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.

Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019 Preview 2, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/#self-contained-deployments-scd).

>Nota: Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a>Supporto JSON predefinito rapido

L'ecosistema .NET si è basato su [**Json.NET**](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide. Come tipo di dati di base **Json.NET** usa le stringhe .NET, che in realtà sono UTF-16.

Il nuovo supporto JSON predefinito offre prestazioni elevate, bassa allocazione ed è basato su `Span<byte>`. Sono stati aggiunti tre nuovi tipi correlati principali JSON a .NET Core 3.0 nello spazio dei nomi `System.Text.Json`.

### <a name="utf8jsonreader"></a>Utf8JsonReader

`System.Text.Json.Utf8JsonReader` è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`. `Utf8JsonReader` è un tipo di base di basso livello, che può essere sfruttato per compilare parser e deserializzatori personalizzati. La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di **Json.NET**. Non viene allocato fino a quando non è necessario realizzare i token JSON come stringhe (UTF-16).

Questa nuova API includerà i componenti seguenti:

* Nell'anteprima 1: lettore JSON (accesso sequenziale)
* Presto disponibili: writer JSON, DOM (accesso casuale), serializzatore poco, deserializzatore poco

Ecco il ciclo del lettore di base per `Utf8JsonReader` che può essere usato come punto iniziale:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a>Utf8JsonWriter

`System.Text.Json.Utf8JsonWriter` rende disponibile un metodo ad alte prestazioni, senza memorizzazione nella cache e forward-only per la scrittura di test JSON con codifica UTF-8 da tipi .NET comuni, come `String`, `Int32` e `DateTime`. Come il lettore, il writer è un tipo di base di basso livello, che può essere sfruttato per creare serializzatori personalizzati. La scrittura di un payload JSON con il nuovo `Utf8JsonWriter` offre velocità maggiori del 30-80% rispetto all'uso del writer da **Json.NET** e non prevede allocazione.

Ecco un esempio di utilizzo di `Utf8JsonWriter` che può essere usato come punto di partenza:

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

`Utf8JsonWriter` accetta `IBufferWriter<byte>` come posizione di output per la scrittura sincrona dei dati JSON ed è il chiamante a dover fornire un'implementazione concreta. Attualmente la piattaforma non include un'implementazione di questa interfaccia. Per un esempio di `IBufferWriter<byte>`, vedere [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)

### <a name="jsondocument"></a>JsonDocument

`System.Text.Json.JsonDocument` è basato su `Utf8JsonReader`. `JsonDocument` offre la possibilità di analizzare i dati JSON e compilare un modello DOM (Document Object Model) di sola lettura su cui è possibile eseguire query per supportare l'accesso casuale e l'enumerazione. Gli elementi JSON che compongono i dati sono accessibili tramite il tipo `JsonElement` che viene esposto da `JsonDocument` come una proprietà denominata `RootElement`. `JsonElement` contiene gli enumeratori di matrice e oggetto JSON insieme alle API per convertire il testo JSON in tipi .NET comuni. L'analisi di un payload JSON tipico e l'accesso a tutti i relativi membri tramite `JsonDocument` è 2-3 volte più veloce rispetto a **Json.NET** con allocazioni minime per dati di dimensioni ragionevoli, ovvero inferiori a 1 MB.

Ecco un esempio di utilizzo di `JsonDocument` e `JsonElement` che può essere usato come punto di partenza:

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a>Assembly non caricabili

Gli assembly non caricabili sono una nuova funzionalità di `AssemblyLoadContext`. Questa nuova funzionalità è in gran parte trasparente dal punto di vista di un'API ed è esposta solo con poche nuove API. Consente di scaricare il contesto di un caricatore, rilasciando tutta la memoria per tipi istanziati, i campi statici e per l'assembly stesso. Un'applicazione deve essere in grado di caricare e scaricare gli assembly tramite questo meccanismo a tempo indefinito senza riscontrare una perdita di memoria.

Questa nuova funzionalità può essere usata per scenari simili ai seguenti:

* Scenari con plug-in in cui sono richiesti il caricamento e lo scaricamento dinamico del plug-in. 
* Compilazione, esecuzione e scaricamento dinamici del codice. Utile per siti Web, motori di scripting e così via.
* Il caricamento degli assembly per introspezione (ad esempio ReflectionOnlyLoad), nonostante [MetadataLoadContext](#type-metadataloadcontext) (rilasciato nella versione Preview 1) sia una scelta migliore in molti casi.

Per altre informazioni, vedere il documento [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) (Usare la funzionalità che impedisce lo scaricamento).

Lo scaricamento degli assembly richiede notevole attenzione per assicurare che tutti i riferimenti agli oggetti gestiti dall'esterno del contesto di un caricatore vengano riconosciuti e gestiti. Quando è richiesto lo scaricamento del contesto del caricatore, occorre rimuovere tutti gli eventuali riferimenti esterni in modo che il contesto del caricatore sia intrinsecamente coerente solo con se stesso.

La funzionalità per impedire lo scaricamento degli assembly era inclusa in .NET Framework tramite i domini dell'applicazione (AppDomain), non supportati in .NET Core. AppDomain presenta sia vantaggi che limiti rispetto a questo nuovo modello. Prendere in considerazione questo nuovo modello di caricatore per ottenere maggiore flessibilità e prestazioni più elevate rispetto ad AppDomain.

## <a name="windows-native-interop"></a>Interoperabilità nativa di Windows

Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT. **P/Invoke** è supportato a partire da .NET Core 1.0. Con .NET Core 3.0 è stato ora aggiunto il supporto della possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.

È possibile vedere un esempio dell'uso di COM con il [codice sorgente per la demo con Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).


## <a name="type-sequencereader"></a>Tipo: SequenceReader

In .NET Core 3.0 è stato aggiunto `System.Buffers.SequenceReader` che può essere usato come lettore per `ReadOnlySequence<T>`. Ciò consente un'analisi semplice, a prestazioni elevate e allocazione ridotta dei dati di `System.IO.Pipelines` che possono attraversare più buffer sottostanti. 

L'esempio seguente suddivide un elemento `Sequence` di input in righe delimitate da `CR/LF` valide:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Tipo: MetadataLoadContext

È stato aggiunto il tipo `MetadataLoadContext` che consente la lettura dei metadati dell'assembly senza impatto sul dominio dell'applicazione del chiamante. Gli assembly vengono letti come dati, inclusi gli assembly compilati per architetture e piattaforme diverse da quelle dell'ambiente di runtime corrente. `MetadataLoadContext` si sovrappone a <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, che è disponibile solo in .NET Framework.

`MetdataLoadContext` è disponibile nel pacchetto [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Si tratta di un pacchetto .NET Standard 2.0.

`MetadataLoadContext` espone API simili al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, ma non si basa su tale tipo. In modo analogo a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` consente il caricamento degli assembly all'interno di un universo di caricamento di assembly isolato. Le API `MetdataLoadContext` restituiscono oggetti <xref:System.Reflection.Assembly>, consentendo l'uso di API di reflection familiari. Le API orientate all'esecuzione, ad esempio [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), non sono consentite e genereranno l'eccezione InvalidOperationException.

L'esempio seguente illustra come trovare tipi concreti in un assembly che implementa una determinata interfaccia:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Gli scenari per `MetadataLoadContext` includono funzionalità della fase di progettazione, strumenti della fase di compilazione e funzionalità esclusive di runtime che devono esaminare un set di assembly come dati e i cui blocchi di file e la cui memoria vengono liberati dopo l'esecuzione dell'ispezione.

`MetadataLoadContext` ha una classe resolver passata al costruttore. Il processo del resolver consiste nel caricare un `Assembly`, dato il relativo `AssemblyName`. La classe resolver deriva dalla classe astratta `MetadataAssemblyResolver`. Con `PathAssemblyResolver` viene fornita un'implementazione del resolver per gli scenari basati sul percorso.

I [test di MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) illustrano numerosi casi d'uso. I [test di Assembly](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sono un buon punto di partenza.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 e OpenSSL 1.1.1 in Linux

.NET Core sfrutterà ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente. I vantaggi di TLS 1.3 sono diversi, secondo il [team di OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):

* Durata della connessione migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.

* Maggiore sicurezza grazie alla rimozione di algoritmi di crittografia obsoleti e non sicuri e alla crittografia di più elementi dell'handshake della connessione.

.NET Core 3.0 Preview 1 può utilizzare **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (a seconda della versione migliore trovata, in un sistema Linux).  Quando **OpenSSL 1.1.1** è disponibile, i tipi SslStream e HttpClient useranno **TLS 1.3** quando si usa `SslProtocols.None` (protocolli predefiniti di sistema), presupponendo che sia il client che il server supportino **TLS 1.3**.

L'esempio seguente illustra .NET Core 3.0 Preview 1 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows e macOS non supportano ancora **TLS 1.3**. .NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.

## <a name="cryptography"></a>Crittografia

È stato aggiunto il supporto per le modalità di crittografia **AES-GCM** e **AES-CCM**, implementate tramite `System.Security.Cryptography.AesGcm` e `System.Security.Cryptography.AesCcm`. Questi algoritmi sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption) nonché i primi algoritmi di cifratura autenticata aggiunti a .NET Core.

Il codice seguente illustra l'uso della modalità di crittografia **AesGcm** per crittografare e decrittografare dati casuali.

Il codice per **AesCcm** sarà pressoché identico, con la sola differenza dei nomi di variabile di classe.

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Importazione/Esportazione di chiavi crittografiche

.NET core 3.0 Preview 1 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche dai formati standard, senza bisogno usare un certificato X.509.

Tutti i tipi di chiavi (RSA, DSA, ECDsa, ECDiffieHellman) supportano il formato **X.509 SubjectPublicKeyInfo** per le chiavi pubbliche e i formati **PKCS#8 PrivateKeyInfo** e **PKCS#8 EncryptedPrivateKeyInfo** per le chiavi private. RSA supporta anche **PKCS#1 RSAPublicKey** e **PKCS#1 RSAPrivateKey**. Tutti i metodi di esportazione producono dati binari con codifica DER e i metodi di importazione presentano lo stesso comportamento. Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

I file PKCS#8 possono essere esaminati con la classe `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.

I file PFX/PKCS#12 possono essere esaminati e modificati rispettivamente con `System.Security.Cryptography.Pkcs.Pkcs12Info` e `System.Security.Cryptography.Pkcs.Pkcs12Builder`.

## <a name="serialport-for-linux"></a>SerialPort per Linux

.NET Core 3.0 supporta ora <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.

In precedenza, .NET Core supportava solo l'uso del tipo `SerialPort` in Windows.

## <a name="more-bcl-improvements"></a>Altri miglioramenti BCL

`Span<T>`, `Memory<T>` e i tipi correlati introdotti in .NET Core 2.1 sono stati ottimizzati in .NET Core 3.0. Le operazioni comuni, ad esempio la costruzione di intervalli, il sezionamento, l'analisi e la formattazione offrono ora prestazioni migliori. 

Inoltre, i tipi come `String` sono stati sottoposti a miglioramenti per aumentarne l'efficienza quando sono usati come chiavi con `Dictionary<TKey, TValue>` e altre raccolte. Per trarre vantaggio da questi miglioramenti, non sono necessarie modifiche al codice.

.NET Core 3 Preview 1 presenta anche i nuovi miglioramenti seguenti:

* Supporto di Brotli predefinito in HttpClient
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* Operatori aritmetici complessi
* API socket per il keep-alive TCP
* StringBuilder.GetChunks
* Analisi IPEndPoint
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>Compilazione a livelli

Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) è attiva. È una funzionalità che consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori, sia all'avvio che per ottimizzare la velocità effettiva.

Questa funzionalità è stata aggiunta come funzionalità con consenso esplicito in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) ed è stata abilitata per impostazione predefinita in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/). Successivamente, è stata ripristinata come funzionalità con consenso esplicito nella versione .NET Core 2.2.

## <a name="arm64-linux-support"></a>Supporto ARM64 per Linux

È stato aggiunto il supporto per ARM64 per Linux. Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.

[Sono disponibili immagini Docker per .NET Core per ARM64](https://hub.docker.com/r/microsoft/dotnet/) di Alpine, Debian e Ubuntu.

Per altre informazioni., vedere [Stato di ARM64 per .NET Core](https://github.com/dotnet/announcements/issues/82).

>[!NOTE]
> Il supporto **ARM64** per Windows non è ancora disponibile.

## <a name="install-net-core-30-previews-on-linux-with-snap"></a>Installare le versioni di anteprima di .NET Core 3.0 in Linux con Snap

Snap è il modo preferenziale per installare e provare le anteprime di .NET Core nelle [distribuzioni di Linux che supportano Snap](https://docs.snapcraft.io/installing-snapd/6735).

Dopo aver configurato Snap nel sistema, eseguire il comando seguente per installare [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).

```console
sudo snap install dotnet-sdk --beta --classic
```
 
Se .NET Core viene installato usando il pacchetto Snap, il comando di .NET Core predefinito è `dotnet-sdk.dotnet`, anziché semplicemente `dotnet`. Il vantaggio del comando con spazio dei nomi è che non si verificheranno conflitti con una versione di .NET Core installata a livello globale eventualmente disponibile. È possibile definire l'alias `dotnet` per questo comando con:

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

Alcune distribuzioni richiedono un altro passaggio per abilitare l'accesso al certificato SSL. Vedere la [documentazione sulla configurazione di Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) per altri dettagli.

## <a name="gpio-support-for-raspberry-pi"></a>Supporto di GPIO per Raspberry Pi

Sono stati rilasciati due nuovi pacchetti NuGet che è possibile usare per la programmazione GPIO.

* [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

I pacchetti GPIO includono le API per i dispositivi GPIO, SPI, I2C e PWM. Il pacchetto di associazioni IoT include [associazioni di dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/README.md) per i vari chip e sensori, gli stessi disponibili in[dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).

Le API per le porte seriali aggiornate, annunciate per .NET Core 3.0 Preview 1, non fanno parte di questi pacchetti ma sono disponibili come parte della piattaforma .NET Core.


## <a name="platform-support"></a>Supporto per piattaforme

.NET Core 3 sarà supportato nei sistemi operativi seguenti:

* Client Windows: 7, 8.1, 10 (1607+)
* Windows Server: 20012 R2 SP1+
* macOS: 10.12+
* RHEL: 6+
* Fedora: 26+
* Ubuntu: 16.04+
* Debian: 9+
* SLES: 12+
* openSUSE: 42.3+
* Alpine: 3.8+

Il supporto dei chip è il seguente:

* x64 in Windows, macOS e Linux
* x86 in Windows
* ARM32 in Windows e Linux
* ARM64 in Linux

Per Linux, ARM32 è supportato in Debian 9+ e Ubuntu 16.04+. Per ARM64, è uguale a ARM32 con l'aggiunta di Alpine 3.8. Queste sono le stesse versioni di tali distribuzioni supportate per x64.

Le immagini Docker per .NET Core 3.0 sono disponibili in [microsoft/dotnet nell'Hub Docker](https://hub.docker.com/r/microsoft/dotnet/). È in corso il processo di adozione di [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) ed è previsto che le immagini finali di .NET Core 3.0 vengano pubblicate solo in MCR.
