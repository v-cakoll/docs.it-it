---
title: Novità di C# 8.0 - Guida a C#
description: Panoramica delle nuove funzionalità disponibili in C# 8.0. Questo articolo è aggiornato alla versione di anteprima 5.
ms.date: 09/02/2019
ms.openlocfilehash: 7210f2e978f307b3ecef2eff272fea0d19025de6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252895"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="e9000-104">Novità di C# 8.0</span><span class="sxs-lookup"><span data-stu-id="e9000-104">What's new in C# 8.0</span></span>

<span data-ttu-id="e9000-105">Sono disponibili numerosi miglioramenti per il linguaggio C# che è già possibile provare.</span><span class="sxs-lookup"><span data-stu-id="e9000-105">There are many enhancements to the C# language that you can try out already.</span></span>

- [<span data-ttu-id="e9000-106">Membri di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9000-106">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="e9000-107">Membri di interfaccia predefiniti</span><span class="sxs-lookup"><span data-stu-id="e9000-107">Default interface members</span></span>](#default-interface-members)
- <span data-ttu-id="e9000-108">[Miglioramenti dei criteri di ricerca](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="e9000-108">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="e9000-109">Espressioni switch</span><span class="sxs-lookup"><span data-stu-id="e9000-109">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="e9000-110">Criteri per le proprietà</span><span class="sxs-lookup"><span data-stu-id="e9000-110">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="e9000-111">Criteri per le tuple</span><span class="sxs-lookup"><span data-stu-id="e9000-111">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="e9000-112">Criteri per la posizione</span><span class="sxs-lookup"><span data-stu-id="e9000-112">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="e9000-113">Dichiarazioni using</span><span class="sxs-lookup"><span data-stu-id="e9000-113">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="e9000-114">Funzioni locali statiche</span><span class="sxs-lookup"><span data-stu-id="e9000-114">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="e9000-115">Struct ref Disposable</span><span class="sxs-lookup"><span data-stu-id="e9000-115">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="e9000-116">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="e9000-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="e9000-117">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="e9000-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="e9000-118">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="e9000-118">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="e9000-119">Miglioramento delle stringhe verbatim interpolate</span><span class="sxs-lookup"><span data-stu-id="e9000-119">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

> [!NOTE]
> <span data-ttu-id="e9000-120">Questo articolo è stato aggiornato per l'ultima volta per l'anteprima 5 di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="e9000-120">This article was last updated for C# 8.0 preview 5.</span></span>

<span data-ttu-id="e9000-121">Il resto di questo articolo descrive brevemente queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e9000-121">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="e9000-122">Se sono disponibili articoli approfonditi, vengono forniti collegamenti a queste panoramiche ed esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="e9000-122">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="e9000-123">È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="e9000-123">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="e9000-124">Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="e9000-124">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="e9000-125">Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="e9000-125">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="e9000-126">Impostare la directory corrente sulla sottodirectory *csharp8* per il repository *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="e9000-126">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="e9000-127">Eseguire `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="e9000-127">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="e9000-128">Membri di sola lettura</span><span class="sxs-lookup"><span data-stu-id="e9000-128">Readonly members</span></span>

<span data-ttu-id="e9000-129">È possibile applicare il modificatore `readonly` a qualsiasi membro di uno struct.</span><span class="sxs-lookup"><span data-stu-id="e9000-129">You can apply the `readonly` modifier to any member of a struct.</span></span> <span data-ttu-id="e9000-130">Indica che il membro non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="e9000-130">It indicates that the member does not modify state.</span></span> <span data-ttu-id="e9000-131">È più granulare rispetto all'applicazione del modificatore `readonly` a una dichiarazione `struct`.</span><span class="sxs-lookup"><span data-stu-id="e9000-131">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="e9000-132">Considerare lo struct modificabile seguente:</span><span class="sxs-lookup"><span data-stu-id="e9000-132">Consider the following mutable struct:</span></span>

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

<span data-ttu-id="e9000-133">Come la maggior parte degli struct, il metodo `ToString()` non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="e9000-133">Like most structs, the `ToString()` method does not modify state.</span></span> <span data-ttu-id="e9000-134">Si potrebbe indicare questa condizione aggiungendo il modificatore `readonly` alla dichiarazione di `ToString()`:</span><span class="sxs-lookup"><span data-stu-id="e9000-134">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="e9000-135">La modifica precedente genera un avviso del compilatore, poiché `ToString` accede alla proprietà `Distance`, che non è contrassegnata come `readonly`:</span><span class="sxs-lookup"><span data-stu-id="e9000-135">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which is not marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="e9000-136">Il compilatore genera un avviso quando deve creare una copia difensiva.</span><span class="sxs-lookup"><span data-stu-id="e9000-136">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="e9000-137">La proprietà `Distance` non modifica lo stato, pertanto è possibile correggere il problema aggiungendo il modificatore `readonly` alla dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="e9000-137">The `Distance` property does not change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="e9000-138">Si noti che il modificatore `readonly` è necessario per una proprietà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e9000-138">Notice that the `readonly` modifier is necessary on a read only property.</span></span> <span data-ttu-id="e9000-139">Il compilatore non presume che le funzioni di accesso `get` non modifichino lo stato. È necessario dichiarare `readonly` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e9000-139">The compiler doesn't assume `get` accessors do not modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="e9000-140">Il compilatore applica la regola che i membri `readonly` non modificano lo stato.</span><span class="sxs-lookup"><span data-stu-id="e9000-140">The compiler does enforce the rule that `readonly` members do not modify state.</span></span> <span data-ttu-id="e9000-141">Il metodo seguente non verrà compilato a meno che non si rimuova il modificatore `readonly`:</span><span class="sxs-lookup"><span data-stu-id="e9000-141">The following method will not compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="e9000-142">Questa funzionalità consente di specificare la finalità della progettazione in modo che il compilatore possa imporla e applicare le ottimizzazioni in base a tale finalità.</span><span class="sxs-lookup"><span data-stu-id="e9000-142">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

## <a name="default-interface-members"></a><span data-ttu-id="e9000-143">Membri di interfaccia predefiniti</span><span class="sxs-lookup"><span data-stu-id="e9000-143">Default interface members</span></span>

<span data-ttu-id="e9000-144">È ora possibile aggiungere membri alle interfacce e fornire un'implementazione per tali membri.</span><span class="sxs-lookup"><span data-stu-id="e9000-144">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="e9000-145">Questa funzionalità del linguaggio consente agli autori di API di aggiungere metodi a un'interfaccia nelle versioni più recenti senza compromettere l'origine o la compatibilità binaria con le implementazioni esistenti di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e9000-145">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="e9000-146">Le implementazioni esistenti *ereditano* l'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e9000-146">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="e9000-147">Questa funzionalità supporta anche l'interoperabilità di C# con API destinate ad Android o Swift, che supporta funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="e9000-147">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="e9000-148">I membri di interfaccia predefiniti abilitano anche scenari simili alla funzionalità del linguaggio "tratti".</span><span class="sxs-lookup"><span data-stu-id="e9000-148">Default interface members also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="e9000-149">I membri di interfaccia predefiniti hanno effetti su molti scenari ed elementi del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e9000-149">Default interface members affects many scenarios and language elements.</span></span> <span data-ttu-id="e9000-150">La prima esercitazione illustra l'[aggiornamento di un'interfaccia con le implementazioni predefinite](../tutorials/default-interface-members-versions.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-150">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-members-versions.md).</span></span> <span data-ttu-id="e9000-151">Sono previsti altre esercitazioni e aggiornamenti dei riferimenti in tempo per il rilascio generale.</span><span class="sxs-lookup"><span data-stu-id="e9000-151">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="e9000-152">Più criteri in più posizioni</span><span class="sxs-lookup"><span data-stu-id="e9000-152">More patterns in more places</span></span>

<span data-ttu-id="e9000-153">I **criteri di ricerca** offrono strumenti per fornire funzionalità dipendenti dalla forma su tipi di dati correlati ma diversi.</span><span class="sxs-lookup"><span data-stu-id="e9000-153">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="e9000-154">In C# 7.0 è stata introdotta la sintassi per i criteri di tipi e i criteri di costanti, tramite l'espressione [`is`](../language-reference/keywords/is.md) e l'istruzione [`switch`](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-154">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="e9000-155">Queste funzionalità rappresentano il primo passo per il supporto dei paradigmi di programmazione in cui i dati e la funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="e9000-155">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="e9000-156">Man mano che il settore effettua la transizione verso più microservizi e altre architetture basate sul cloud, diventano necessari altri strumenti del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e9000-156">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="e9000-157">C# 8.0 espande questo vocabolario, in modo da poter usare più espressioni di criteri in più posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="e9000-157">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="e9000-158">Prendere in considerazione queste funzionalità quando i dati e le funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="e9000-158">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="e9000-159">Prendere in considerazione i criteri di ricerca quando gli algoritmi dipendono da un fatto diverso dal tipo di runtime di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="e9000-159">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="e9000-160">Queste tecniche offrono un altro modo per esprimere le progettazioni.</span><span class="sxs-lookup"><span data-stu-id="e9000-160">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="e9000-161">Oltre ai nuovi criteri disponibili in nuove posizioni, C# 8.0 introduce i **criteri ricorsivi**.</span><span class="sxs-lookup"><span data-stu-id="e9000-161">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="e9000-162">Il risultato di qualsiasi espressione di criteri è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e9000-162">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="e9000-163">Un criterio ricorsivo è semplicemente un'espressione di criteri applicata all'output di un'altra espressione di criteri.</span><span class="sxs-lookup"><span data-stu-id="e9000-163">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="e9000-164">Espressioni switch</span><span class="sxs-lookup"><span data-stu-id="e9000-164">switch expressions</span></span>

<span data-ttu-id="e9000-165">Spesso, un'istruzione [`switch`](../language-reference/keywords/switch.md) produce un valore in ognuno dei relativi blocchi `case`.</span><span class="sxs-lookup"><span data-stu-id="e9000-165">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="e9000-166">Le **espressioni switch** consentono di usare una sintassi più concisa per le espressioni</span><span class="sxs-lookup"><span data-stu-id="e9000-166">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="e9000-167">con meno parole chiave `case` e `break` ripetitive e un numero inferiore di parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="e9000-167">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="e9000-168">Ad esempio, si consideri l'enumerazione seguente che elenca i colori dell'arcobaleno:</span><span class="sxs-lookup"><span data-stu-id="e9000-168">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

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

<span data-ttu-id="e9000-169">Se l'applicazione ha definito un tipo `RGBColor` costituito dai componenti `R`, `G` e `B`, è possibile convertire un valore `Rainbow` nei relativi valori RGB usando il metodo seguente che contiene un'espressione switch:</span><span class="sxs-lookup"><span data-stu-id="e9000-169">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

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

<span data-ttu-id="e9000-170">Questo esempio include numerosi miglioramenti della sintassi:</span><span class="sxs-lookup"><span data-stu-id="e9000-170">There are several syntax improvements here:</span></span>

- <span data-ttu-id="e9000-171">La variabile precede la parola chiave `switch`.</span><span class="sxs-lookup"><span data-stu-id="e9000-171">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="e9000-172">L'ordine diverso rende più semplice distinguere visivamente l'espressione switch dall'istruzione switch.</span><span class="sxs-lookup"><span data-stu-id="e9000-172">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="e9000-173">Gli elementi `case` e `:` vengono sostituiti con `=>`.</span><span class="sxs-lookup"><span data-stu-id="e9000-173">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="e9000-174">È più conciso e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="e9000-174">It's more concise and intuitive.</span></span>
- <span data-ttu-id="e9000-175">Il caso `default` è sostituito con un discard `_`.</span><span class="sxs-lookup"><span data-stu-id="e9000-175">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="e9000-176">I corpi sono espressioni e non istruzioni.</span><span class="sxs-lookup"><span data-stu-id="e9000-176">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="e9000-177">Confrontare questo codice con quello equivalente che usa l'istruzione `switch` classica:</span><span class="sxs-lookup"><span data-stu-id="e9000-177">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

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

### <a name="property-patterns"></a><span data-ttu-id="e9000-178">Criteri per le proprietà</span><span class="sxs-lookup"><span data-stu-id="e9000-178">Property patterns</span></span>

<span data-ttu-id="e9000-179">I **criteri per le proprietà** consentono di individuare corrispondenze in base alle proprietà dell'oggetto esaminato.</span><span class="sxs-lookup"><span data-stu-id="e9000-179">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="e9000-180">Si consideri un sito di e-commerce che deve calcolare le imposte sulle vendite in base all'indirizzo dell'acquirente.</span><span class="sxs-lookup"><span data-stu-id="e9000-180">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="e9000-181">Questo calcolo non è una delle responsabilità principali di una classe `Address`.</span><span class="sxs-lookup"><span data-stu-id="e9000-181">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="e9000-182">È soggetto a variazioni nel tempo, probabilmente più spesso rispetto a eventuali modifiche del formato dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e9000-182">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="e9000-183">L'importo delle imposte sulle vendite dipende dalla proprietà `State` dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e9000-183">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="e9000-184">Il metodo seguente usa i criteri per le proprietà per calcolare l'imposta sulle vendite dall'indirizzo e dal prezzo:</span><span class="sxs-lookup"><span data-stu-id="e9000-184">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

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

<span data-ttu-id="e9000-185">I criteri di ricerca creano una sintassi concisa per esprimere questo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e9000-185">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="e9000-186">Criteri per le tuple</span><span class="sxs-lookup"><span data-stu-id="e9000-186">Tuple patterns</span></span>

<span data-ttu-id="e9000-187">Alcuni algoritmi dipendono da più input.</span><span class="sxs-lookup"><span data-stu-id="e9000-187">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="e9000-188">I **criteri per le tuple** consentono di passare da un valore a un altro, espressi come [tupla](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-188">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="e9000-189">Il codice seguente illustra un'espressione switch per il gioco *rock, paper, scissors* (carta-forbice-sasso):</span><span class="sxs-lookup"><span data-stu-id="e9000-189">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

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

<span data-ttu-id="e9000-190">I messaggi indicano il vincitore.</span><span class="sxs-lookup"><span data-stu-id="e9000-190">The messages indicate the winner.</span></span> <span data-ttu-id="e9000-191">Il caso discard rappresenta le tre combinazioni di valori equivalenti o altri input di testo.</span><span class="sxs-lookup"><span data-stu-id="e9000-191">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="e9000-192">Criteri per la posizione</span><span class="sxs-lookup"><span data-stu-id="e9000-192">Positional patterns</span></span>

<span data-ttu-id="e9000-193">Alcuni tipi includono un metodo `Deconstruct` che decostruisce le proprietà in variabili discrete.</span><span class="sxs-lookup"><span data-stu-id="e9000-193">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="e9000-194">Quando un metodo `Deconstruct` è accessibile, è possibile usare i **criteri per la posizione** per esaminare le proprietà dell'oggetto e usare tali proprietà per un criterio.</span><span class="sxs-lookup"><span data-stu-id="e9000-194">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="e9000-195">Considerare la classe `Point` seguente che include un metodo `Deconstruct` per creare variabili discrete per `X` e `Y`:</span><span class="sxs-lookup"><span data-stu-id="e9000-195">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

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

<span data-ttu-id="e9000-196">Considerare anche l'enumerazione seguente, che rappresenta posizioni diverse in un quadrante:</span><span class="sxs-lookup"><span data-stu-id="e9000-196">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

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

<span data-ttu-id="e9000-197">Il metodo seguente usa i **criteri per la posizione** per estrarre i valori di `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="e9000-197">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="e9000-198">Quindi usa una clausola `when` per determinare l'elemento `Quadrant` del punto:</span><span class="sxs-lookup"><span data-stu-id="e9000-198">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

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

<span data-ttu-id="e9000-199">I criteri discard nell'espressione switch precedente trovano una corrispondenza quando `x` o `y` è uguale a 0, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="e9000-199">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="e9000-200">Un'espressione switch deve produrre un valore o generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9000-200">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="e9000-201">Se nessuno dei casi corrisponde, l'espressione switch genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e9000-201">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="e9000-202">Il compilatore genera un avviso per l'utente se non è possibile includere tutti i casi possibili nell'espressione switch.</span><span class="sxs-lookup"><span data-stu-id="e9000-202">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="e9000-203">È possibile esplorare le tecniche dei criteri di ricerca in questa [esercitazione avanzata sui criteri di ricerca](../tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-203">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="e9000-204">Dichiarazioni using</span><span class="sxs-lookup"><span data-stu-id="e9000-204">using declarations</span></span>

<span data-ttu-id="e9000-205">Una **dichiarazione using** è una dichiarazione di variabile preceduta dalla parola chiave `using`.</span><span class="sxs-lookup"><span data-stu-id="e9000-205">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="e9000-206">Indica al compilatore che la variabile dichiarata deve essere eliminata alla fine dell'ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="e9000-206">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="e9000-207">Ad esempio, si consideri il codice seguente che consente di scrivere un file di testo:</span><span class="sxs-lookup"><span data-stu-id="e9000-207">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="e9000-208">Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura per il metodo.</span><span class="sxs-lookup"><span data-stu-id="e9000-208">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="e9000-209">Questa è la fine dell'ambito in cui viene dichiarato `file`.</span><span class="sxs-lookup"><span data-stu-id="e9000-209">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="e9000-210">Il codice precedente è equivalente al codice seguente con l'[istruzione using](../language-reference/keywords/using-statement.md) classica:</span><span class="sxs-lookup"><span data-stu-id="e9000-210">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="e9000-211">Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura associata all'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="e9000-211">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="e9000-212">In entrambi i casi, il compilatore genera la chiamata a `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="e9000-212">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="e9000-213">Il compilatore genera un errore se l'espressione nell'istruzione `using` non è eliminabile.</span><span class="sxs-lookup"><span data-stu-id="e9000-213">The compiler generates an error if the expression in the `using` statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="e9000-214">Funzioni locali statiche</span><span class="sxs-lookup"><span data-stu-id="e9000-214">Static local functions</span></span>

<span data-ttu-id="e9000-215">È ora possibile aggiungere il modificatore `static` alle funzioni locali per assicurarsi che tale funzione locale non acquisisca (faccia riferimento a) variabili dall'ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="e9000-215">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="e9000-216">In questo modo viene generato l'errore `CS8421` "A static local function can't contain a reference to \<variable>" (Una funzione locale statica non può fare riferimento a <variabile>).</span><span class="sxs-lookup"><span data-stu-id="e9000-216">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="e9000-217">Si consideri il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e9000-217">Consider the following code.</span></span> <span data-ttu-id="e9000-218">La funzione locale `LocalFunction` accede alla variabile `y`, dichiarata nell'ambito di inclusione (il metodo `M`).</span><span class="sxs-lookup"><span data-stu-id="e9000-218">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="e9000-219">Pertanto, non è possibile dichiarare `LocalFunction` con il modificatore `static`:</span><span class="sxs-lookup"><span data-stu-id="e9000-219">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="e9000-220">Il codice seguente contiene una funzione locale statica.</span><span class="sxs-lookup"><span data-stu-id="e9000-220">The following code contains a static local function.</span></span> <span data-ttu-id="e9000-221">Può essere statica perché non accede ad alcuna variabile nell'ambito di inclusione:</span><span class="sxs-lookup"><span data-stu-id="e9000-221">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="e9000-222">Struct ref Disposable</span><span class="sxs-lookup"><span data-stu-id="e9000-222">Disposable ref structs</span></span>

<span data-ttu-id="e9000-223">Un oggetto `struct` dichiarato con il modificatore `ref` potrebbe non implementare alcuna interfaccia e quindi non può implementare <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="e9000-223">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="e9000-224">Pertanto, per abilitare un `ref struct` per l'eliminazione, deve avere un metodo `void Dispose()` accessibile.</span><span class="sxs-lookup"><span data-stu-id="e9000-224">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="e9000-225">Questo vale anche per le dichiarazioni `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="e9000-225">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="e9000-226">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="e9000-226">Nullable reference types</span></span>

<span data-ttu-id="e9000-227">All'interno di un contesto delle annotazioni nullable, qualsiasi variabile di un tipo riferimento viene considerata come un **tipo riferimento non nullable**.</span><span class="sxs-lookup"><span data-stu-id="e9000-227">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="e9000-228">Se si vuole indicare che una variabile può essere Null, è necessario aggiungere `?` al nome del tipo per dichiarare la variabile come un **tipo riferimento nullable**.</span><span class="sxs-lookup"><span data-stu-id="e9000-228">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="e9000-229">Per i tipi riferimento non nullable, il compilatore usa l'analisi di flusso per garantire che le variabili locali vengano inizializzate su un valore diverso da Null al momento della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e9000-229">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="e9000-230">I campi devono essere inizializzati durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="e9000-230">Fields must be initialized during construction.</span></span> <span data-ttu-id="e9000-231">Il compilatore genera un avviso se la variabile non è impostata da una chiamata a uno qualsiasi dei costruttori disponibili o da un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="e9000-231">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="e9000-232">Inoltre, non è possibile assegnare ai tipi riferimento non nullable un valore che potrebbe essere Null.</span><span class="sxs-lookup"><span data-stu-id="e9000-232">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="e9000-233">I tipi riferimento nullable non vengono controllati per verificare che non vengano assegnati o inizializzati su Null.</span><span class="sxs-lookup"><span data-stu-id="e9000-233">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="e9000-234">Tuttavia, il compilatore usa l'analisi di flusso per garantire che qualsiasi variabile di un tipo riferimento nullable venga controllata per i valori Null prima dell'accesso o prima che venga assegnata a un tipo riferimento non nullable.</span><span class="sxs-lookup"><span data-stu-id="e9000-234">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="e9000-235">Altre informazioni su questa funzionalità sono disponibili nella panoramica dei [tipi riferimento nullable](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-235">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="e9000-236">È possibile provare in autonomia in una nuova applicazione in questa [esercitazione sui tipi riferimento nullable](../tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-236">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="e9000-237">Per informazioni sulla procedura per eseguire la migrazione di una base di codice esistente per l'uso dei tipi riferimento nullable, vedere l'[esercitazione sulla migrazione di un'applicazione per l'uso dei tipi riferimento nullable](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-237">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="e9000-238">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="e9000-238">Asynchronous streams</span></span>

<span data-ttu-id="e9000-239">A partire da C# 8.0, è possibile creare e utilizzare i flussi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e9000-239">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="e9000-240">Un metodo che restituisce un flusso asincrono ha tre proprietà:</span><span class="sxs-lookup"><span data-stu-id="e9000-240">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="e9000-241">È stato dichiarato con il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="e9000-241">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="e9000-242">Restituisce <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e9000-242">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="e9000-243">Il metodo contiene istruzioni `yield return` per restituire gli elementi successivi nel flusso asincrono.</span><span class="sxs-lookup"><span data-stu-id="e9000-243">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="e9000-244">Per utilizzare un flusso asincrono, è necessario aggiungere la parola chiave `await` prima della parola chiave `foreach` quando si enumerano gli elementi del flusso.</span><span class="sxs-lookup"><span data-stu-id="e9000-244">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="e9000-245">Per l'aggiunta della parola chiave `await`, il metodo che enumera il flusso asincrono deve essere dichiarato con il modificatore `async` e restituire un tipo consentito per un metodo `async`.</span><span class="sxs-lookup"><span data-stu-id="e9000-245">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="e9000-246">In genere ciò significa restituire <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e9000-246">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e9000-247">Può anche essere <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="e9000-247">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="e9000-248">Un metodo può sia utilizzare che produrre un flusso asincrono, il che significa che restituirebbe <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e9000-248">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="e9000-249">Il codice seguente genera una sequenza da 0 a 19, con un'attesa di 100 ms tra la generazione di ogni numero:</span><span class="sxs-lookup"><span data-stu-id="e9000-249">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

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

<span data-ttu-id="e9000-250">La sequenza viene enumerata usando l'istruzione `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="e9000-250">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="e9000-251">È possibile provare i flussi asincroni in autonomia nell'esercitazione dedicata alla [creazione e all'utilizzo di flussi asincroni](../tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-251">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="e9000-252">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="e9000-252">Indices and ranges</span></span>

<span data-ttu-id="e9000-253">Gli intervalli e gli indici offrono una sintassi concisa per la specifica di intervalli secondari in una matrice, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="e9000-253">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="e9000-254">Questo supporto per il linguaggio si basa su due nuovi tipi e due nuovi operatori:</span><span class="sxs-lookup"><span data-stu-id="e9000-254">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="e9000-255"><xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="e9000-255"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="e9000-256">L'operatore `^`, che specifica che un indice è relativo alla fine della sequenza.</span><span class="sxs-lookup"><span data-stu-id="e9000-256">The `^` operator, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="e9000-257"><xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="e9000-257"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="e9000-258">L'operatore Range (`..`), che specifica l'inizio e fine di un intervallo come operandi.</span><span class="sxs-lookup"><span data-stu-id="e9000-258">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="e9000-259">Per iniziare, ecco come funzionano le regole per gli indici.</span><span class="sxs-lookup"><span data-stu-id="e9000-259">Let's start with the rules for indexes.</span></span> <span data-ttu-id="e9000-260">Prendere in considerazione una matrice `sequence`.</span><span class="sxs-lookup"><span data-stu-id="e9000-260">Consider an array `sequence`.</span></span> <span data-ttu-id="e9000-261">L'indice `0` è uguale a `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="e9000-261">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="e9000-262">L'indice `^0` è uguale a `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="e9000-262">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="e9000-263">Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="e9000-263">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="e9000-264">Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="e9000-264">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="e9000-265">Un intervallo specifica *inizio* e *fine* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="e9000-265">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="e9000-266">L'inizio dell'intervallo è inclusivo, ma la fine dell'intervallo è esclusiva, vale a dire che l'*inizio* è compreso nell'intervallo, mentre la *fine* non lo è.</span><span class="sxs-lookup"><span data-stu-id="e9000-266">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* is not included in the range.</span></span> <span data-ttu-id="e9000-267">L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.</span><span class="sxs-lookup"><span data-stu-id="e9000-267">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="e9000-268">Di seguito verranno esaminati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="e9000-268">Let's look at a few examples.</span></span> <span data-ttu-id="e9000-269">Si consideri la matrice seguente, annotata con il relativo indice dall'inizio e dalla fine:</span><span class="sxs-lookup"><span data-stu-id="e9000-269">Consider the following array, annotated with its index from the start and from the end:</span></span>

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

<span data-ttu-id="e9000-270">È possibile recuperare l'ultima parola con l'indice `^1`:</span><span class="sxs-lookup"><span data-stu-id="e9000-270">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="e9000-271">Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox".</span><span class="sxs-lookup"><span data-stu-id="e9000-271">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="e9000-272">Include da `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="e9000-272">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="e9000-273">L'elemento `words[4]` non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e9000-273">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="e9000-274">Il codice seguente crea un intervallo secondario con "lazy" e "dog".</span><span class="sxs-lookup"><span data-stu-id="e9000-274">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="e9000-275">Include `words[^2]` e `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="e9000-275">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="e9000-276">L'indice finale `words[^0]` non viene incluso:</span><span class="sxs-lookup"><span data-stu-id="e9000-276">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="e9000-277">Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:</span><span class="sxs-lookup"><span data-stu-id="e9000-277">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="e9000-278">È anche possibile dichiarare gli intervalli come variabili:</span><span class="sxs-lookup"><span data-stu-id="e9000-278">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="e9000-279">L'intervallo può quindi essere usato all'interno dei caratteri `[` e `]`:</span><span class="sxs-lookup"><span data-stu-id="e9000-279">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="e9000-280">È possibile ottenere maggiori informazioni su indici e intervalli nell'esercitazione [Indici e intervalli](../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-280">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="e9000-281">Miglioramento delle stringhe verbatim interpolate</span><span class="sxs-lookup"><span data-stu-id="e9000-281">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="e9000-282">L' `$` ordine dei token `@` e nelle stringhe verbatim [interpolate](../language-reference/tokens/interpolated.md) può essere any: sia `$@"..."` che `@$"..."` sono stringhe verbatim interpolate valide.</span><span class="sxs-lookup"><span data-stu-id="e9000-282">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="e9000-283">Nelle versioni C# precedenti il `$` token deve essere visualizzato prima del `@` token.</span><span class="sxs-lookup"><span data-stu-id="e9000-283">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
