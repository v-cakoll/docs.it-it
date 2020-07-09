---
title: Scelta tra tipi anonimi e di tupla
description: Informazioni su quando è opportuno scegliere tra tipi anonimi e tipo di tupla.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 9140250ad1f48501bf1d2e53a1c179e6823f19cd
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100964"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a>Scelta tra tipi anonimi e di tupla

La scelta del tipo appropriato comporta una valutazione dell'usabilità, delle prestazioni e dei compromessi rispetto ad altri tipi. I tipi anonimi sono disponibili a partire da C# 3,0, mentre i tipi generici <xref:System.Tuple%602?displayProperty=nameWithType> sono stati introdotti con .NET Framework 4,0. Dal momento che sono state introdotte nuove opzioni con il supporto a livello di lingua, ad esempio, come indicato <xref:System.ValueTuple%602?displayProperty=nameWithType> dal nome, fornire un tipo di valore con la flessibilità dei tipi anonimi. In questo articolo si apprenderà quando è opportuno scegliere un tipo rispetto all'altro.

## <a name="usability-and-functionality"></a>Usabilità e funzionalità

I tipi anonimi sono stati introdotti in C# 3,0 con espressioni LINQ (Language Integrated Query). Con LINQ, gli sviluppatori spesso proiettano i risultati delle query in tipi anonimi che contengono alcune proprietà Select degli oggetti con cui lavorano. Si consideri l'esempio seguente, che crea un'istanza di una matrice di <xref:System.DateTime> oggetti, e ne scorre la proiezione in un tipo anonimo con due proprietà.

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var anonymous in
             dates.Select(
                 date => new { Formatted = $"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks }))
{
    Console.WriteLine($"Ticks: {anonymous.Ticks}, formatted: {anonymous.Formatted}");
}
```

Viene creata un'istanza dei tipi anonimi usando l' [`new`](../../csharp/language-reference/operators/new-operator.md) operatore e i nomi e i tipi delle proprietà vengono dedotti dalla dichiarazione. Se due o più inizializzatori di oggetti anonimi nello stesso assembly specificano una sequenza di proprietà nello stesso ordine e con gli stessi nomi e tipi, il compilatore considera gli oggetti come istanze dello stesso tipo. Condividono le stesse informazioni sul tipo generate dal compilatore.

Il frammento C# precedente proietta un tipo anonimo con due proprietà, analogamente alla seguente classe C# generata dal compilatore:

```csharp
internal sealed class f__AnonymousType0
{
    public string Formatted { get; }
    public long Ticks { get; }

    public f__AnonymousType0(string formatted, long ticks)
    {
        Formatted = formatted;
        Ticks = ticks;
    }
}
```

Per ulteriori informazioni, vedere [tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). La stessa funzionalità è disponibile con le tuple quando si proiettano in query LINQ, è possibile selezionare le proprietà in Tuple. Queste Tuple passano attraverso la query, analogamente ai tipi anonimi. Si consideri ora l'esempio seguente usando `System.Tuple<string, long>` .

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var tuple in
            dates.Select(
                date => new Tuple<string, long>($"{date:MMM dd, yyyy hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {tuple.Item2}, formatted: {tuple.Item1}");
}
```

Con <xref:System.Tuple%602?displayProperty=nameWithType> , l'istanza espone le proprietà degli elementi numerati, ad esempio `Item1` , e `Item2` . Questi nomi di proprietà possono rendere più difficile la comprensione dello scopo dei valori delle proprietà, in quanto il nome della proprietà fornisce solo il numero ordinale. I `System.Tuple` tipi sono inoltre tipi di riferimento `class` . <xref:System.ValueTuple%602?displayProperty=nameWithType>Tuttavia, è un tipo di valore `struct` . Il frammento C# seguente usa `ValueTuple<string, long>` per proiettare in. In questo modo, assegna usando una sintassi letterale.

```csharp-interactive
var dates = new[]
{
    DateTime.UtcNow.AddHours(-1),
    DateTime.UtcNow,
    DateTime.UtcNow.AddHours(1),
};

foreach (var (formatted, ticks) in
            dates.Select(
                date => (Formatted: $"{date:MMM dd, yyyy at hh:mm zzz}", date.Ticks)))
{
    Console.WriteLine($"Ticks: {ticks}, formatted: {formatted}");
}
```

C# fornisce il supporto del linguaggio per le tuple con il <xref:System.ValueTuple> tipo e la semantica per:

- [Assegnazione di Tuple](../../csharp/tuples.md#assignment-and-tuples)
- [Decostruzione di Tuple](../../csharp/deconstruct.md) (non limitate a Tuple)
- [Controlli di uguaglianza della tupla](../../csharp/tuples.md#equality-and-tuples)
- [Inizializzatori di proiezione tupla](../../csharp/tuples.md#tuple-projection-initializers)

Gli esempi precedenti sono tutti funzionalmente equivalenti, tuttavia; l'usabilità e le implementazioni sottostanti sono lievemente irrilevanti.

## <a name="tradeoffs"></a>Compromessi

Potrebbe essere necessario utilizzare sempre <xref:System.ValueTuple> <xref:System.Tuple> i tipi anonimi, ma è necessario considerare compromessi. I <xref:System.ValueTuple> tipi sono modificabili, mentre sono di sola <xref:System.Tuple> lettura. I tipi anonimi possono essere utilizzati negli alberi delle espressioni, mentre le tuple non possono. La tabella seguente è una panoramica di alcune delle differenze principali.

### <a name="key-differences"></a>Differenze principali

| Nome                     | Modificatore di accesso | Type     | Nome del membro personalizzato | Supporto per la decostruzione | Supporto dell'albero delle espressioni |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| Tipi anonimi          | `internal`      | `class`  | ✔️                   | ❌                     | ✔️                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | ✔️                     |
| <xref:System.ValueTuple> | `public`        | `struct` | ✔️                   | ✔️                     | ❌                     |

### <a name="serialization"></a>Serializzazione

Una considerazione importante per la scelta di un tipo è la necessità o meno di serializzare. La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato. Per ulteriori informazioni, vedere [serializzazione](../../csharp/programming-guide/concepts/serialization/index.md). Quando la serializzazione è importante, la creazione di un oggetto `class` o `struct` è preferibile a tipi anonimi o tipi di tupla

## <a name="performance"></a>Prestazioni

Le prestazioni tra questi tipi dipendono dallo scenario. L'effetto principale riguarda il compromesso tra le allocazioni e la copia. Nella maggior parte degli scenari, l'effetto è ridotto. Quando possono verificarsi conseguenze principali, è necessario adottare misure per informare la decisione.

## <a name="conclusion"></a>Conclusioni

Per gli sviluppatori che scelgono tra le tuple e i tipi anonimi, è necessario prendere in considerazione diversi fattori. In generale, se non si utilizzano alberi delle [espressioni](../../csharp/expression-trees.md)e si ha familiarità con la sintassi di tupla, scegliere <xref:System.ValueTuple> il tipo di valore con la flessibilità per assegnare un nome alle proprietà. Se si usano gli alberi delle espressioni e si preferisce assegnare un nome alle proprietà, scegliere tipi anonimi. In caso contrario, usare <xref:System.Tuple>.

## <a name="see-also"></a>Vedere anche

- [Tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Alberi delle espressioni](../../csharp/expression-trees.md)
- [Tipi di tupla](../../csharp/tuples.md)
- [Linee guida per la progettazione di tipi](../design-guidelines/type.md)
