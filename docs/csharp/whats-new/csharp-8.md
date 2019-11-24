---
title: What's new in C# 8.0 - C# Guide
description: Panoramica delle nuove funzionalità disponibili in C# 8.0.
ms.date: 09/20/2019
ms.openlocfilehash: 540b95beaf00c17812a3b602602504278be69b0e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429395"
---
# <a name="whats-new-in-c-80"></a>Novità di C# 8.0

C# 8.0 adds the following features and enhancements to the C# language:

- [Membri di sola lettura](#readonly-members)
- [Default interface methods](#default-interface-methods)
- [Miglioramenti dei criteri di ricerca](#more-patterns-in-more-places):
  - [Espressioni switch](#switch-expressions)
  - [Criteri per le proprietà](#property-patterns)
  - [Criteri per le tuple](#tuple-patterns)
  - [Criteri per la posizione](#positional-patterns)
- [Dichiarazioni using](#using-declarations)
- [Funzioni locali statiche](#static-local-functions)
- [Struct ref Disposable](#disposable-ref-structs)
- [Tipi riferimento nullable](#nullable-reference-types)
- [Flussi asincroni](#asynchronous-streams)
- [Indici e intervalli](#indices-and-ranges)
- [Null-coalescing assignment](#null-coalescing-assignment)
- [Unmanaged constructed types](#unmanaged-constructed-types)
- [Stackalloc in nested expressions](#stackalloc-in-nested-expressions)
- [Enhancement of interpolated verbatim strings](#enhancement-of-interpolated-verbatim-strings)

C# 8.0 is supported on **.NET Core 3.x** and **.NET Standard 2.1**. For more information, see [C# language versioning](../language-reference/configure-language-version.md).

Il resto di questo articolo descrive brevemente queste funzionalità. Se sono disponibili articoli approfonditi, vengono forniti collegamenti a queste panoramiche ed esercitazioni. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp8* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="readonly-members"></a>Membri di sola lettura

You can apply the `readonly` modifier to members of a struct. It indicates that the member doesn't modify state. È più granulare rispetto all'applicazione del modificatore `readonly` a una dichiarazione `struct`.  Considerare lo struct modificabile seguente:

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

Like most structs, the `ToString()` method doesn't modify state. Si potrebbe indicare questa condizione aggiungendo il modificatore `readonly` alla dichiarazione di `ToString()`:

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which isn't marked `readonly`:

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

Il compilatore genera un avviso quando deve creare una copia difensiva.  The `Distance` property doesn't change state, so you can fix this warning by adding the `readonly` modifier to the declaration:

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

Notice that the `readonly` modifier is necessary on a read-only property. The compiler doesn't assume `get` accessors don't modify state; you must declare `readonly` explicitly. Auto-implemented properties are an exception; the compiler will treat all auto-implemented getters as readonly, so here there's no need to add the `readonly` modifier to the `X` and `Y` properties.

The compiler does enforce the rule that `readonly` members don't modify state. The following method won't compile unless you remove the `readonly` modifier:

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

Questa funzionalità consente di specificare la finalità della progettazione in modo che il compilatore possa imporla e applicare le ottimizzazioni in base a tale finalità. You can learn more about readonly members in the language reference article on [`readonly`](../language-reference/keywords/readonly.md#readonly-member-examples).

## <a name="default-interface-methods"></a>Metodi di interfaccia predefiniti

È ora possibile aggiungere membri alle interfacce e fornire un'implementazione per tali membri. Questa funzionalità del linguaggio consente agli autori di API di aggiungere metodi a un'interfaccia nelle versioni più recenti senza compromettere l'origine o la compatibilità binaria con le implementazioni esistenti di tale interfaccia. Le implementazioni esistenti *ereditano* l'implementazione predefinita. Questa funzionalità supporta anche l'interoperabilità di C# con API destinate ad Android o Swift, che supporta funzionalità simili. Default interface methods also enable scenarios similar to a "traits" language feature.

Default interface methods affects many scenarios and language elements. La prima esercitazione illustra l'[aggiornamento di un'interfaccia con le implementazioni predefinite](../tutorials/default-interface-methods-versions.md). Sono previsti altre esercitazioni e aggiornamenti dei riferimenti in tempo per il rilascio generale.

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

I **criteri per le proprietà** consentono di individuare corrispondenze in base alle proprietà dell'oggetto esaminato. Si consideri un sito di e-commerce che deve calcolare le imposte sulle vendite in base all'indirizzo dell'acquirente. That computation isn't a core responsibility of an `Address` class. È soggetto a variazioni nel tempo, probabilmente più spesso rispetto a eventuali modifiche del formato dell'indirizzo. L'importo delle imposte sulle vendite dipende dalla proprietà `State` dell'indirizzo. Il metodo seguente usa i criteri per le proprietà per calcolare l'imposta sulle vendite dall'indirizzo e dal prezzo:

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

I criteri discard nell'espressione switch precedente trovano una corrispondenza quando `x` o `y` è uguale a 0, ma non entrambi. Un'espressione switch deve produrre un valore o generare un'eccezione. Se nessuno dei casi corrisponde, l'espressione switch genera un'eccezione. The compiler generates a warning for you if you don't cover all possible cases in your switch expression.

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

In entrambi i casi, il compilatore genera la chiamata a `Dispose()`. The compiler generates an error if the expression in the `using` statement isn't disposable.

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

A `struct` declared with the `ref` modifier may not implement any interfaces and so can't implement <xref:System.IDisposable>. Pertanto, per abilitare un `ref struct` per l'eliminazione, deve avere un metodo `void Dispose()` accessibile. This feature also applies to `readonly ref struct` declarations.

## <a name="nullable-reference-types"></a>Tipi riferimento nullable

All'interno di un contesto delle annotazioni nullable, qualsiasi variabile di un tipo riferimento viene considerata come un **tipo riferimento non nullable**. Se si vuole indicare che una variabile può essere Null, è necessario aggiungere `?` al nome del tipo per dichiarare la variabile come un **tipo riferimento nullable**.

Per i tipi riferimento non nullable, il compilatore usa l'analisi di flusso per garantire che le variabili locali vengano inizializzate su un valore diverso da Null al momento della dichiarazione. I campi devono essere inizializzati durante la costruzione. The compiler generates a warning if the variable isn't set by a call to any of the available constructors or by an initializer. Inoltre, non è possibile assegnare ai tipi riferimento non nullable un valore che potrebbe essere Null.

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

Indices and ranges provide a succinct syntax for accessing single elements or ranges in a sequence.

This language support relies on two new types, and two new operators:

- <xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.
- The index from end operator `^`, which specifies that an index is relative to the end of the sequence.
- <xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.
- The range operator `..`, which specifies the start and end of a range as its operands.

Per iniziare, ecco come funzionano le regole per gli indici. Prendere in considerazione una matrice `sequence`. L'indice `0` è uguale a `sequence[0]`. L'indice `^0` è uguale a `sequence[sequence.Length]`. Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`. Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence.Length - n`.

Un intervallo specifica *inizio* e *fine* di un intervallo. The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* isn't included in the range. L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.

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

Il codice seguente crea un intervallo secondario con "lazy" e "dog". Include `words[^2]` e `words[^1]`. The end index `words[^0]` isn't included:

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

Not only arrays support indices and ranges. You also can use indices and ranges with [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>. For more information, see [Type support for indices and ranges](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).

È possibile ottenere maggiori informazioni su indici e intervalli nell'esercitazione [Indici e intervalli](../tutorials/ranges-indexes.md).

## <a name="null-coalescing-assignment"></a>Null-coalescing assignment

C# 8.0 introduces the null-coalescing assignment operator `??=`. You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.

## <a name="unmanaged-constructed-types"></a>Unmanaged constructed types

In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) can't be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md). Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.

For example, given the following definition of the generic `Coords<T>` type:

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

the `Coords<int>` type is an unmanaged type in C# 8.0 and later. Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).

## <a name="stackalloc-in-nested-expressions"></a>Stackalloc in nested expressions

Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6 ,8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a>Enhancement of interpolated verbatim strings

Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings. In earlier C# versions, the `$` token must appear before the `@` token.
