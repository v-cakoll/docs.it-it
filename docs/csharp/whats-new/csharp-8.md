---
title: Novità di C' 8.0 - Guida di C
description: Panoramica delle nuove funzionalità disponibili in C# 8.0.
ms.date: 04/07/2020
ms.openlocfilehash: 1a005750751129969f2d1e9caf156330dbe61cb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989207"
---
# <a name="whats-new-in-c-80"></a>Novità di C# 8.0

La versione 8.0 include le funzionalità e i miglioramenti seguenti al linguaggio C:

- [Membri di sola lettura](#readonly-members)
- [Metodi di interfaccia predefiniti](#default-interface-methods)
- [Miglioramenti dei criteri di ricerca](#more-patterns-in-more-places):
  - [Passare da un'espressione all'altra](#switch-expressions)
  - [Criteri per le proprietà](#property-patterns)
  - [Criteri per le tuple](#tuple-patterns)
  - [Criteri per la posizione](#positional-patterns)
- [Utilizzo delle dichiarazioni](#using-declarations)
- [Funzioni locali statiche](#static-local-functions)
- [Struct ref Disposable](#disposable-ref-structs)
- [Tipi riferimento nullable](#nullable-reference-types)
- [Flussi asincroni](#asynchronous-streams)
- [Eliminabile asincrono](#asynchronous-disposable)
- [Indici e intervalli](#indices-and-ranges)
- [Assegnazione di valori Null](#null-coalescing-assignment)
- [Tipi costruiti non gestitiUnmanaged constructed types](#unmanaged-constructed-types)
- [Stackalloc nelle espressioni annidate](#stackalloc-in-nested-expressions)
- [Miglioramento delle stringhe verbatim interpolate](#enhancement-of-interpolated-verbatim-strings)

In **.NET Core 3.x** e **.NET Standard 2.1**è supportata la versione 8.0 di .NET 8.0. Per ulteriori informazioni, vedere [Controllo delle versioni del linguaggio C.](../language-reference/configure-language-version.md)

Il resto di questo articolo descrive brevemente queste funzionalità. Se sono disponibili articoli approfonditi, vengono forniti collegamenti a queste panoramiche ed esercitazioni. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp8* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="readonly-members"></a>Membri di sola lettura

È possibile `readonly` applicare il modificatore ai membri di uno struct. Indica che il membro non modifica lo stato. È più granulare rispetto all'applicazione del modificatore `readonly` a una dichiarazione `struct`.  Considerare lo struct modificabile seguente:

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

Come la maggior `ToString()` parte degli struct, il metodo non modifica lo stato. Si potrebbe indicare questa condizione aggiungendo il modificatore `readonly` alla dichiarazione di `ToString()`:

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

La modifica precedente genera un `ToString` avviso del `Distance` compilatore, poiché `readonly`accede alla proprietà, che non è contrassegnata come :

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

Il compilatore genera un avviso quando deve creare una copia difensiva.  La `Distance` proprietà non modifica lo stato, pertanto è `readonly` possibile correggere questo avviso aggiungendo il modificatore alla dichiarazione:The property doesn't change state, so you can fix this warning by adding the modifier to the declaration:

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

Si noti che il `readonly` modificatore è necessario in una proprietà di sola lettura. Il compilatore non `get` presuppone che le funzioni di accesso non modifichino lo stato. è necessario `readonly` dichiarare in modo esplicito. Le proprietà implementate automaticamente sono un'eccezione; il compilatore considererà tutti i getter implementati automaticamente come readonly, `readonly` quindi `X` qui `Y` non è necessario aggiungere il modificatore alle proprietà e .

Il compilatore applica `readonly` la regola che i membri non modificano lo stato. Il metodo seguente non verrà compilato `readonly` a meno che non si rimuova il modificatore:

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

Questa funzionalità consente di specificare la finalità della progettazione in modo che il compilatore possa imporla e applicare le ottimizzazioni in base a tale finalità. Per ulteriori informazioni sui membri readonly, [`readonly`](../language-reference/keywords/readonly.md#readonly-member-examples)vedere l'articolo di riferimento sulla lingua su .

## <a name="default-interface-methods"></a>Metodi di interfaccia predefiniti

È ora possibile aggiungere membri alle interfacce e fornire un'implementazione per tali membri. Questa funzionalità del linguaggio consente agli autori di API di aggiungere metodi a un'interfaccia nelle versioni più recenti senza compromettere l'origine o la compatibilità binaria con le implementazioni esistenti di tale interfaccia. Le implementazioni esistenti *ereditano* l'implementazione predefinita. Questa funzionalità supporta anche l'interoperabilità di C# con API destinate ad Android o Swift, che supporta funzionalità simili. I metodi di interfaccia predefiniti abilitano anche scenari simili a una funzionalità del linguaggio "tratti".

I metodi di interfaccia predefiniti influiscono su molti scenari ed elementi del linguaggio. La prima esercitazione illustra l'[aggiornamento di un'interfaccia con le implementazioni predefinite](../tutorials/default-interface-methods-versions.md). Sono previsti altre esercitazioni e aggiornamenti dei riferimenti in tempo per il rilascio generale.

## <a name="more-patterns-in-more-places"></a>Più criteri in più posizioni

I **criteri di ricerca** offrono strumenti per fornire funzionalità dipendenti dalla forma su tipi di dati correlati ma diversi. In C'è stata introdotta la sintassi [`is`](../language-reference/keywords/is.md) per i [`switch`](../language-reference/keywords/switch.md) modelli di tipo e i modelli di costante utilizzando l'espressione e l'istruzione . Queste funzionalità rappresentano il primo passo per il supporto dei paradigmi di programmazione in cui i dati e la funzionalità sono separati. Man mano che il settore effettua la transizione verso più microservizi e altre architetture basate sul cloud, diventano necessari altri strumenti del linguaggio.

C# 8.0 espande questo vocabolario, in modo da poter usare più espressioni di criteri in più posizioni nel codice. Prendere in considerazione queste funzionalità quando i dati e le funzionalità sono separati. Prendere in considerazione i criteri di ricerca quando gli algoritmi dipendono da un fatto diverso dal tipo di runtime di un oggetto. Queste tecniche offrono un altro modo per esprimere le progettazioni.

Oltre ai nuovi criteri disponibili in nuove posizioni, C# 8.0 introduce i **criteri ricorsivi**. Il risultato di qualsiasi espressione di criteri è un'espressione. Un criterio ricorsivo è semplicemente un'espressione di criteri applicata all'output di un'altra espressione di criteri.

### <a name="switch-expressions"></a>Espressioni switch

Spesso, [`switch`](../language-reference/keywords/switch.md) un'istruzione produce un `case` valore in ognuno dei blocchi. Le **espressioni switch** consentono di usare una sintassi più concisa per le espressioni con meno parole chiave `case` e `break` ripetitive e un numero inferiore di parentesi graffe.  Ad esempio, si consideri l'enumerazione seguente che elenca i colori dell'arcobaleno:

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

Se l'applicazione ha definito un tipo `RGBColor` costituito dai componenti `R`, `G` e `B`, è possibile convertire un valore `Rainbow` nei relativi valori RGB usando il metodo seguente che contiene un'espressione switch:

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

I **criteri per le proprietà** consentono di individuare corrispondenze in base alle proprietà dell'oggetto esaminato. Si consideri un sito di e-commerce che deve calcolare le imposte sulle vendite in base all'indirizzo dell'acquirente. Questo calcolo non è una `Address` responsabilità fondamentale di una classe. È soggetto a variazioni nel tempo, probabilmente più spesso rispetto a eventuali modifiche del formato dell'indirizzo. L'importo delle imposte sulle vendite dipende dalla proprietà `State` dell'indirizzo. Il metodo seguente usa i criteri per le proprietà per calcolare l'imposta sulle vendite dall'indirizzo e dal prezzo:

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

Considerare anche l'enumerazione seguente, che rappresenta posizioni diverse in un quadrante:

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

Il metodo seguente usa i **criteri per la posizione** per estrarre i valori di `x` e `y`. Quindi usa una clausola `when` per determinare l'elemento `Quadrant` del punto:

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

I criteri discard nell'espressione switch precedente trovano una corrispondenza quando `x` o `y` è uguale a 0, ma non entrambi. Un'espressione switch deve produrre un valore o generare un'eccezione. Se nessuno dei casi corrisponde, l'espressione switch genera un'eccezione. Il compilatore genera automaticamente un avviso se non si coprono tutti i casi possibili nell'espressione switch.

È possibile esplorare le tecniche dei criteri di ricerca in questa [esercitazione avanzata sui criteri di ricerca](../tutorials/pattern-matching.md).

## <a name="using-declarations"></a>Dichiarazioni using

Una **dichiarazione using** è una dichiarazione di variabile preceduta dalla parola chiave `using`. Indica al compilatore che la variabile dichiarata deve essere eliminata alla fine dell'ambito di inclusione. Ad esempio, si consideri il codice seguente che consente di scrivere un file di testo:

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    // Notice how we declare skippedLines after the using statement.
    int skippedLines = 0;
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
        else
        {
            skippedLines++;
        }
    }
    // Notice how skippedLines is in scope here.
    return skippedLines;
    // file is disposed here
}
```

Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura per il metodo. Questa è la fine dell'ambito in cui viene dichiarato `file`. Il codice precedente è equivalente al codice seguente con l'[istruzione using](../language-reference/keywords/using-statement.md) classica:

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    // We must declare the variable outside of the using block
    // so that it is in scope to be returned.
    int skippedLines = 0;
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
            else
            {
                skippedLines++;
            }
        }
    } // file is disposed here
    return skippedLines;
}
```

Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura associata all'istruzione `using`.

In entrambi i casi, il compilatore genera la chiamata a `Dispose()`. Il compilatore genera un errore `using` se l'espressione nell'istruzione non è eliminabile.

## <a name="static-local-functions"></a>Funzioni locali statiche

È ora possibile aggiungere il modificatore `static` alle funzioni locali per assicurarsi che tale funzione locale non acquisisca (faccia riferimento a) variabili dall'ambito di inclusione. In questo modo viene generato l'errore `CS8421` "A static local function can't contain a reference to \<variable>" (Una funzione locale statica non può fare riferimento a <variabile>).

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

Un `struct` dichiarato `ref` con il modificatore non può implementare <xref:System.IDisposable>alcuna interfaccia e pertanto non può implementare . Pertanto, per abilitare un `ref struct` per l'eliminazione, deve avere un metodo `void Dispose()` accessibile. Questa funzione si `readonly ref struct` applica anche alle dichiarazioni.

## <a name="nullable-reference-types"></a>Tipi riferimento nullable

All'interno di un contesto delle annotazioni nullable, qualsiasi variabile di un tipo riferimento viene considerata come un **tipo riferimento non nullable**. Se si vuole indicare che una variabile può essere Null, è necessario aggiungere `?` al nome del tipo per dichiarare la variabile come un **tipo riferimento nullable**.

Per i tipi riferimento non nullable, il compilatore usa l'analisi di flusso per garantire che le variabili locali vengano inizializzate su un valore diverso da Null al momento della dichiarazione. I campi devono essere inizializzati durante la costruzione. Il compilatore genera un avviso se la variabile non è impostata da una chiamata a uno dei costruttori disponibili o da un inizializzatore. Inoltre, non è possibile assegnare ai tipi riferimento non nullable un valore che potrebbe essere Null.

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

È possibile provare i flussi asincroni in autonomia nell'esercitazione dedicata alla [creazione e all'utilizzo di flussi asincroni](../tutorials/generate-consume-asynchronous-stream.md). Per impostazione predefinita, gli elementi di flusso vengono elaborati nel contesto acquisito. Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione. Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo [sull'utilizzo del modello asincrono basato su attività](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).

## <a name="asynchronous-disposable"></a>Eliminabile asincrono

A partire dalla versione 8.0 di C, il <xref:System.IAsyncDisposable?displayProperty=nameWithType> linguaggio supporta i tipi eliminabili asincroni che implementano l'interfaccia. L'operando di `using` un'espressione <xref:System.IDisposable> <xref:System.IAsyncDisposable>può implementare o . Nel caso `IAsyncDisposable`di , il `await` compilatore genera codice per il <xref:System.Threading.Tasks.Task> restituito da <xref:System.IAsyncDisposable.DisposeAsync%2A?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [ `using` l'istruzione](../language-reference/keywords/using-statement.md).

## <a name="indices-and-ranges"></a>Indici e intervalli

Gli indici e gli intervalli forniscono una sintassi concisa per l'accesso a singoli elementi o intervalli in una sequenza.

Questo supporto del linguaggio si basa su due nuovi tipi e due nuovi operatori:

- <xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.
- Indice dall'operatore `^`finale , che specifica che un indice è relativo alla fine della sequenza.
- <xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.
- Operatore `..`di intervallo , che specifica l'inizio e la fine di un intervallo come operandi.

Per iniziare, ecco come funzionano le regole per gli indici. Prendere in considerazione una matrice `sequence`. L'indice `0` è uguale a `sequence[0]`. L'indice `^0` è uguale a `sequence[sequence.Length]`. Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`. Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence.Length - n`.

Un intervallo specifica *inizio* e *fine* di un intervallo. L'inizio dell'intervallo è inclusivo, ma la fine dell'intervallo è esclusiva, il che significa che *l'inizio* è incluso nell'intervallo ma la *fine* non è inclusa nell'intervallo. L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.

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
};              // 9 (or words.Length) ^0
```

È possibile recuperare l'ultima parola con l'indice `^1`:

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox". Include da `words[1]` a `words[3]`. L'elemento `words[4]` non è compreso nell'intervallo.

```csharp
var quickBrownFox = words[1..4];
```

Il codice seguente crea un intervallo secondario con "lazy" e "dog". Include `words[^2]` e `words[^1]`. L'indice `words[^0]` finale non è incluso:

```csharp
var lazyDog = words[^2..^0];
```

Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

È anche possibile dichiarare gli intervalli come variabili:

```csharp
Range phrase = 1..4;
```

L'intervallo può quindi essere usato all'interno dei caratteri `[` e `]`:

```csharp
var text = words[phrase];
```

Non solo gli array supportano indici e intervalli. È inoltre possibile utilizzare indici [string](../language-reference/builtin-types/reference-types.md#the-string-type)e <xref:System.Span%601>intervalli con string , , o <xref:System.ReadOnlySpan%601>. Per ulteriori informazioni, consultate Supporto dei tipi [per indici e intervalli](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).

È possibile ottenere maggiori informazioni su indici e intervalli nell'esercitazione [Indici e intervalli](../tutorials/ranges-indexes.md).

## <a name="null-coalescing-assignment"></a>Assegnazione di valori Null

In Visual Basic 8.0 è stato introdotto `??=`l'operatore di assegnazione null-coalescing . È possibile `??=` utilizzare l'operatore per assegnare il valore del relativo operando di destra al relativo `null`operando di sinistra solo se l'operando di sinistra restituisce .

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

Per ulteriori informazioni, vedere il [?? e ?? :](../language-reference/operators/null-coalescing-operator.md) articolo degli operatori.

## <a name="unmanaged-constructed-types"></a>Tipi costruiti non gestitiUnmanaged constructed types

Nelle versioni precedenti e la versione 7.3 del linguaggio C, un tipo costruito (un tipo che include almeno un argomento di tipo) non può essere un [tipo non gestito.](../language-reference/builtin-types/unmanaged-types.md) A partire dalla versione 8.0 di C, un tipo di valore costruito non è gestito se contiene solo campi di tipi non gestiti.

Ad esempio, data la seguente `Coords<T>` definizione del tipo generico:

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

il `Coords<int>` tipo è un tipo non gestito in C . Come per qualsiasi tipo non gestito, è possibile creare un puntatore a una variabile di questo tipo o [allocare un blocco di memoria nello stack](../language-reference/operators/stackalloc.md) per le istanze di questo tipo:

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

Per ulteriori informazioni, vedere [Tipi non gestiti](../language-reference/builtin-types/unmanaged-types.md).

## <a name="stackalloc-in-nested-expressions"></a>Stackalloc nelle espressioni annidate

A partire dalla versione 8.0 di C, se il <xref:System.Span%601?displayProperty=nameWithType> <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> risultato di un'espressione [stackalloc](../language-reference/operators/stackalloc.md) è di tipo o , è possibile usare l'espressione `stackalloc` in altre espressioni:

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6 ,8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a>Miglioramento delle stringhe verbatim interpolate

L'ordine `$` `@` dei token e nelle stringhe verbatim [interpolate](../language-reference/tokens/interpolated.md) può essere qualsiasi: entrambi `$@"..."` e `@$"..."` sono stringhe letterali interpolate valide. Nelle versioni precedenti di `$` C, il `@` token deve essere visualizzato prima del token.
