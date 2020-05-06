---
title: Novità di C# 8,0-Guida a C#
description: Panoramica delle nuove funzionalità disponibili in C# 8.0.
ms.date: 04/07/2020
ms.openlocfilehash: 8935660d175cc3ee404ee374e3a58fc47d283771
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794572"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="78e9b-103">Novità di C# 8.0</span><span class="sxs-lookup"><span data-stu-id="78e9b-103">What's new in C# 8.0</span></span>

<span data-ttu-id="78e9b-104">C# 8,0 aggiunge le funzionalità e i miglioramenti seguenti al linguaggio C#:</span><span class="sxs-lookup"><span data-stu-id="78e9b-104">C# 8.0 adds the following features and enhancements to the C# language:</span></span>

- [<span data-ttu-id="78e9b-105">Membri di sola lettura</span><span class="sxs-lookup"><span data-stu-id="78e9b-105">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="78e9b-106">Metodi di interfaccia predefiniti</span><span class="sxs-lookup"><span data-stu-id="78e9b-106">Default interface methods</span></span>](#default-interface-methods)
- <span data-ttu-id="78e9b-107">[Miglioramenti dei criteri di ricerca](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="78e9b-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="78e9b-108">Espressioni switch</span><span class="sxs-lookup"><span data-stu-id="78e9b-108">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="78e9b-109">Criteri per le proprietà</span><span class="sxs-lookup"><span data-stu-id="78e9b-109">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="78e9b-110">Criteri per le tuple</span><span class="sxs-lookup"><span data-stu-id="78e9b-110">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="78e9b-111">Criteri per la posizione</span><span class="sxs-lookup"><span data-stu-id="78e9b-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="78e9b-112">Utilizzo di dichiarazioni</span><span class="sxs-lookup"><span data-stu-id="78e9b-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="78e9b-113">Funzioni locali statiche</span><span class="sxs-lookup"><span data-stu-id="78e9b-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="78e9b-114">Struct ref Disposable</span><span class="sxs-lookup"><span data-stu-id="78e9b-114">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="78e9b-115">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="78e9b-115">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="78e9b-116">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="78e9b-116">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="78e9b-117">Monouso asincrono</span><span class="sxs-lookup"><span data-stu-id="78e9b-117">Asynchronous disposable</span></span>](#asynchronous-disposable)
- [<span data-ttu-id="78e9b-118">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="78e9b-118">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="78e9b-119">Assegnazione di Unione null</span><span class="sxs-lookup"><span data-stu-id="78e9b-119">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="78e9b-120">Tipi costruiti non gestiti</span><span class="sxs-lookup"><span data-stu-id="78e9b-120">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="78e9b-121">Stackalloc nelle espressioni annidate</span><span class="sxs-lookup"><span data-stu-id="78e9b-121">Stackalloc in nested expressions</span></span>](#stackalloc-in-nested-expressions)
- [<span data-ttu-id="78e9b-122">Miglioramento delle stringhe verbatim interpolate</span><span class="sxs-lookup"><span data-stu-id="78e9b-122">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

<span data-ttu-id="78e9b-123">C# 8,0 è supportato in **.NET Core 3. x** e **.NET standard 2,1**.</span><span class="sxs-lookup"><span data-stu-id="78e9b-123">C# 8.0 is supported on **.NET Core 3.x** and **.NET Standard 2.1**.</span></span> <span data-ttu-id="78e9b-124">Per ulteriori informazioni, vedere [controllo delle versioni del linguaggio C#](../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-124">For more information, see [C# language versioning](../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="78e9b-125">Il resto di questo articolo descrive brevemente queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="78e9b-125">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="78e9b-126">Se sono disponibili articoli approfonditi, vengono forniti collegamenti a queste panoramiche ed esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="78e9b-126">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="78e9b-127">È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-127">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="78e9b-128">Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="78e9b-128">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="78e9b-129">Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="78e9b-129">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="78e9b-130">Impostare la directory corrente sulla sottodirectory *csharp8* per il repository *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="78e9b-130">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="78e9b-131">Eseguire `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-131">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="78e9b-132">Membri di sola lettura</span><span class="sxs-lookup"><span data-stu-id="78e9b-132">Readonly members</span></span>

<span data-ttu-id="78e9b-133">È possibile applicare il `readonly` modificatore ai membri di uno struct.</span><span class="sxs-lookup"><span data-stu-id="78e9b-133">You can apply the `readonly` modifier to members of a struct.</span></span> <span data-ttu-id="78e9b-134">Indica che il membro non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="78e9b-134">It indicates that the member doesn't modify state.</span></span> <span data-ttu-id="78e9b-135">È più granulare rispetto all'applicazione del modificatore `readonly` a una dichiarazione `struct`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-135">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="78e9b-136">Considerare lo struct modificabile seguente:</span><span class="sxs-lookup"><span data-stu-id="78e9b-136">Consider the following mutable struct:</span></span>

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

<span data-ttu-id="78e9b-137">Come la maggior parte degli struct `ToString()` , il metodo non modifica lo stato.</span><span class="sxs-lookup"><span data-stu-id="78e9b-137">Like most structs, the `ToString()` method doesn't modify state.</span></span> <span data-ttu-id="78e9b-138">Si potrebbe indicare questa condizione aggiungendo il modificatore `readonly` alla dichiarazione di `ToString()`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-138">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="78e9b-139">La modifica precedente genera un avviso del compilatore, `ToString` perché accede alla `Distance` proprietà, che non è `readonly`contrassegnata come:</span><span class="sxs-lookup"><span data-stu-id="78e9b-139">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which isn't marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="78e9b-140">Il compilatore genera un avviso quando deve creare una copia difensiva.</span><span class="sxs-lookup"><span data-stu-id="78e9b-140">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="78e9b-141">La `Distance` proprietà non modifica lo stato, quindi è possibile correggere questo avviso aggiungendo il `readonly` modificatore alla dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="78e9b-141">The `Distance` property doesn't change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="78e9b-142">Si noti che `readonly` il modificatore è necessario in una proprietà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="78e9b-142">Notice that the `readonly` modifier is necessary on a read-only property.</span></span> <span data-ttu-id="78e9b-143">Il compilatore non presuppone `get` che le funzioni di accesso non modifichino lo stato; è necessario dichiarare `readonly` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="78e9b-143">The compiler doesn't assume `get` accessors don't modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="78e9b-144">Le proprietà implementate automaticamente sono un'eccezione. il compilatore considererà tutti i Getter implementati automaticamente come `readonly`, quindi non è necessario aggiungere il `readonly` modificatore alle proprietà `X` e. `Y`</span><span class="sxs-lookup"><span data-stu-id="78e9b-144">Auto-implemented properties are an exception; the compiler will treat all auto-implemented getters as `readonly`, so here there's no need to add the `readonly` modifier to the `X` and `Y` properties.</span></span>

<span data-ttu-id="78e9b-145">Il compilatore applica la regola che `readonly` i membri non modificano lo stato.</span><span class="sxs-lookup"><span data-stu-id="78e9b-145">The compiler does enforce the rule that `readonly` members don't modify state.</span></span> <span data-ttu-id="78e9b-146">Il metodo seguente non verrà compilato a meno che non `readonly` si rimuova il modificatore:</span><span class="sxs-lookup"><span data-stu-id="78e9b-146">The following method won't compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="78e9b-147">Questa funzionalità consente di specificare la finalità della progettazione in modo che il compilatore possa imporla e applicare le ottimizzazioni in base a tale finalità.</span><span class="sxs-lookup"><span data-stu-id="78e9b-147">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

<span data-ttu-id="78e9b-148">Per ulteriori informazioni, vedere la [ `readonly` sezione membri di istanza](../language-reference/builtin-types/struct.md#readonly-instance-members) dell'articolo [tipi di struttura](../language-reference/builtin-types/struct.md) .</span><span class="sxs-lookup"><span data-stu-id="78e9b-148">For more information, see the [`readonly` instance members](../language-reference/builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../language-reference/builtin-types/struct.md) article.</span></span>

## <a name="default-interface-methods"></a><span data-ttu-id="78e9b-149">Metodi di interfaccia predefiniti</span><span class="sxs-lookup"><span data-stu-id="78e9b-149">Default interface methods</span></span>

<span data-ttu-id="78e9b-150">È ora possibile aggiungere membri alle interfacce e fornire un'implementazione per tali membri.</span><span class="sxs-lookup"><span data-stu-id="78e9b-150">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="78e9b-151">Questa funzionalità del linguaggio consente agli autori di API di aggiungere metodi a un'interfaccia nelle versioni più recenti senza compromettere l'origine o la compatibilità binaria con le implementazioni esistenti di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="78e9b-151">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="78e9b-152">Le implementazioni esistenti *ereditano* l'implementazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="78e9b-152">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="78e9b-153">Questa funzionalità supporta anche l'interoperabilità di C# con API destinate ad Android o Swift, che supporta funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="78e9b-153">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="78e9b-154">I metodi di interfaccia predefiniti consentono inoltre scenari simili alla funzionalità del linguaggio "tratti".</span><span class="sxs-lookup"><span data-stu-id="78e9b-154">Default interface methods also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="78e9b-155">I metodi di interfaccia predefiniti interessano molti scenari ed elementi del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="78e9b-155">Default interface methods affect many scenarios and language elements.</span></span> <span data-ttu-id="78e9b-156">La prima esercitazione illustra l'[aggiornamento di un'interfaccia con le implementazioni predefinite](../tutorials/default-interface-methods-versions.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-156">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-methods-versions.md).</span></span> <span data-ttu-id="78e9b-157">Sono previsti altre esercitazioni e aggiornamenti dei riferimenti in tempo per il rilascio generale.</span><span class="sxs-lookup"><span data-stu-id="78e9b-157">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="78e9b-158">Più criteri in più posizioni</span><span class="sxs-lookup"><span data-stu-id="78e9b-158">More patterns in more places</span></span>

<span data-ttu-id="78e9b-159">I **criteri di ricerca** offrono strumenti per fornire funzionalità dipendenti dalla forma su tipi di dati correlati ma diversi.</span><span class="sxs-lookup"><span data-stu-id="78e9b-159">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="78e9b-160">In C# 7,0 è stata introdotta la sintassi per i modelli di [`is`](../language-reference/keywords/is.md) tipo e costanti [`switch`](../language-reference/keywords/switch.md) usando l'espressione e l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-160">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="78e9b-161">Queste funzionalità rappresentano il primo passo per il supporto dei paradigmi di programmazione in cui i dati e la funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="78e9b-161">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="78e9b-162">Man mano che il settore effettua la transizione verso più microservizi e altre architetture basate sul cloud, diventano necessari altri strumenti del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="78e9b-162">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="78e9b-163">C# 8.0 espande questo vocabolario, in modo da poter usare più espressioni di criteri in più posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="78e9b-163">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="78e9b-164">Prendere in considerazione queste funzionalità quando i dati e le funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="78e9b-164">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="78e9b-165">Prendere in considerazione i criteri di ricerca quando gli algoritmi dipendono da un fatto diverso dal tipo di runtime di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="78e9b-165">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="78e9b-166">Queste tecniche offrono un altro modo per esprimere le progettazioni.</span><span class="sxs-lookup"><span data-stu-id="78e9b-166">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="78e9b-167">Oltre ai nuovi criteri disponibili in nuove posizioni, C# 8.0 introduce i **criteri ricorsivi**.</span><span class="sxs-lookup"><span data-stu-id="78e9b-167">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="78e9b-168">Il risultato di qualsiasi espressione di criteri è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-168">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="78e9b-169">Un criterio ricorsivo è semplicemente un'espressione di criteri applicata all'output di un'altra espressione di criteri.</span><span class="sxs-lookup"><span data-stu-id="78e9b-169">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="78e9b-170">Espressioni switch</span><span class="sxs-lookup"><span data-stu-id="78e9b-170">Switch expressions</span></span>

<span data-ttu-id="78e9b-171">Spesso un' [`switch`](../language-reference/keywords/switch.md) istruzione produce un valore in ogni `case` blocco.</span><span class="sxs-lookup"><span data-stu-id="78e9b-171">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="78e9b-172">Le **espressioni switch** consentono di usare una sintassi più concisa per le espressioni</span><span class="sxs-lookup"><span data-stu-id="78e9b-172">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="78e9b-173">con meno parole chiave `case` e `break` ripetitive e un numero inferiore di parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="78e9b-173">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="78e9b-174">Ad esempio, si consideri l'enumerazione seguente che elenca i colori dell'arcobaleno:</span><span class="sxs-lookup"><span data-stu-id="78e9b-174">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

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

<span data-ttu-id="78e9b-175">Se l'applicazione ha definito un tipo `RGBColor` costituito dai componenti `R`, `G` e `B`, è possibile convertire un valore `Rainbow` nei relativi valori RGB usando il metodo seguente che contiene un'espressione switch:</span><span class="sxs-lookup"><span data-stu-id="78e9b-175">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

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

<span data-ttu-id="78e9b-176">Questo esempio include numerosi miglioramenti della sintassi:</span><span class="sxs-lookup"><span data-stu-id="78e9b-176">There are several syntax improvements here:</span></span>

- <span data-ttu-id="78e9b-177">La variabile precede la parola chiave `switch`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-177">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="78e9b-178">L'ordine diverso rende più semplice distinguere visivamente l'espressione switch dall'istruzione switch.</span><span class="sxs-lookup"><span data-stu-id="78e9b-178">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="78e9b-179">Gli elementi `case` e `:` vengono sostituiti con `=>`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-179">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="78e9b-180">È più conciso e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-180">It's more concise and intuitive.</span></span>
- <span data-ttu-id="78e9b-181">Il caso `default` è sostituito con un discard `_`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-181">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="78e9b-182">I corpi sono espressioni e non istruzioni.</span><span class="sxs-lookup"><span data-stu-id="78e9b-182">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="78e9b-183">Confrontare questo codice con quello equivalente che usa l'istruzione `switch` classica:</span><span class="sxs-lookup"><span data-stu-id="78e9b-183">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

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

### <a name="property-patterns"></a><span data-ttu-id="78e9b-184">Criteri per le proprietà</span><span class="sxs-lookup"><span data-stu-id="78e9b-184">Property patterns</span></span>

<span data-ttu-id="78e9b-185">I **criteri per le proprietà** consentono di individuare corrispondenze in base alle proprietà dell'oggetto esaminato.</span><span class="sxs-lookup"><span data-stu-id="78e9b-185">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="78e9b-186">Si consideri un sito di e-commerce che deve calcolare le imposte sulle vendite in base all'indirizzo dell'acquirente.</span><span class="sxs-lookup"><span data-stu-id="78e9b-186">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="78e9b-187">Tale calcolo non è un compito fondamentale di `Address` una classe.</span><span class="sxs-lookup"><span data-stu-id="78e9b-187">That computation isn't a core responsibility of an `Address` class.</span></span> <span data-ttu-id="78e9b-188">È soggetto a variazioni nel tempo, probabilmente più spesso rispetto a eventuali modifiche del formato dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-188">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="78e9b-189">L'importo delle imposte sulle vendite dipende dalla proprietà `State` dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-189">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="78e9b-190">Il metodo seguente usa i criteri per le proprietà per calcolare l'imposta sulle vendite dall'indirizzo e dal prezzo:</span><span class="sxs-lookup"><span data-stu-id="78e9b-190">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

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

<span data-ttu-id="78e9b-191">I criteri di ricerca creano una sintassi concisa per esprimere questo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-191">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="78e9b-192">Criteri per le tuple</span><span class="sxs-lookup"><span data-stu-id="78e9b-192">Tuple patterns</span></span>

<span data-ttu-id="78e9b-193">Alcuni algoritmi dipendono da più input.</span><span class="sxs-lookup"><span data-stu-id="78e9b-193">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="78e9b-194">I **criteri per le tuple** consentono di passare da un valore a un altro, espressi come [tupla](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-194">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="78e9b-195">Il codice seguente illustra un'espressione switch per il gioco *rock, paper, scissors* (carta-forbice-sasso):</span><span class="sxs-lookup"><span data-stu-id="78e9b-195">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

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

<span data-ttu-id="78e9b-196">I messaggi indicano il vincitore.</span><span class="sxs-lookup"><span data-stu-id="78e9b-196">The messages indicate the winner.</span></span> <span data-ttu-id="78e9b-197">Il caso discard rappresenta le tre combinazioni di valori equivalenti o altri input di testo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-197">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="78e9b-198">Criteri per la posizione</span><span class="sxs-lookup"><span data-stu-id="78e9b-198">Positional patterns</span></span>

<span data-ttu-id="78e9b-199">Alcuni tipi includono un metodo `Deconstruct` che decostruisce le proprietà in variabili discrete.</span><span class="sxs-lookup"><span data-stu-id="78e9b-199">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="78e9b-200">Quando un metodo `Deconstruct` è accessibile, è possibile usare i **criteri per la posizione** per esaminare le proprietà dell'oggetto e usare tali proprietà per un criterio.</span><span class="sxs-lookup"><span data-stu-id="78e9b-200">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="78e9b-201">Considerare la classe `Point` seguente che include un metodo `Deconstruct` per creare variabili discrete per `X` e `Y`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-201">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

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

<span data-ttu-id="78e9b-202">Considerare anche l'enumerazione seguente, che rappresenta posizioni diverse in un quadrante:</span><span class="sxs-lookup"><span data-stu-id="78e9b-202">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

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

<span data-ttu-id="78e9b-203">Il metodo seguente usa i **criteri per la posizione** per estrarre i valori di `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-203">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="78e9b-204">Quindi usa una clausola `when` per determinare l'elemento `Quadrant` del punto:</span><span class="sxs-lookup"><span data-stu-id="78e9b-204">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

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

<span data-ttu-id="78e9b-205">I criteri discard nell'espressione switch precedente trovano una corrispondenza quando `x` o `y` è uguale a 0, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="78e9b-205">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="78e9b-206">Un'espressione switch deve produrre un valore o generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-206">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="78e9b-207">Se nessuno dei casi corrisponde, l'espressione switch genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-207">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="78e9b-208">Il compilatore genera un avviso se non si coprono tutti i casi possibili nell'espressione switch.</span><span class="sxs-lookup"><span data-stu-id="78e9b-208">The compiler generates a warning for you if you don't cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="78e9b-209">È possibile esplorare le tecniche dei criteri di ricerca in questa [esercitazione avanzata sui criteri di ricerca](../tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-209">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="78e9b-210">Dichiarazioni using</span><span class="sxs-lookup"><span data-stu-id="78e9b-210">Using declarations</span></span>

<span data-ttu-id="78e9b-211">Una **dichiarazione using** è una dichiarazione di variabile preceduta dalla parola chiave `using`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-211">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="78e9b-212">Indica al compilatore che la variabile dichiarata deve essere eliminata alla fine dell'ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-212">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="78e9b-213">Ad esempio, si consideri il codice seguente che consente di scrivere un file di testo:</span><span class="sxs-lookup"><span data-stu-id="78e9b-213">For example, consider the following code that writes a text file:</span></span>

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

<span data-ttu-id="78e9b-214">Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura per il metodo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-214">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="78e9b-215">Questa è la fine dell'ambito in cui viene dichiarato `file`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-215">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="78e9b-216">Il codice precedente è equivalente al codice seguente con l'[istruzione using](../language-reference/keywords/using-statement.md) classica:</span><span class="sxs-lookup"><span data-stu-id="78e9b-216">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

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

<span data-ttu-id="78e9b-217">Nell'esempio precedente il file viene eliminato quando viene raggiunta la parentesi graffa di chiusura associata all'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-217">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="78e9b-218">In entrambi i casi, il compilatore genera la chiamata a `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-218">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="78e9b-219">Il compilatore genera un errore se l'espressione nell' `using` istruzione non è Disposable.</span><span class="sxs-lookup"><span data-stu-id="78e9b-219">The compiler generates an error if the expression in the `using` statement isn't disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="78e9b-220">Funzioni locali statiche</span><span class="sxs-lookup"><span data-stu-id="78e9b-220">Static local functions</span></span>

<span data-ttu-id="78e9b-221">È ora possibile aggiungere il modificatore `static` alle funzioni locali per assicurarsi che tale funzione locale non acquisisca (faccia riferimento a) variabili dall'ambito di inclusione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-221">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="78e9b-222">In questo modo viene generato l'errore `CS8421` "A static local function can't contain a reference to \<variable>" (Una funzione locale statica non può fare riferimento a <variabile>).</span><span class="sxs-lookup"><span data-stu-id="78e9b-222">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span>

<span data-ttu-id="78e9b-223">Si consideri il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="78e9b-223">Consider the following code.</span></span> <span data-ttu-id="78e9b-224">La funzione locale `LocalFunction` accede alla variabile `y`, dichiarata nell'ambito di inclusione (il metodo `M`).</span><span class="sxs-lookup"><span data-stu-id="78e9b-224">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="78e9b-225">Pertanto, non è possibile dichiarare `LocalFunction` con il modificatore `static`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-225">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="78e9b-226">Il codice seguente contiene una funzione locale statica.</span><span class="sxs-lookup"><span data-stu-id="78e9b-226">The following code contains a static local function.</span></span> <span data-ttu-id="78e9b-227">Può essere statica perché non accede ad alcuna variabile nell'ambito di inclusione:</span><span class="sxs-lookup"><span data-stu-id="78e9b-227">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="78e9b-228">Struct ref Disposable</span><span class="sxs-lookup"><span data-stu-id="78e9b-228">Disposable ref structs</span></span>

<span data-ttu-id="78e9b-229">Una `struct` dichiarata `ref` con il modificatore non può implementare alcuna interfaccia e <xref:System.IDisposable>pertanto non può implementare.</span><span class="sxs-lookup"><span data-stu-id="78e9b-229">A `struct` declared with the `ref` modifier may not implement any interfaces and so can't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="78e9b-230">Pertanto, per abilitare un `ref struct` per l'eliminazione, deve avere un metodo `void Dispose()` accessibile.</span><span class="sxs-lookup"><span data-stu-id="78e9b-230">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="78e9b-231">Questa funzionalità si applica anche `readonly ref struct` alle dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="78e9b-231">This feature also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="78e9b-232">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="78e9b-232">Nullable reference types</span></span>

<span data-ttu-id="78e9b-233">All'interno di un contesto delle annotazioni nullable, qualsiasi variabile di un tipo riferimento viene considerata come un **tipo riferimento non nullable**.</span><span class="sxs-lookup"><span data-stu-id="78e9b-233">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="78e9b-234">Se si vuole indicare che una variabile può essere Null, è necessario aggiungere `?` al nome del tipo per dichiarare la variabile come un **tipo riferimento nullable**.</span><span class="sxs-lookup"><span data-stu-id="78e9b-234">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="78e9b-235">Per i tipi riferimento non nullable, il compilatore usa l'analisi di flusso per garantire che le variabili locali vengano inizializzate su un valore diverso da Null al momento della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-235">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="78e9b-236">I campi devono essere inizializzati durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-236">Fields must be initialized during construction.</span></span> <span data-ttu-id="78e9b-237">Il compilatore genera un avviso se la variabile non è impostata da una chiamata a uno dei costruttori disponibili o da un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="78e9b-237">The compiler generates a warning if the variable isn't set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="78e9b-238">Inoltre, non è possibile assegnare ai tipi riferimento non nullable un valore che potrebbe essere Null.</span><span class="sxs-lookup"><span data-stu-id="78e9b-238">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="78e9b-239">I tipi riferimento nullable non vengono controllati per verificare che non vengano assegnati o inizializzati su Null.</span><span class="sxs-lookup"><span data-stu-id="78e9b-239">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="78e9b-240">Tuttavia, il compilatore usa l'analisi di flusso per garantire che qualsiasi variabile di un tipo riferimento nullable venga controllata per i valori Null prima dell'accesso o prima che venga assegnata a un tipo riferimento non nullable.</span><span class="sxs-lookup"><span data-stu-id="78e9b-240">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="78e9b-241">Altre informazioni su questa funzionalità sono disponibili nella panoramica dei [tipi riferimento nullable](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-241">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="78e9b-242">È possibile provare in autonomia in una nuova applicazione in questa [esercitazione sui tipi riferimento nullable](../tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-242">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="78e9b-243">Per informazioni sulla procedura per eseguire la migrazione di una base di codice esistente per l'uso dei tipi riferimento nullable, vedere l'[esercitazione sulla migrazione di un'applicazione per l'uso dei tipi riferimento nullable](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-243">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="78e9b-244">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="78e9b-244">Asynchronous streams</span></span>

<span data-ttu-id="78e9b-245">A partire da C# 8.0, è possibile creare e utilizzare i flussi in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="78e9b-245">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="78e9b-246">Un metodo che restituisce un flusso asincrono ha tre proprietà:</span><span class="sxs-lookup"><span data-stu-id="78e9b-246">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="78e9b-247">È stato dichiarato con il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-247">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="78e9b-248">Restituisce <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-248">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="78e9b-249">Il metodo contiene istruzioni `yield return` per restituire gli elementi successivi nel flusso asincrono.</span><span class="sxs-lookup"><span data-stu-id="78e9b-249">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="78e9b-250">Per utilizzare un flusso asincrono, è necessario aggiungere la parola chiave `await` prima della parola chiave `foreach` quando si enumerano gli elementi del flusso.</span><span class="sxs-lookup"><span data-stu-id="78e9b-250">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="78e9b-251">Per l'aggiunta della parola chiave `await`, il metodo che enumera il flusso asincrono deve essere dichiarato con il modificatore `async` e restituire un tipo consentito per un metodo `async`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-251">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="78e9b-252">In genere ciò significa restituire <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-252">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="78e9b-253">Può anche essere <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-253">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="78e9b-254">Un metodo può sia utilizzare che produrre un flusso asincrono, il che significa che restituirebbe <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-254">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="78e9b-255">Il codice seguente genera una sequenza da 0 a 19, con un'attesa di 100 ms tra la generazione di ogni numero:</span><span class="sxs-lookup"><span data-stu-id="78e9b-255">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

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

<span data-ttu-id="78e9b-256">La sequenza viene enumerata usando l'istruzione `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-256">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="78e9b-257">È possibile provare i flussi asincroni in autonomia nell'esercitazione dedicata alla [creazione e all'utilizzo di flussi asincroni](../tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-257">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span> <span data-ttu-id="78e9b-258">Per impostazione predefinita, gli elementi del flusso vengono elaborati nel contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="78e9b-258">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="78e9b-259">Se si desidera disabilitare l'acquisizione del contesto, utilizzare il metodo <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> di estensione.</span><span class="sxs-lookup"><span data-stu-id="78e9b-259">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="78e9b-260">Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo sull' [utilizzo del modello asincrono basato su attività](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-260">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

## <a name="asynchronous-disposable"></a><span data-ttu-id="78e9b-261">Monouso asincrono</span><span class="sxs-lookup"><span data-stu-id="78e9b-261">Asynchronous disposable</span></span>

<span data-ttu-id="78e9b-262">A partire da C# 8,0, il linguaggio supporta i tipi monouso asincroni <xref:System.IAsyncDisposable?displayProperty=nameWithType> che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="78e9b-262">Starting with C# 8.0, the language supports asynchronous disposable types that implement the <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="78e9b-263">L'operando di `using` un'espressione può implementare <xref:System.IDisposable> o <xref:System.IAsyncDisposable>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-263">The operand of a `using` expression can implement either <xref:System.IDisposable> or <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="78e9b-264">Nel caso di `IAsyncDisposable`, il compilatore genera il codice per `await` l' <xref:System.Threading.Tasks.Task> oggetto restituito <xref:System.IAsyncDisposable.DisposeAsync%2A?displayProperty=nameWithType>da.</span><span class="sxs-lookup"><span data-stu-id="78e9b-264">In the case of `IAsyncDisposable`, the compiler generates code to `await` the <xref:System.Threading.Tasks.Task> returned from <xref:System.IAsyncDisposable.DisposeAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="78e9b-265">Per ulteriori informazioni, vedere l' [ `using` istruzione](../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-265">For more information, see the [`using` statement](../language-reference/keywords/using-statement.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="78e9b-266">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="78e9b-266">Indices and ranges</span></span>

<span data-ttu-id="78e9b-267">Gli indici e gli intervalli forniscono una sintassi concisa per l'accesso a singoli elementi o intervalli in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="78e9b-267">Indices and ranges provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="78e9b-268">Questo supporto per il linguaggio si basa su due nuovi tipi e due nuovi operatori:</span><span class="sxs-lookup"><span data-stu-id="78e9b-268">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="78e9b-269"><xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="78e9b-269"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="78e9b-270">Indice dell'operatore `^`end, che specifica che un indice è relativo alla fine della sequenza.</span><span class="sxs-lookup"><span data-stu-id="78e9b-270">The index from end operator `^`, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="78e9b-271"><xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="78e9b-271"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="78e9b-272">Operatore `..`Range, che specifica l'inizio e la fine di un intervallo come operandi.</span><span class="sxs-lookup"><span data-stu-id="78e9b-272">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="78e9b-273">Per iniziare, ecco come funzionano le regole per gli indici.</span><span class="sxs-lookup"><span data-stu-id="78e9b-273">Let's start with the rules for indexes.</span></span> <span data-ttu-id="78e9b-274">Prendere in considerazione una matrice `sequence`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-274">Consider an array `sequence`.</span></span> <span data-ttu-id="78e9b-275">L'indice `0` è uguale a `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-275">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="78e9b-276">L'indice `^0` è uguale a `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-276">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="78e9b-277">Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-277">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="78e9b-278">Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence.Length - n`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-278">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="78e9b-279">Un intervallo specifica *inizio* e *fine* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-279">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="78e9b-280">L'inizio dell'intervallo è inclusivo, ma la fine dell'intervallo è esclusiva, ovvero l' *inizio* è incluso nell'intervallo, ma la *fine* non è inclusa nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-280">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* isn't included in the range.</span></span> <span data-ttu-id="78e9b-281">L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-281">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span>

<span data-ttu-id="78e9b-282">Di seguito verranno esaminati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="78e9b-282">Let's look at a few examples.</span></span> <span data-ttu-id="78e9b-283">Si consideri la matrice seguente, annotata con il relativo indice dall'inizio e dalla fine:</span><span class="sxs-lookup"><span data-stu-id="78e9b-283">Consider the following array, annotated with its index from the start and from the end:</span></span>

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

<span data-ttu-id="78e9b-284">È possibile recuperare l'ultima parola con l'indice `^1`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-284">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="78e9b-285">Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox".</span><span class="sxs-lookup"><span data-stu-id="78e9b-285">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="78e9b-286">Include da `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-286">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="78e9b-287">L'elemento `words[4]` non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="78e9b-287">The element `words[4]` isn't in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="78e9b-288">Il codice seguente crea un intervallo secondario con "lazy" e "dog".</span><span class="sxs-lookup"><span data-stu-id="78e9b-288">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="78e9b-289">Include `words[^2]` e `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-289">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="78e9b-290">L'indice `words[^0]` finale non è incluso:</span><span class="sxs-lookup"><span data-stu-id="78e9b-290">The end index `words[^0]` isn't included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="78e9b-291">Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:</span><span class="sxs-lookup"><span data-stu-id="78e9b-291">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="78e9b-292">È anche possibile dichiarare gli intervalli come variabili:</span><span class="sxs-lookup"><span data-stu-id="78e9b-292">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="78e9b-293">L'intervallo può quindi essere usato all'interno dei caratteri `[` e `]`:</span><span class="sxs-lookup"><span data-stu-id="78e9b-293">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="78e9b-294">Non solo le matrici supportano gli indici e gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="78e9b-294">Not only arrays support indices and ranges.</span></span> <span data-ttu-id="78e9b-295">È anche possibile usare gli indici e gli intervalli [string](../language-reference/builtin-types/reference-types.md#the-string-type)con String <xref:System.Span%601>, o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="78e9b-295">You can also use indices and ranges with [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="78e9b-296">Per altre informazioni, vedere [supporto dei tipi per indici e intervalli](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span><span class="sxs-lookup"><span data-stu-id="78e9b-296">For more information, see [Type support for indices and ranges](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span></span>

<span data-ttu-id="78e9b-297">È possibile ottenere maggiori informazioni su indici e intervalli nell'esercitazione [Indici e intervalli](../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-297">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="78e9b-298">Assegnazione di Unione null</span><span class="sxs-lookup"><span data-stu-id="78e9b-298">Null-coalescing assignment</span></span>

<span data-ttu-id="78e9b-299">C# 8,0 introduce l'operatore `??=`di assegnazione di Unione null.</span><span class="sxs-lookup"><span data-stu-id="78e9b-299">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="78e9b-300">È possibile usare l' `??=` operatore per assegnare il valore dell'operando destro all'operando sinistro solo se l'operando sinistro restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="78e9b-300">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="78e9b-301">Per ulteriori informazioni, vedere [?? e?? = articolo Operators](../language-reference/operators/null-coalescing-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="78e9b-301">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="78e9b-302">Tipi costruiti non gestiti</span><span class="sxs-lookup"><span data-stu-id="78e9b-302">Unmanaged constructed types</span></span>

<span data-ttu-id="78e9b-303">In C# 7,3 e versioni precedenti, un tipo costruito (un tipo che include almeno un argomento di tipo) non può essere un [tipo non gestito](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-303">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) can't be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="78e9b-304">A partire da C# 8,0, un tipo di valore costruito non è gestito se contiene campi solo di tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="78e9b-304">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="78e9b-305">Ad esempio, data la seguente definizione del tipo generico `Coords<T>` :</span><span class="sxs-lookup"><span data-stu-id="78e9b-305">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="78e9b-306">il `Coords<int>` tipo è un tipo non gestito in C# 8,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="78e9b-306">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="78e9b-307">Come per qualsiasi tipo non gestito, è possibile creare un puntatore a una variabile di questo tipo o [allocare un blocco di memoria nello stack per le](../language-reference/operators/stackalloc.md) istanze di questo tipo:</span><span class="sxs-lookup"><span data-stu-id="78e9b-307">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="78e9b-308">Per ulteriori informazioni, vedere [tipi non gestiti](../language-reference/builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="78e9b-308">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="stackalloc-in-nested-expressions"></a><span data-ttu-id="78e9b-309">Stackalloc nelle espressioni annidate</span><span class="sxs-lookup"><span data-stu-id="78e9b-309">Stackalloc in nested expressions</span></span>

<span data-ttu-id="78e9b-310">A partire da C# 8,0, se il risultato di un'espressione [stackalloc](../language-reference/operators/stackalloc.md) è di <xref:System.Span%601?displayProperty=nameWithType> tipo <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> o, è possibile usare l' `stackalloc` espressione in altre espressioni:</span><span class="sxs-lookup"><span data-stu-id="78e9b-310">Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:</span></span>

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6, 8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="78e9b-311">Miglioramento delle stringhe verbatim interpolate</span><span class="sxs-lookup"><span data-stu-id="78e9b-311">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="78e9b-312">L' `$` ordine dei token `@` e nelle stringhe verbatim [interpolate](../language-reference/tokens/interpolated.md) può essere any: sia `$@"..."` che `@$"..."` sono stringhe verbatim interpolate valide.</span><span class="sxs-lookup"><span data-stu-id="78e9b-312">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="78e9b-313">Nelle versioni precedenti di C# il `$` token deve essere visualizzato prima `@` del token.</span><span class="sxs-lookup"><span data-stu-id="78e9b-313">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
