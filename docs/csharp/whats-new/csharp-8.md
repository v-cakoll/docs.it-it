---
title: Novità di C# 8.0 - Guida a C#
description: Panoramica delle nuove funzionalità disponibili in C# 8.0. Questo articolo è aggiornato alla versione di anteprima 2.
ms.date: 02/12/2019
ms.openlocfilehash: d95ec3dc050f5633b4b069caa5bd2811f6b61300
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262582"
---
# <a name="whats-new-in-c-80"></a>Novità di C# 8.0

Sono disponibili numerosi miglioramenti per il linguaggio C# che è già possibile provare con l'anteprima 2. Le nuove funzionalità aggiunte nell'anteprima 2 sono:

- [Miglioramenti dei criteri di ricerca](#more-patterns-in-more-places):
  * [Espressioni switch](#switch-expressions)
  * [Criteri per le proprietà](#property-patterns)
  * [Criteri per le tuple](#tuple-patterns)
  * [Criteri per la posizione](#positional-patterns)
- [Dichiarazioni using](#using-declarations)
- [Funzioni locali statiche](#static-local-functions)
- [Struct ref Disposable](#disposable-ref-structs)

Le funzionalità del linguaggio seguenti sono state introdotte nell'anteprima 1 di C# 8.0:

- [Tipi riferimento nullable](#nullable-reference-types)
- [Flussi asincroni](#asynchronous-streams)
- [Indici e intervalli](#indices-and-ranges)

> [!NOTE]
> Questo articolo è stato aggiornato per l'ultima volta per l'anteprima 2 di C# 8.0.

Il resto di questo articolo descrive brevemente queste funzionalità. Se sono disponibili articoli approfonditi, vengono forniti collegamenti a queste panoramiche ed esercitazioni.

## <a name="more-patterns-in-more-places"></a>Più criteri in più posizioni

I **criteri di ricerca** offrono strumenti per fornire funzionalità dipendenti dalla forma su tipi di dati correlati ma diversi. In C# 7.0 è stata introdotta la sintassi per i criteri di tipi e i criteri di costanti, tramite l'espressione [`is`](../language-reference/keywords/is.md) e l'istruzione [`switch`](../language-reference/keywords/switch.md). Queste funzionalità rappresentano il primo passo per il supporto dei paradigmi di programmazione in cui i dati e la funzionalità sono separati. Man mano che il settore effettua la transizione verso più microservizi e altre architetture basate sul cloud, diventano necessari altri strumenti del linguaggio.

C# 8.0 espande questo vocabolario, in modo da poter usare più espressioni di criteri in più posizioni nel codice. Prendere in considerazione queste funzionalità quando i dati e le funzionalità sono separati. Prendere in considerazione i criteri di ricerca quando gli algoritmi dipendono da un fatto diverso dal tipo di runtime di un oggetto. Queste tecniche offrono un altro modo per esprimere le progettazioni.

Oltre ai nuovi criteri disponibili in nuove posizioni, C# 8.0 introduce i **criteri ricorsivi**. Il risultato di qualsiasi espressione di criteri è un'espressione. Un criterio ricorsivo è semplicemente un'espressione di criteri applicata all'output di un'altra espressione di criteri.

### <a name="switch-expressions"></a>Espressioni switch

Spesso, un'istruzione [`switch`](../language-reference/keywords/switch.md) produce un valore in ognuno dei relativi blocchi `case`. Le **espressioni switch** consentono di usare una sintassi più concisa per le espressioni con meno parole chiave `case` e `break` ripetitive e un numero inferiore di parentesi graffe.  Ad esempio, si consideri l'enumerazione seguente che elenca i colori dell'arcobaleno:

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

È possibile convertire un valore `Rainbow` nei relativi valori RGB usando il metodo seguente che contiene un'espressione switch:

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

Questo esempio include numerosi miglioramenti della sintassi:

- La variabile precede la parola chiave `switch`. L'ordine diverso rende più semplice distinguere visivamente l'espressione switch dall'istruzione switch.
- Gli elementi `case` e `:` vengono sostituiti con `=>`. È più conciso e intuitivo.
- Il caso `default` è sostituito con un discard `_`.
- I corpi sono espressioni e non istruzioni.

Confrontare questo codice con quello equivalente che usa l'istruzione `switch` classica:

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a>Criteri per le proprietà

I **criteri per le proprietà** consentono di individuare corrispondenze in base alle proprietà dell'oggetto esaminato. Si consideri un sito di e-commerce che deve calcolare le imposte sulle vendite in base all'indirizzo dell'acquirente. Questo calcolo non è una delle responsabilità principali di una classe `Address`. È soggetto a variazioni nel tempo, probabilmente più spesso rispetto a eventuali modifiche del formato dell'indirizzo. L'importo delle imposte sulle vendite dipende dalla proprietà `State` dell'indirizzo. Il metodo seguente usa i criteri per le proprietà per calcolare l'imposta sulle vendite dall'indirizzo e dal prezzo:

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

I criteri di ricerca creano una sintassi concisa per esprimere questo algoritmo.

### <a name="tuple-patterns"></a>Criteri per le tuple

Alcuni algoritmi dipendono da più input. I **criteri per le tuple** consentono di passare da un valore a un altro, espressi come [tupla](../tuples.md).  Il codice seguente illustra un'espressione switch per il gioco *rock, paper, scissors* (carta-forbice-sasso):

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

I messaggi indicano il vincitore. Il caso discard rappresenta le tre combinazioni di valori equivalenti o altri input di testo.

### <a name="positional-patterns"></a>Criteri per la posizione

Alcuni tipi includono un metodo `Deconstruct` che decostruisce le proprietà in variabili discrete. Quando un metodo `Deconstruct` è accessibile, è possibile usare i **criteri per la posizione** per esaminare le proprietà dell'oggetto e usare tali proprietà per un criterio.  Considerare la classe `Point` seguente che include un metodo `Deconstruct` per creare variabili discrete per `X` e `Y`:

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

Il metodo seguente usa i **criteri per la posizione** per estrarre i valori di `x` e `y`. Usa quindi una clausola `when` per determinare il quadrante del punto:

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

I criteri discard nell'espressione switch precedente individuano una corrispondenza quando `x` o `y` è 0, ma non entrambi. Un'espressione switch deve produrre un valore o generare un'eccezione. Se nessuno dei casi corrisponde, l'espressione switch genera un'eccezione. Il compilatore genera un avviso per l'utente se non è possibile includere tutti i casi possibili nell'espressione switch.

È possibile esplorare le tecniche dei criteri di ricerca in questa [esercitazione avanzata sui criteri di ricerca](../tutorials/pattern-matching.md).

## <a name="using-declarations"></a>Dichiarazioni using

Una **dichiarazione using** è una dichiarazione di variabile preceduta dalla parola chiave `using`. Indica al compilatore che la variabile dichiarata deve essere eliminata alla fine dell'ambito di inclusione. Ad esempio, si consideri il codice seguente che consente di scrivere un file di testo:

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura per il metodo. Questa è la fine dell'ambito in cui viene dichiarato `file`. Il codice precedente è equivalente al codice seguente con l'[istruzione using](../language-reference/keywords/using-statement.md) classica:


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura associata all'istruzione `using`.

In entrambi i casi, il compilatore genera la chiamata a `Dispose()`. Il compilatore genera un errore se l'espressione nell'istruzione using non è eliminabile.

## <a name="static-local-functions"></a>Funzioni locali statiche

È ora possibile aggiungere il modificatore `static` alle funzioni locali per assicurarsi che tale funzione locale non acquisisca (faccia riferimento a) variabili dall'ambito di inclusione. In questo modo viene generato l'errore `CS8421`, "A static local function can't contain a reference to <variable>." (Una funzione locale statica non può fare riferimento a 'variabile') 

Si consideri il codice seguente. La funzione locale `LocalFunction` accede alla variabile `y`, dichiarata nell'ambito di inclusione (il metodo `M`). Pertanto, non è possibile dichiarare `LocalFunction` con il modificatore `static`:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

Il codice seguente contiene una funzione locale statica. Può essere statica perché non accede ad alcuna variabile nell'ambito di inclusione:

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a>Struct ref Disposable

Un oggetto `struct` dichiarato con il modificatore `ref` potrebbe non implementare alcuna interfaccia e quindi non può implementare <xref:System.IDisposable>. Pertanto, per abilitare un `ref struct` per l'eliminazione, deve avere un metodo `void Dispose()` accessibile. Questo vale anche per le dichiarazioni `readonly ref struct`.

## <a name="nullable-reference-types"></a>Tipi riferimento nullable

All'interno di un contesto delle annotazioni nullable, qualsiasi variabile di un tipo riferimento viene considerata come un **tipo riferimento non nullable**. Se si vuole indicare che una variabile può essere Null, è necessario aggiungere `?` al nome del tipo per dichiarare la variabile come un **tipo riferimento nullable**.

Per i tipi riferimento non nullable, il compilatore usa l'analisi di flusso per garantire che le variabili locali vengano inizializzate su un valore diverso da Null al momento della dichiarazione. I campi devono essere inizializzati durante la costruzione. Il compilatore genera un avviso se la variabile non è impostata da una chiamata a uno qualsiasi dei costruttori disponibili o da un inizializzatore. Inoltre, non è possibile assegnare ai tipi riferimento non nullable un valore che potrebbe essere Null.

I tipi riferimento nullable non vengono controllati per verificare che non vengano assegnati o inizializzati su Null. Tuttavia, il compilatore usa l'analisi di flusso per garantire che qualsiasi variabile di un tipo riferimento nullable venga controllata per i valori Null prima dell'accesso o prima che venga assegnata a un tipo riferimento non nullable.

Altre informazioni su questa funzionalità sono disponibili nella panoramica dei [tipi riferimento nullable](../nullable-references.md). È possibile provare in autonomia in una nuova applicazione in questa [esercitazione sui tipi riferimento nullable](../tutorials/nullable-reference-types.md). Per informazioni sulla procedura per eseguire la migrazione di una base di codice esistente per l'uso dei tipi riferimento nullable, vedere l'[esercitazione sulla migrazione di un'applicazione per l'uso dei tipi riferimento nullable](../tutorials/upgrade-to-nullable-references.md).

## <a name="asynchronous-streams"></a>Flussi asincroni

A partire da C# 8.0, è possibile creare e utilizzare i flussi in modo asincrono. Un metodo che restituisce un flusso asincrono ha tre proprietà:

1. È stato dichiarato con il modificatore `async`.
1. Restituisce <xref:System.Collections.Generic.IAsyncEnumerable%601>.
1. Il metodo contiene istruzioni `yield return` per restituire gli elementi successivi nel flusso asincrono.

Per utilizzare un flusso asincrono, è necessario aggiungere la parola chiave `await` prima della parola chiave `foreach` quando si enumerano gli elementi del flusso. Per l'aggiunta della parola chiave `await`, il metodo che enumera il flusso asincrono deve essere dichiarato con il modificatore `async` e restituire un tipo consentito per un metodo `async`. In genere ciò significa restituire <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Può anche essere <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Un metodo può sia utilizzare che produrre un flusso asincrono, il che significa che restituirebbe <xref:System.Collections.Generic.IAsyncEnumerable%601>. Il codice seguente genera una sequenza da 0 a 19, con un'attesa di 100 ms tra la generazione di ogni numero:

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

La sequenza viene enumerata usando l'istruzione `await foreach`:

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

È possibile provare i flussi asincroni in autonomia nell'esercitazione dedicata alla [creazione e all'utilizzo di flussi asincroni](../tutorials/generate-consume-asynchronous-stream.md).

## <a name="indices-and-ranges"></a>Indici e intervalli

Gli intervalli e gli indici offrono una sintassi concisa per la specifica di intervalli secondari in una matrice, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.

È possibile specificare un indice **dalla fine**. Per specificarlo **dalla fine** si usa l'operatore `^`. Si ha familiarità con `array[2]`, che indica l'elemento "2 dall'inizio". `array[^2]` significa l'elemento "2 dalla fine". L'indice `^0` significa "la fine" o l'indice che segue l'ultimo elemento.

È possibile specificare un **intervallo** con l'**operatore range**: `..`. Ad esempio, `0..^0` specifica l'intero intervallo della matrice: 0 dall'inizio fino a 0 dalla fine, escluso. Per entrambi gli operandi è possibile usare "dall'inizio" o "dalla fine". Inoltre, uno degli operandi può essere omesso. I valori predefiniti sono `0` per l'indice iniziale e `^0` per l'indice finale.

Di seguito verranno esaminati alcuni esempi. Si consideri la matrice seguente, annotata con il relativo indice dall'inizio e dalla fine:

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

L'indice di ogni elemento consolida il concetto di "dall'inizio" e "dalla fine" e che gli intervalli escludono la fine dell'intervallo. L'intera matrice "inizia" con il primo elemento. La "fine" dell'intera matrice è *dopo* l'ultimo elemento.

È possibile recuperare l'ultima parola con l'indice `^1`:

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox". Include da `words[1]` a `words[3]`. L'elemento `words[4]` non è compreso nell'intervallo.

```csharp
var quickBrownFox = words[1..4];
```

Il codice seguente crea un intervallo secondario con "lazy" e "dog". Include `words[^2]` e `words[^1]`. L'indice finale `words[^0]` non viene incluso:

```csharp
var lazyDog = words[^2..^0];
```

Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

È anche possibile dichiarare gli intervalli come variabili:

```csharp
Range phrase = 1..4;
```

L'intervallo può quindi essere usato all'interno dei caratteri `[` e `]`:

```csharp
var text = words[phrase];
```
