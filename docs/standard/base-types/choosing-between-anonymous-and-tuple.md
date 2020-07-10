---
title: Scelta tra tipi anonimi e di tupla
description: Informazioni su quando è opportuno scegliere tra tipi anonimi e tipo di tupla.
author: IEvangelist
ms.author: dapine
ms.date: 07/01/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 9c186133a639faf187c89d872856d860a20f5a2d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174218"
---
# <a name="choosing-between-anonymous-and-tuple-types"></a><span data-ttu-id="26539-103">Scelta tra tipi anonimi e di tupla</span><span class="sxs-lookup"><span data-stu-id="26539-103">Choosing between anonymous and tuple types</span></span>

<span data-ttu-id="26539-104">La scelta del tipo appropriato comporta una valutazione dell'usabilità, delle prestazioni e dei compromessi rispetto ad altri tipi.</span><span class="sxs-lookup"><span data-stu-id="26539-104">Choosing the appropriate type involves considering its usability, performance, and tradeoffs compared to other types.</span></span> <span data-ttu-id="26539-105">I tipi anonimi sono disponibili a partire da C# 3,0, mentre i tipi generici <xref:System.Tuple%602?displayProperty=nameWithType> sono stati introdotti con .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="26539-105">Anonymous types have been available since C# 3.0, while generic <xref:System.Tuple%602?displayProperty=nameWithType> types were introduced with .NET Framework 4.0.</span></span> <span data-ttu-id="26539-106">Dal momento che sono state introdotte nuove opzioni con il supporto a livello di lingua, ad esempio, come indicato <xref:System.ValueTuple%602?displayProperty=nameWithType> dal nome, fornire un tipo di valore con la flessibilità dei tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="26539-106">Since then new options have been introduced with language level support, such as <xref:System.ValueTuple%602?displayProperty=nameWithType> - which as the name implies, provide a value type with the flexibility of anonymous types.</span></span> <span data-ttu-id="26539-107">In questo articolo si apprenderà quando è opportuno scegliere un tipo rispetto all'altro.</span><span class="sxs-lookup"><span data-stu-id="26539-107">In this article, you'll learn when it's appropriate to choose one type over the other.</span></span>

## <a name="usability-and-functionality"></a><span data-ttu-id="26539-108">Usabilità e funzionalità</span><span class="sxs-lookup"><span data-stu-id="26539-108">Usability and functionality</span></span>

<span data-ttu-id="26539-109">I tipi anonimi sono stati introdotti in C# 3,0 con espressioni LINQ (Language Integrated Query).</span><span class="sxs-lookup"><span data-stu-id="26539-109">Anonymous types were introduced in C# 3.0 with Language-Integrated Query (LINQ) expressions.</span></span> <span data-ttu-id="26539-110">Con LINQ, gli sviluppatori spesso proiettano i risultati delle query in tipi anonimi che contengono alcune proprietà Select degli oggetti con cui lavorano.</span><span class="sxs-lookup"><span data-stu-id="26539-110">With LINQ, developers often project results from queries into anonymous types that hold a few select properties from the objects they're working with.</span></span> <span data-ttu-id="26539-111">Si consideri l'esempio seguente, che crea un'istanza di una matrice di <xref:System.DateTime> oggetti, e ne scorre la proiezione in un tipo anonimo con due proprietà.</span><span class="sxs-lookup"><span data-stu-id="26539-111">Consider the following example, that instantiates an array of <xref:System.DateTime> objects, and iterates through them projecting into an anonymous type with two properties.</span></span>

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

<span data-ttu-id="26539-112">Viene creata un'istanza dei tipi anonimi usando l' [`new`](../../csharp/language-reference/operators/new-operator.md) operatore e i nomi e i tipi delle proprietà vengono dedotti dalla dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="26539-112">Anonymous types are instantiated by using the [`new`](../../csharp/language-reference/operators/new-operator.md) operator, and the property names and types are inferred from the declaration.</span></span> <span data-ttu-id="26539-113">Se due o più inizializzatori di oggetti anonimi nello stesso assembly specificano una sequenza di proprietà nello stesso ordine e con gli stessi nomi e tipi, il compilatore considera gli oggetti come istanze dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="26539-113">If two or more anonymous object initializers in the same assembly specify a sequence of properties that are in the same order and that have the same names and types, the compiler treats the objects as instances of the same type.</span></span> <span data-ttu-id="26539-114">Condividono le stesse informazioni sul tipo generate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="26539-114">They share the same compiler-generated type information.</span></span>

<span data-ttu-id="26539-115">Il frammento C# precedente proietta un tipo anonimo con due proprietà, analogamente alla seguente classe C# generata dal compilatore:</span><span class="sxs-lookup"><span data-stu-id="26539-115">The previous C# snippet projects an anonymous type with two properties, much like the following compiler-generated C# class:</span></span>

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

<span data-ttu-id="26539-116">Per ulteriori informazioni, vedere [tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="26539-116">For more information, see [anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="26539-117">La stessa funzionalità è disponibile con le tuple quando si proiettano in query LINQ, è possibile selezionare le proprietà in Tuple.</span><span class="sxs-lookup"><span data-stu-id="26539-117">The same functionality exists with tuples when projecting into LINQ queries, you can select properties into tuples.</span></span> <span data-ttu-id="26539-118">Queste Tuple passano attraverso la query, analogamente ai tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="26539-118">These tuples flow through the query, just as anonymous types would.</span></span> <span data-ttu-id="26539-119">Si consideri ora l'esempio seguente usando `System.Tuple<string, long>` .</span><span class="sxs-lookup"><span data-stu-id="26539-119">Now consider the following example using the `System.Tuple<string, long>`.</span></span>

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

<span data-ttu-id="26539-120">Con <xref:System.Tuple%602?displayProperty=nameWithType> , l'istanza espone le proprietà degli elementi numerati, ad esempio `Item1` , e `Item2` .</span><span class="sxs-lookup"><span data-stu-id="26539-120">With the <xref:System.Tuple%602?displayProperty=nameWithType>, the instance exposes numbered item properties, such as `Item1`, and `Item2`.</span></span> <span data-ttu-id="26539-121">Questi nomi di proprietà possono rendere più difficile la comprensione dello scopo dei valori delle proprietà, in quanto il nome della proprietà fornisce solo il numero ordinale.</span><span class="sxs-lookup"><span data-stu-id="26539-121">These property names can make it more difficult to understand the intent of the property values, as the property name only provides the ordinal.</span></span> <span data-ttu-id="26539-122">I `System.Tuple` tipi sono inoltre tipi di riferimento `class` .</span><span class="sxs-lookup"><span data-stu-id="26539-122">Furthermore, the `System.Tuple` types are reference `class` types.</span></span> <span data-ttu-id="26539-123"><xref:System.ValueTuple%602?displayProperty=nameWithType>Tuttavia, è un tipo di valore `struct` .</span><span class="sxs-lookup"><span data-stu-id="26539-123">The <xref:System.ValueTuple%602?displayProperty=nameWithType> however, is a value `struct` type.</span></span> <span data-ttu-id="26539-124">Il frammento C# seguente usa `ValueTuple<string, long>` per proiettare in.</span><span class="sxs-lookup"><span data-stu-id="26539-124">The following C# snippet, uses `ValueTuple<string, long>` to project into.</span></span> <span data-ttu-id="26539-125">In questo modo, assegna usando una sintassi letterale.</span><span class="sxs-lookup"><span data-stu-id="26539-125">In doing so, it assigns using a literal syntax.</span></span>

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

<span data-ttu-id="26539-126">Per ulteriori informazioni sulle tuple, vedere [tipi di tupla (riferimenti per C#)](../../csharp/language-reference/builtin-types/value-tuples.md) o [tuple (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).</span><span class="sxs-lookup"><span data-stu-id="26539-126">For more information about tuples, see [Tuple types (C# reference)](../../csharp/language-reference/builtin-types/value-tuples.md) or [Tuples (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/tuples.md).</span></span>

<span data-ttu-id="26539-127">Gli esempi precedenti sono tutti funzionalmente equivalenti, tuttavia; l'usabilità e le implementazioni sottostanti sono lievemente irrilevanti.</span><span class="sxs-lookup"><span data-stu-id="26539-127">The previous examples are all functionally equivalent, however; there are slight differences in their usability and their underlying implementations.</span></span>

## <a name="tradeoffs"></a><span data-ttu-id="26539-128">Compromessi</span><span class="sxs-lookup"><span data-stu-id="26539-128">Tradeoffs</span></span>

<span data-ttu-id="26539-129">Potrebbe essere necessario utilizzare sempre <xref:System.ValueTuple> <xref:System.Tuple> i tipi anonimi, ma è necessario considerare compromessi.</span><span class="sxs-lookup"><span data-stu-id="26539-129">You might want to always use <xref:System.ValueTuple> over <xref:System.Tuple>, and anonymous types, but there are tradeoffs you should consider.</span></span> <span data-ttu-id="26539-130">I <xref:System.ValueTuple> tipi sono modificabili, mentre sono di sola <xref:System.Tuple> lettura.</span><span class="sxs-lookup"><span data-stu-id="26539-130">The <xref:System.ValueTuple> types are mutable, whereas <xref:System.Tuple> are read-only.</span></span> <span data-ttu-id="26539-131">I tipi anonimi possono essere utilizzati negli alberi delle espressioni, mentre le tuple non possono.</span><span class="sxs-lookup"><span data-stu-id="26539-131">Anonymous types can be used in expression trees, while tuples cannot.</span></span> <span data-ttu-id="26539-132">La tabella seguente è una panoramica di alcune delle differenze principali.</span><span class="sxs-lookup"><span data-stu-id="26539-132">The following table is an overview of some of the key differences.</span></span>

### <a name="key-differences"></a><span data-ttu-id="26539-133">Differenze principali</span><span class="sxs-lookup"><span data-stu-id="26539-133">Key differences</span></span>

| <span data-ttu-id="26539-134">Nome</span><span class="sxs-lookup"><span data-stu-id="26539-134">Name</span></span>                     | <span data-ttu-id="26539-135">Modificatore di accesso</span><span class="sxs-lookup"><span data-stu-id="26539-135">Access modifier</span></span> | <span data-ttu-id="26539-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="26539-136">Type</span></span>     | <span data-ttu-id="26539-137">Nome del membro personalizzato</span><span class="sxs-lookup"><span data-stu-id="26539-137">Custom member name</span></span> | <span data-ttu-id="26539-138">Supporto per la decostruzione</span><span class="sxs-lookup"><span data-stu-id="26539-138">Deconstruction support</span></span> | <span data-ttu-id="26539-139">Supporto dell'albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="26539-139">Expression tree support</span></span> |
|--------------------------|-----------------|----------|----------------------|------------------------|-------------------------|
| <span data-ttu-id="26539-140">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="26539-140">Anonymous types</span></span>          | `internal`      | `class`  | <span data-ttu-id="26539-141">✔️</span><span class="sxs-lookup"><span data-stu-id="26539-141">✔️</span></span>                   | ❌                     | <span data-ttu-id="26539-142">✔️</span><span class="sxs-lookup"><span data-stu-id="26539-142">✔️</span></span>                     |
| <xref:System.Tuple>      | `public`        | `class`  | ❌                   | ❌                     | <span data-ttu-id="26539-143">✔️</span><span class="sxs-lookup"><span data-stu-id="26539-143">✔️</span></span>                     |
| <xref:System.ValueTuple> | `public`        | `struct` | <span data-ttu-id="26539-144">✔️</span><span class="sxs-lookup"><span data-stu-id="26539-144">✔️</span></span>                   | <span data-ttu-id="26539-145">✔️</span><span class="sxs-lookup"><span data-stu-id="26539-145">✔️</span></span>                     | ❌                     |

### <a name="serialization"></a><span data-ttu-id="26539-146">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="26539-146">Serialization</span></span>

<span data-ttu-id="26539-147">Una considerazione importante per la scelta di un tipo è la necessità o meno di serializzare.</span><span class="sxs-lookup"><span data-stu-id="26539-147">One important consideration when choosing a type, is whether or not it will need to be serialized.</span></span> <span data-ttu-id="26539-148">La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato.</span><span class="sxs-lookup"><span data-stu-id="26539-148">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="26539-149">Per ulteriori informazioni, vedere [serializzazione](../../csharp/programming-guide/concepts/serialization/index.md).</span><span class="sxs-lookup"><span data-stu-id="26539-149">For more information, see [serialization](../../csharp/programming-guide/concepts/serialization/index.md).</span></span> <span data-ttu-id="26539-150">Quando la serializzazione è importante, la creazione di un oggetto `class` o `struct` è preferibile a tipi anonimi o tipi di tupla</span><span class="sxs-lookup"><span data-stu-id="26539-150">When serialization is important, creating a `class` or `struct` is preferred over anonymous types or tuple types.</span></span>

## <a name="performance"></a><span data-ttu-id="26539-151">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="26539-151">Performance</span></span>

<span data-ttu-id="26539-152">Le prestazioni tra questi tipi dipendono dallo scenario.</span><span class="sxs-lookup"><span data-stu-id="26539-152">Performance between these types depends on the scenario.</span></span> <span data-ttu-id="26539-153">L'effetto principale riguarda il compromesso tra le allocazioni e la copia.</span><span class="sxs-lookup"><span data-stu-id="26539-153">The major impact involves the tradeoff between allocations and copying.</span></span> <span data-ttu-id="26539-154">Nella maggior parte degli scenari, l'effetto è ridotto.</span><span class="sxs-lookup"><span data-stu-id="26539-154">In most scenarios, the impact is small.</span></span> <span data-ttu-id="26539-155">Quando possono verificarsi conseguenze principali, è necessario adottare misure per informare la decisione.</span><span class="sxs-lookup"><span data-stu-id="26539-155">When major impacts could arise, measurements should be taken to inform the decision.</span></span>

## <a name="conclusion"></a><span data-ttu-id="26539-156">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="26539-156">Conclusion</span></span>

<span data-ttu-id="26539-157">Per gli sviluppatori che scelgono tra le tuple e i tipi anonimi, è necessario prendere in considerazione diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="26539-157">As a developer choosing between tuples and anonymous types, there are several factors to consider.</span></span> <span data-ttu-id="26539-158">In generale, se non si utilizzano alberi delle [espressioni](../../csharp/expression-trees.md)e si ha familiarità con la sintassi di tupla, scegliere <xref:System.ValueTuple> il tipo di valore con la flessibilità per assegnare un nome alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="26539-158">Generally speaking, if you're not working with [expression trees](../../csharp/expression-trees.md), and you're comfortable with tuple syntax then choose <xref:System.ValueTuple> as they provide a value type with the flexibility to name properties.</span></span> <span data-ttu-id="26539-159">Se si usano gli alberi delle espressioni e si preferisce assegnare un nome alle proprietà, scegliere tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="26539-159">If you're working with expression trees, and you'd prefer to name properties, choose anonymous types.</span></span> <span data-ttu-id="26539-160">In caso contrario, usare <xref:System.Tuple>.</span><span class="sxs-lookup"><span data-stu-id="26539-160">Otherwise, use <xref:System.Tuple>.</span></span>

## <a name="see-also"></a><span data-ttu-id="26539-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26539-161">See also</span></span>

- [<span data-ttu-id="26539-162">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="26539-162">Anonymous types</span></span>](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="26539-163">Alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="26539-163">Expression trees</span></span>](../../csharp/expression-trees.md)
- [<span data-ttu-id="26539-164">Tipi di tupla (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="26539-164">Tuple types (C# reference)</span></span>](../../csharp/language-reference/builtin-types/value-tuples.md)
- [<span data-ttu-id="26539-165">Tuple (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26539-165">Tuples (Visual Basic)</span></span>](../../visual-basic/programming-guide/language-features/data-types/tuples.md)
- [<span data-ttu-id="26539-166">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="26539-166">Type design guidelines</span></span>](../design-guidelines/type.md)
