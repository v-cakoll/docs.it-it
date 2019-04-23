---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 086be4649f4e7e27ff98df6f26d08856683865c8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611783"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="f9a4d-103">Novità di .NET Core 3.0 (Preview 2)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="f9a4d-104">Questo articolo descrive le novità di .NET Core 3.0 (Preview 2).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="f9a4d-105">Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="f9a4d-106">Utilizzando un componente di .NET Core 3.0 SDK denominato Windows Desktop, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="f9a4d-107">Il componente Windows Desktop è dunque supportato e incluso solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="f9a4d-108">Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="f9a4d-109">.NET Core 3.0 aggiunge il supporto per C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="f9a4d-110">[Scaricare e iniziare subito a usare .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) in Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-110">[Download and get started with .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="f9a4d-111">È possibile visualizzare i dettagli completi della versione nelle [note sulla versione di .NET Core 3.0 Preview 2](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-111">You can see complete details of the release in the [.NET Core 3.0 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="f9a4d-112">Per altre informazioni sulle funzionalità incluse in ogni versione, vedere gli annunci seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-112">For more information about what was released with each version, see the following announcements:</span></span>

- [<span data-ttu-id="f9a4d-113">Annuncio di .NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="f9a4d-113">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [<span data-ttu-id="f9a4d-114">Annuncio di .NET Core 3.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="f9a4d-114">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)

## <a name="c-8"></a><span data-ttu-id="f9a4d-115">C# 8</span><span class="sxs-lookup"><span data-stu-id="f9a4d-115">C# 8</span></span>

<span data-ttu-id="f9a4d-116">.NET Core 3.0 supporta C# 8 e a partire da .NET Core 3.0 Preview 2 supporta queste nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-116">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="f9a4d-117">Per altre informazioni sulle funzionalità di C# 8.0, vedere i post di blog seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-117">For more information about C# 8.0 features, see the following blog posts:</span></span>

- <span data-ttu-id="f9a4d-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/) (Nuove potenzialità con i modelli in C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)</span></span>
- <span data-ttu-id="f9a4d-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/) (Un giro di C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)</span></span>
- <span data-ttu-id="f9a4d-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/) (Sviluppo con C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/)</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="f9a4d-121">Gli intervalli e indici</span><span class="sxs-lookup"><span data-stu-id="f9a4d-121">Ranges and indices</span></span>

<span data-ttu-id="f9a4d-122">Il nuovo tipo `Index` può essere usato per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-122">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="f9a4d-123">È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-123">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="f9a4d-124">Esiste anche un tipo `Range`, costituito da due valori `Index`, uno per l'inizio e uno per la fine, che può essere scritto con un'espressione intervallo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-124">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="f9a4d-125">È quindi possibile eseguire l'indicizzazione con `Range` per generare una sezione:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-125">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="f9a4d-126">Flussi asincroni</span><span class="sxs-lookup"><span data-stu-id="f9a4d-126">Async streams</span></span>

<span data-ttu-id="f9a4d-127">Il tipo `IAsyncEnumerable<T>` è una nuova versione asincrona di `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-127">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="f9a4d-128">Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-128">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="f9a4d-129">L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-129">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="f9a4d-130">L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-130">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="f9a4d-131">Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-131">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="f9a4d-132">Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-132">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="f9a4d-133">Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-133">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="f9a4d-134">È necessario .NET Core 3.0 Preview 2 per usare flussi asincroni se si vuole sviluppare con Visual Studio 2019 o con l'anteprima più recente dell'[estensione C# per Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-134">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="f9a4d-135">Se si usa .NET Core 3.0 Preview 2 dalla riga di comando, tutto funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-135">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="f9a4d-136">Dichiarazioni using</span><span class="sxs-lookup"><span data-stu-id="f9a4d-136">Using Declarations</span></span>

<span data-ttu-id="f9a4d-137">Le *dichiarazioni using* sono un nuovo modo per assicurarsi che l'oggetto venga eliminato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-137">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="f9a4d-138">Una *dichiarazione using* mantiene attivo l'oggetto mentre è ancora nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-138">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="f9a4d-139">Quando l'oggetto diventa esterno all'ambito, viene eliminato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-139">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="f9a4d-140">In questo modo si riducono le *istruzioni using* annidate e il codice diventa più chiaro.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-140">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="f9a4d-141">Espressioni switch</span><span class="sxs-lookup"><span data-stu-id="f9a4d-141">Switch Expressions</span></span>

<span data-ttu-id="f9a4d-142">Le *espressioni switch* sono un modo più pulito per eseguire un'*istruzione switch* ma, trattandosi di un'espressione, restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-142">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="f9a4d-143">Le *espressioni switch* sono anche completamente integrate con i criteri di ricerca e usano il criterio di rimozione `_` per rappresentare il valore `default`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-143">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="f9a4d-144">È possibile visualizzare la sintassi per le *espressioni switch* nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-144">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="f9a4d-145">In questo esempio entrano in gioco due criteri.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-145">There are two patterns at play in this example.</span></span> <span data-ttu-id="f9a4d-146">`o` corrisponde prima di tutto al *criterio di tipo* `Point` e poi al *criterio di proprietà* all'interno delle *{parentesi graffe}*.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-146">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="f9a4d-147">`_` descrive `discard pattern`, uguale a `default` per le *istruzioni switch*.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-147">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="f9a4d-148">I criteri consentono di scrivere codice dichiarativo che definisce la finalità anziché codice procedurale che implementa i test.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-148">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="f9a4d-149">Il compilatore diventa responsabile dell'implementazione di tale codice procedurale noioso e viene garantito che l'operazione sia sempre eseguita in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-149">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="f9a4d-150">Esistono comunque casi in cui le *istruzioni switch* saranno preferibili rispetto alle *espressioni switch* e i criteri possono essere usati con entrambi gli stili di sintassi.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-150">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="f9a4d-151">Per altre informazioni, vedere [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/) (Nuove potenzialità con i modelli in C# 8.0).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-151">For more information, see [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="f9a4d-152">Miglioramenti per le API a virgola mobile IEEE</span><span class="sxs-lookup"><span data-stu-id="f9a4d-152">IEEE Floating-point improvements</span></span>

<span data-ttu-id="f9a4d-153">Le API a virgola mobile sono in corso di aggiornamento per soddisfare i requisiti della [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-153">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="f9a4d-154">L'obiettivo di queste modifiche è esporre tutte le operazioni "obbligatorie" e assicurarsi che siano compatibili a livello di comportamento con la specifica IEEE.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-154">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="f9a4d-155">Correzioni per analisi e formattazione:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-155">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="f9a4d-156">Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-156">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="f9a4d-157">Analisi corretta e formattazione dello zero negativo.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-157">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="f9a4d-158">Analisi corretta di valori Infinity e NaN con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-158">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="f9a4d-159">Le nuove API per operazioni matematiche:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-159">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="f9a4d-160">Corrispondono alle operazioni IEEE `nextUp` e `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-160">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="f9a4d-161">Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-161">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="f9a4d-162">Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-162">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="f9a4d-163">Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-163">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="f9a4d-164">Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-164">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="f9a4d-165">Corrispondono all'operazione IEEE `logB` che restituisce il logaritmo in base 2 integrale del parametro di input.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-165">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="f9a4d-166">Equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-166">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="f9a4d-167">Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-167">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="f9a4d-168">Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-168">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="f9a4d-169">Gli errori di arrotondamento sono ridotti al minimo.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-169">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="f9a4d-170">Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-170">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="f9a4d-171">Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-171">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="f9a4d-172">Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)` che restituisce `1e308`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-172">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="f9a4d-173">L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-173">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="f9a4d-174">Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-174">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="f9a4d-175">Intrinseci dipendenti dalla piattaforma .NET</span><span class="sxs-lookup"><span data-stu-id="f9a4d-175">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="f9a4d-176">Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-176">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="f9a4d-177">Queste istruzioni consentono di ottenere miglioramenti delle prestazioni notevoli in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-177">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="f9a4d-178">Oltre a esporre le API per i programmi, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-178">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="f9a4d-179">Le richieste pull CoreCLR seguenti illustrano alcuni degli intrinseci, tramite implementazione o uso:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-179">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* <span data-ttu-id="f9a4d-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585) (Implementare intrinseci hardware SSE2 semplici)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585)</span></span>
* <span data-ttu-id="f9a4d-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538) (Implementare gli intrinseci hardware SSE)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538)</span></span>
* <span data-ttu-id="f9a4d-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822) (Intrinseci hardware base Arm64)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822)</span></span>
* <span data-ttu-id="f9a4d-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073) (Usare TZCNT e LZCNT per Locate{First|Last}Found{Byte|Char})</span><span class="sxs-lookup"><span data-stu-id="f9a4d-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073)</span></span>

<span data-ttu-id="f9a4d-184">Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET), che definisce un approccio per la definizione di questa infrastruttura hardware, che consente a Microsoft, fornitori di chip o altre società o singoli di definire API per hardware/chip che devono essere esposte al codice .NET.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-184">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="f9a4d-185">File eseguibili predefiniti</span><span class="sxs-lookup"><span data-stu-id="f9a4d-185">Default executables</span></span>

<span data-ttu-id="f9a4d-186">Per impostazione predefinita .NET Core compilerà ora i [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-186">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="f9a4d-187">Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-187">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="f9a4d-188">Finora solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) producevano un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-188">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="f9a4d-189">Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile purché corrisponda all'ambiente e alla piattaforma dell'SDK usato.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-189">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="f9a4d-190">Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-190">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="f9a4d-191">È possibile fare doppio clic sul file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-191">You can double-click on the executable.</span></span>
* <span data-ttu-id="f9a4d-192">È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-192">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="f9a4d-193">Copia delle dipendenze tramite la compilazione</span><span class="sxs-lookup"><span data-stu-id="f9a4d-193">Build copies dependencies</span></span>

<span data-ttu-id="f9a4d-194">`dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet alla cartella di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-194">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="f9a4d-195">In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-195">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="f9a4d-196">Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-196">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-dotnet-tools"></a><span data-ttu-id="f9a4d-197">Strumenti dotnet locali</span><span class="sxs-lookup"><span data-stu-id="f9a4d-197">Local dotnet tools</span></span>

> [!WARNING]
> <span data-ttu-id="f9a4d-198">È stata introdotta una modifica per gli strumenti .NET Core locali tra .NET Core 3.0 Preview 1 e .NET Core 3.0 Preview 2.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-198">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="f9a4d-199">Se sono stati provati gli strumenti locali nella versione Preview 1 eseguendo un comando come `dotnet tool restore` o `dotnet tool install`, è necessario eliminare la cartella della cache degli strumenti locali prima che gli strumenti locali funzionino correttamente nella versione Preview 2.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-199">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="f9a4d-200">Questa cartella si trova in:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-200">This folder is located at:</span></span>
>
> <span data-ttu-id="f9a4d-201">In Mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="f9a4d-201">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="f9a4d-202">In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="f9a4d-202">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
> <span data-ttu-id="f9a4d-203">Se non si elimina questa cartella, si riceverà un errore.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-203">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="f9a4d-204">Mentre .NET Core 2.1 supportava strumenti globali, .NET Core 3.0 ha ora strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-204">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="f9a4d-205">Gli strumenti locali sono simili agli strumenti globali, ma sono associati a una determinata posizione sul disco.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-205">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="f9a4d-206">Ciò consente di usare strumenti specifici per ogni progetto e ogni repository.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-206">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="f9a4d-207">Gli strumenti installati in locale non sono disponibili a livello globale.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-207">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="f9a4d-208">Gli strumenti vengono distribuiti come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-208">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="f9a4d-209">Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-209">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="f9a4d-210">Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-210">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="f9a4d-211">Creando questo file manifesto nella radice del repository, si ha la certezza che chiunque cloni il codice non possa ripristinare e usare gli strumenti necessari per lavorare in modo corretto con il codice.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-211">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="f9a4d-212">Per creare un file manifesto `dotnet-tools.json`, usare:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-212">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="f9a4d-213">Aggiungere un nuovo strumento al manifesto locale con:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-213">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="f9a4d-214">È anche possibile elencare gli strumenti nel manifesto locale con:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-214">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="f9a4d-215">Per vedere quali strumenti vengono installati a livello globale, usare:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-215">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="f9a4d-216">Quando il file manifesto degli strumenti locali è disponibile, ma gli strumenti definiti nel manifesto non sono stati installati, usare il comando seguente per scaricare e installare automaticamente tali strumenti in locale:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-216">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="f9a4d-217">Eseguire uno strumento locale con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-217">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="f9a4d-218">Quando viene eseguito uno strumento locale, dotnet cerca un manifesto nella struttura di directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-218">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="f9a4d-219">Quando viene trovato un file manifesto degli strumenti, viene eseguita la ricerca dello strumento richiesto.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-219">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="f9a4d-220">Se lo strumento viene trovato nel manifesto, ma non la cache, l'utente riceve un errore e deve eseguire `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-220">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="f9a4d-221">Per rimuovere uno strumento dal file manifesto dello strumento locale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-221">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="f9a4d-222">Il file manifesto dello strumento è progettato per consentire la modifica manuale, ad esempio per aggiornare la versione necessaria per usare il repository.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-222">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="f9a4d-223">Ecco un file `dotnet-tools.json` di esempio:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-223">Here is an example `dotnet-tools.json` file:</span></span>

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

<span data-ttu-id="f9a4d-224">Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="f9a4d-225">Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="f9a4d-226">Per installarli a livello globale o locale, è ancora necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-226">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="f9a4d-227">Desktop di Windows</span><span class="sxs-lookup"><span data-stu-id="f9a4d-227">Windows desktop</span></span>

<span data-ttu-id="f9a4d-228">A partire da .NET Core 3.0 Preview 1, è possibile compilare applicazioni desktop di Windows con WPF e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-228">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="f9a4d-229">Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-229">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="f9a4d-230">Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-230">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="f9a4d-231">È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-231">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="f9a4d-232">Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-232">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="f9a4d-233">Le finestre di progettazione non sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-233">Designers are still not yet supported.</span></span> <span data-ttu-id="f9a4d-234">È possibile aprire, avviare ed eseguire il debug di questi progetti in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-234">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="f9a4d-235">Visual Studio 2017 15.9 aggiunge la possibilità di [abilitare le anteprime di .NET Core](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), ma è necessario attivare questa funzionalità e non è uno scenario supportato.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-235">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="f9a4d-236">I nuovi progetti sono uguali ai progetti .NET Core esistenti, con alcune aggiunte.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-236">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="f9a4d-237">Di seguito è riportato il confronto tra il progetto console .NET Core di base e un progetto Windows Form e WPF di base.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-237">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="f9a4d-238">In un progetto console .NET Core il progetto usa l'SDK `Microsoft.NET.Sdk` e dichiara una dipendenza da .NET Core 3.0 tramite il framework di destinazione `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-238">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="f9a4d-239">Per creare un'app desktop di Windows, usare l'SDK `Microsoft.NET.Sdk.WindowsDesktop` e scegliere quale framework interfaccia utente usare:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-239">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

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

<span data-ttu-id="f9a4d-240">Per scegliere Windows Form invece di WPF, impostare `UseWindowsForms` invece che `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-240">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

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

<span data-ttu-id="f9a4d-241">Sia `UseWPF` che `UseWindowsForms` possono essere impostati su `true` se l'app usa entrambi i framework, ad esempio quando una finestra di dialogo di Windows Form ospita un controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-241">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="f9a4d-242">Condividere commenti e suggerimenti nei repository [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) e [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-242">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="f9a4d-243">Distribuzione MSIX per Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="f9a4d-243">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="f9a4d-244">[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di app Windows.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-244">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="f9a4d-245">Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-245">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="f9a4d-246">Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-246">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

> [!NOTE]
> <span data-ttu-id="f9a4d-247">Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-247">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
>
> ```xml
> <RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
> ```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="f9a4d-248">Supporto JSON predefinito rapido</span><span class="sxs-lookup"><span data-stu-id="f9a4d-248">Fast built-in JSON support</span></span>

<span data-ttu-id="f9a4d-249">L'ecosistema .NET si è basato su [**Json.NET**](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-249">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="f9a4d-250">Come tipo di dati di base **Json.NET** usa le stringhe .NET, che in realtà sono UTF-16.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-250">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="f9a4d-251">Il nuovo supporto JSON predefinito offre prestazioni elevate, bassa allocazione ed è basato su `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-251">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="f9a4d-252">Sono stati aggiunti tre nuovi tipi correlati principali JSON a .NET Core 3.0 nello spazio dei nomi `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-252">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="f9a4d-253">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="f9a4d-253">Utf8JsonReader</span></span>

<span data-ttu-id="f9a4d-254">`System.Text.Json.Utf8JsonReader` è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-254">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="f9a4d-255">`Utf8JsonReader` è un tipo di base di basso livello, che può essere sfruttato per compilare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-255">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="f9a4d-256">La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-256">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="f9a4d-257">Non viene allocato fino a quando non è necessario realizzare i token JSON come stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-257">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="f9a4d-258">Questa nuova API includerà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-258">This new API will include the following components:</span></span>

* <span data-ttu-id="f9a4d-259">Nell'anteprima 1: lettore JSON (accesso sequenziale)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-259">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="f9a4d-260">Presto disponibili: writer JSON, DOM (accesso casuale), serializzatore poco, deserializzatore poco</span><span class="sxs-lookup"><span data-stu-id="f9a4d-260">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="f9a4d-261">Ecco il ciclo del lettore di base per `Utf8JsonReader` che può essere usato come punto iniziale:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-261">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

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

### <a name="utf8jsonwriter"></a><span data-ttu-id="f9a4d-262">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="f9a4d-262">Utf8JsonWriter</span></span>

<span data-ttu-id="f9a4d-263">`System.Text.Json.Utf8JsonWriter` rende disponibile un metodo ad alte prestazioni, senza memorizzazione nella cache e forward-only per la scrittura di test JSON con codifica UTF-8 da tipi .NET comuni, come `String`, `Int32` e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-263">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="f9a4d-264">Come il lettore, il writer è un tipo di base di basso livello, che può essere sfruttato per creare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-264">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="f9a4d-265">La scrittura di un payload JSON con il nuovo `Utf8JsonWriter` offre velocità maggiori del 30-80% rispetto all'uso del writer da **Json.NET** e non prevede allocazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-265">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="f9a4d-266">Ecco un esempio di utilizzo di `Utf8JsonWriter` che può essere usato come punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-266">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

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

<span data-ttu-id="f9a4d-267">`Utf8JsonWriter` accetta `IBufferWriter<byte>` come posizione di output per la scrittura sincrona dei dati JSON ed è il chiamante a dover fornire un'implementazione concreta.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-267">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="f9a4d-268">Attualmente la piattaforma non include un'implementazione di questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-268">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="f9a4d-269">Per un esempio di `IBufferWriter<byte>`, vedere <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-269">For an example of `IBufferWriter<byte>`, see <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="f9a4d-270">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="f9a4d-270">JsonDocument</span></span>

<span data-ttu-id="f9a4d-271">`System.Text.Json.JsonDocument` è basato su `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-271">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="f9a4d-272">`JsonDocument` offre la possibilità di analizzare i dati JSON e compilare un modello DOM (Document Object Model) di sola lettura su cui è possibile eseguire query per supportare l'accesso casuale e l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-272">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="f9a4d-273">Gli elementi JSON che compongono i dati sono accessibili tramite il tipo `JsonElement` che viene esposto da `JsonDocument` come una proprietà denominata `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-273">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="f9a4d-274">`JsonElement` contiene gli enumeratori di matrice e oggetto JSON insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-274">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="f9a4d-275">L'analisi di un payload JSON tipico e l'accesso a tutti i relativi membri tramite `JsonDocument` è 2-3 volte più veloce rispetto a **Json.NET** con allocazioni minime per dati di dimensioni ragionevoli, ovvero inferiori a 1 MB.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-275">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="f9a4d-276">Ecco un esempio di utilizzo di `JsonDocument` e `JsonElement` che può essere usato come punto di partenza:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-276">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

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

## <a name="assembly-unloadability"></a><span data-ttu-id="f9a4d-277">Assembly non caricabili</span><span class="sxs-lookup"><span data-stu-id="f9a4d-277">Assembly Unloadability</span></span>

<span data-ttu-id="f9a4d-278">Gli assembly non caricabili sono una nuova funzionalità di `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-278">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="f9a4d-279">Questa nuova funzionalità è in gran parte trasparente dal punto di vista di un'API ed è esposta solo con poche nuove API.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-279">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="f9a4d-280">Consente di scaricare il contesto di un caricatore, rilasciando tutta la memoria per tipi istanziati, i campi statici e per l'assembly stesso.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-280">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="f9a4d-281">Un'applicazione deve essere in grado di caricare e scaricare gli assembly tramite questo meccanismo a tempo indefinito senza riscontrare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-281">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="f9a4d-282">Questa nuova funzionalità può essere usata per scenari simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-282">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="f9a4d-283">Scenari con plug-in in cui sono richiesti il caricamento e lo scaricamento dinamico del plug-in.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-283">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span>
* <span data-ttu-id="f9a4d-284">Compilazione, esecuzione e scaricamento dinamici del codice.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-284">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="f9a4d-285">Utile per siti Web, motori di scripting e così via.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-285">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="f9a4d-286">Il caricamento degli assembly per introspezione (ad esempio ReflectionOnlyLoad), nonostante [MetadataLoadContext](#type-metadataloadcontext) (rilasciato nella versione Preview 1) sia una scelta migliore in molti casi.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-286">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="f9a4d-287">Per altre informazioni, vedere il documento [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) (Usare la funzionalità che impedisce lo scaricamento).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-287">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="f9a4d-288">Lo scaricamento degli assembly richiede notevole attenzione per assicurare che tutti i riferimenti agli oggetti gestiti dall'esterno del contesto di un caricatore vengano riconosciuti e gestiti.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-288">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="f9a4d-289">Quando è richiesto lo scaricamento del contesto del caricatore, occorre rimuovere tutti gli eventuali riferimenti esterni in modo che il contesto del caricatore sia intrinsecamente coerente solo con se stesso.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-289">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="f9a4d-290">La funzionalità per impedire lo scaricamento degli assembly era inclusa in .NET Framework tramite i domini dell'applicazione (AppDomain), non supportati in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-290">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="f9a4d-291">AppDomain presenta sia vantaggi che limiti rispetto a questo nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-291">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="f9a4d-292">Prendere in considerazione questo nuovo modello di caricatore per ottenere maggiore flessibilità e prestazioni più elevate rispetto ad AppDomain.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-292">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="f9a4d-293">Interoperabilità nativa di Windows</span><span class="sxs-lookup"><span data-stu-id="f9a4d-293">Windows Native Interop</span></span>

<span data-ttu-id="f9a4d-294">Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-294">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="f9a4d-295">**P/Invoke** è supportato a partire da .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-295">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="f9a4d-296">Con .NET Core 3.0 è stato ora aggiunto il supporto della possibilità di **generare contestualmente API COM** e di **attivare API WinRT**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-296">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="f9a4d-297">È possibile vedere un esempio dell'uso di COM con il [codice sorgente per la demo con Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-297">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="f9a4d-298">Tipo: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="f9a4d-298">Type: SequenceReader</span></span>

<span data-ttu-id="f9a4d-299">In .NET Core 3.0 è stato aggiunto `System.Buffers.SequenceReader` che può essere usato come lettore per `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-299">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="f9a4d-300">Ciò consente un'analisi semplice, a prestazioni elevate e allocazione ridotta dei dati di `System.IO.Pipelines` che possono attraversare più buffer sottostanti.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-300">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span>

<span data-ttu-id="f9a4d-301">L'esempio seguente suddivide un elemento `Sequence` di input in righe delimitate da `CR/LF` valide:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-301">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

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

## <a name="type-metadataloadcontext"></a><span data-ttu-id="f9a4d-302">Tipo: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="f9a4d-302">Type: MetadataLoadContext</span></span>

<span data-ttu-id="f9a4d-303">È stato aggiunto il tipo `MetadataLoadContext` che consente la lettura dei metadati dell'assembly senza impatto sul dominio dell'applicazione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-303">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="f9a4d-304">Gli assembly vengono letti come dati, inclusi gli assembly compilati per architetture e piattaforme diverse da quelle dell'ambiente di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-304">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="f9a4d-305">`MetadataLoadContext` si sovrappone a <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, che è disponibile solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-305">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="f9a4d-306">`MetdataLoadContext` è disponibile nel pacchetto [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-306">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="f9a4d-307">Si tratta di un pacchetto .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-307">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="f9a4d-308">`MetadataLoadContext` espone API simili al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, ma non si basa su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-308">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="f9a4d-309">In modo analogo a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` consente il caricamento degli assembly all'interno di un universo di caricamento di assembly isolato.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-309">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="f9a4d-310">Le API `MetdataLoadContext` restituiscono oggetti <xref:System.Reflection.Assembly>, consentendo l'uso di API di reflection familiari.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-310">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="f9a4d-311">Le API orientate all'esecuzione, ad esempio [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), non sono consentite e genereranno l'eccezione InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-311">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="f9a4d-312">L'esempio seguente illustra come trovare tipi concreti in un assembly che implementa una determinata interfaccia:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-312">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

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

<span data-ttu-id="f9a4d-313">Gli scenari per `MetadataLoadContext` includono funzionalità della fase di progettazione, strumenti della fase di compilazione e funzionalità esclusive di runtime che devono esaminare un set di assembly come dati e i cui blocchi di file e la cui memoria vengono liberati dopo l'esecuzione dell'ispezione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-313">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="f9a4d-314">`MetadataLoadContext` ha una classe resolver passata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-314">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="f9a4d-315">Il processo del resolver consiste nel caricare un `Assembly`, dato il relativo `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-315">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="f9a4d-316">La classe resolver deriva dalla classe astratta `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-316">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="f9a4d-317">Con `PathAssemblyResolver` viene fornita un'implementazione del resolver per gli scenari basati sul percorso.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-317">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="f9a4d-318">I [test di MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) illustrano numerosi casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-318">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="f9a4d-319">I [test di Assembly](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sono un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-319">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="f9a4d-320">TLS 1.3 e OpenSSL 1.1.1 in Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-320">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="f9a4d-321">.NET Core sfrutterà ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-321">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="f9a4d-322">I vantaggi di TLS 1.3 sono diversi, secondo il [team di OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="f9a4d-322">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="f9a4d-323">Durata della connessione migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-323">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="f9a4d-324">Maggiore sicurezza grazie alla rimozione di algoritmi di crittografia obsoleti e non sicuri e alla crittografia di più elementi dell'handshake della connessione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-324">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="f9a4d-325">.NET Core 3.0 Preview 1 può utilizzare **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (a seconda della versione migliore trovata, in un sistema Linux).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-325">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="f9a4d-326">Quando **OpenSSL 1.1.1** è disponibile, i tipi SslStream e HttpClient useranno **TLS 1.3** quando si usa `SslProtocols.None` (protocolli predefiniti di sistema), presupponendo che sia il client che il server supportino **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-326">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="f9a4d-327">L'esempio seguente illustra .NET Core 3.0 Preview 1 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-327">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

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
><span data-ttu-id="f9a4d-328">Windows e macOS non supportano ancora **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-328">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="f9a4d-329">.NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-329">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="f9a4d-330">Crittografia</span><span class="sxs-lookup"><span data-stu-id="f9a4d-330">Cryptography</span></span>

<span data-ttu-id="f9a4d-331">È stato aggiunto il supporto per le modalità di crittografia **AES-GCM** e **AES-CCM**, implementate tramite `System.Security.Cryptography.AesGcm` e `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-331">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="f9a4d-332">Questi algoritmi sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption) nonché i primi algoritmi di cifratura autenticata aggiunti a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-332">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="f9a4d-333">Il codice seguente illustra l'uso della modalità di crittografia **AesGcm** per crittografare e decrittografare dati casuali.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-333">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="f9a4d-334">Il codice per **AesCcm** sarà pressoché identico, con la sola differenza dei nomi di variabile di classe.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-334">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

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

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="f9a4d-335">Importazione/Esportazione di chiavi crittografiche</span><span class="sxs-lookup"><span data-stu-id="f9a4d-335">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="f9a4d-336">.NET core 3.0 Preview 1 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche dai formati standard, senza bisogno usare un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-336">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="f9a4d-337">Tutti i tipi di chiavi (RSA, DSA, ECDsa, ECDiffieHellman) supportano il formato **X.509 SubjectPublicKeyInfo** per le chiavi pubbliche e i formati **PKCS#8 PrivateKeyInfo** e **PKCS#8 EncryptedPrivateKeyInfo** per le chiavi private.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-337">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="f9a4d-338">RSA supporta anche **PKCS#1 RSAPublicKey** e **PKCS#1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-338">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="f9a4d-339">Tutti i metodi di esportazione producono dati binari con codifica DER e i metodi di importazione presentano lo stesso comportamento.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-339">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="f9a4d-340">Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-340">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

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

<span data-ttu-id="f9a4d-341">I file PKCS#8 possono essere esaminati con la classe `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-341">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="f9a4d-342">I file PFX/PKCS#12 possono essere esaminati e modificati rispettivamente con `System.Security.Cryptography.Pkcs.Pkcs12Info` e `System.Security.Cryptography.Pkcs.Pkcs12Builder`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-342">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="f9a4d-343">SerialPort per Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-343">SerialPort for Linux</span></span>

<span data-ttu-id="f9a4d-344">.NET Core 3.0 supporta ora <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-344">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="f9a4d-345">In precedenza, .NET Core supportava solo l'uso del tipo `SerialPort` in Windows.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-345">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="f9a4d-346">Altri miglioramenti BCL</span><span class="sxs-lookup"><span data-stu-id="f9a4d-346">More BCL Improvements</span></span>

<span data-ttu-id="f9a4d-347">`Span<T>`, `Memory<T>` e i tipi correlati introdotti in .NET Core 2.1 sono stati ottimizzati in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-347">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="f9a4d-348">Le operazioni comuni, ad esempio la costruzione di intervalli, il sezionamento, l'analisi e la formattazione offrono ora prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-348">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span>

<span data-ttu-id="f9a4d-349">Inoltre, i tipi come `String` sono stati sottoposti a miglioramenti per aumentarne l'efficienza quando sono usati come chiavi con `Dictionary<TKey, TValue>` e altre raccolte.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-349">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="f9a4d-350">Per trarre vantaggio da questi miglioramenti, non sono necessarie modifiche al codice.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-350">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="f9a4d-351">.NET Core 3 Preview 1 presenta anche i nuovi miglioramenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-351">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="f9a4d-352">Supporto di Brotli predefinito in HttpClient</span><span class="sxs-lookup"><span data-stu-id="f9a4d-352">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="f9a4d-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="f9a4d-354">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="f9a4d-354">Unsafe.Unbox</span></span>
* <span data-ttu-id="f9a4d-355">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="f9a4d-355">CancellationToken.Unregister</span></span>
* <span data-ttu-id="f9a4d-356">Operatori aritmetici complessi</span><span class="sxs-lookup"><span data-stu-id="f9a4d-356">Complex arithmetic operators</span></span>
* <span data-ttu-id="f9a4d-357">API socket per il keep-alive TCP</span><span class="sxs-lookup"><span data-stu-id="f9a4d-357">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="f9a4d-358">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="f9a4d-358">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="f9a4d-359">Analisi IPEndPoint</span><span class="sxs-lookup"><span data-stu-id="f9a4d-359">IPEndPoint parsing</span></span>
* <span data-ttu-id="f9a4d-360">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="f9a4d-360">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="f9a4d-361">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="f9a4d-361">Tiered compilation</span></span>

<span data-ttu-id="f9a4d-362">Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) è attiva.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-362">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="f9a4d-363">È una funzionalità che consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori, sia all'avvio che per ottimizzare la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-363">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="f9a4d-364">Questa funzionalità è stata aggiunta come funzionalità con consenso esplicito in [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) ed è stata abilitata per impostazione predefinita in [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-364">This feature was added as an opt-in feature in [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="f9a4d-365">Successivamente, è stata ripristinata come funzionalità con consenso esplicito nella versione .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-365">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="f9a4d-366">Supporto ARM64 per Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-366">ARM64 Linux support</span></span>

<span data-ttu-id="f9a4d-367">È stato aggiunto il supporto per ARM64 per Linux.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-367">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="f9a4d-368">Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-368">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="f9a4d-369">[Sono disponibili immagini Docker per .NET Core per ARM64](https://hub.docker.com/r/microsoft/dotnet/) di Alpine, Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-369">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="f9a4d-370">Per altre informazioni., vedere [Stato di ARM64 per .NET Core](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-370">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="f9a4d-371">Il supporto **ARM64** per Windows non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-371">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="f9a4d-372">Installare le versioni di anteprima di .NET Core 3.0 in Linux con Snap</span><span class="sxs-lookup"><span data-stu-id="f9a4d-372">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="f9a4d-373">Snap è il modo preferenziale per installare e provare le anteprime di .NET Core nelle [distribuzioni di Linux che supportano Snap](https://docs.snapcraft.io/installing-snapd/6735).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-373">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="f9a4d-374">Dopo aver configurato Snap nel sistema, eseguire il comando seguente per installare [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-374">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```

<span data-ttu-id="f9a4d-375">Se .NET Core viene installato usando il pacchetto Snap, il comando di .NET Core predefinito è `dotnet-sdk.dotnet`, anziché semplicemente `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-375">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="f9a4d-376">Il vantaggio del comando con spazio dei nomi è che non si verificheranno conflitti con una versione di .NET Core installata a livello globale eventualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-376">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="f9a4d-377">È possibile definire l'alias `dotnet` per questo comando con:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-377">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="f9a4d-378">Alcune distribuzioni richiedono un altro passaggio per abilitare l'accesso al certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-378">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="f9a4d-379">Vedere la [documentazione sulla configurazione di Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-379">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="f9a4d-380">Supporto di GPIO per Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="f9a4d-380">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="f9a4d-381">Sono stati rilasciati due nuovi pacchetti NuGet che è possibile usare per la programmazione GPIO.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-381">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="f9a4d-382">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="f9a4d-382">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="f9a4d-383">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="f9a4d-383">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="f9a4d-384">I pacchetti GPIO includono le API per i dispositivi GPIO, SPI, I2C e PWM.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-384">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="f9a4d-385">Il pacchetto di associazioni IoT include [associazioni di dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/README.md) per i vari chip e sensori, gli stessi disponibili in[dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-385">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="f9a4d-386">Le API per le porte seriali aggiornate, annunciate per .NET Core 3.0 Preview 1, non fanno parte di questi pacchetti ma sono disponibili come parte della piattaforma .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-386">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>

## <a name="platform-support"></a><span data-ttu-id="f9a4d-387">Supporto per piattaforme</span><span class="sxs-lookup"><span data-stu-id="f9a4d-387">Platform Support</span></span>

<span data-ttu-id="f9a4d-388">.NET Core 3 sarà supportato nei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-388">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="f9a4d-389">Client Windows: 7, 8.1, 10 (1607+)</span><span class="sxs-lookup"><span data-stu-id="f9a4d-389">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="f9a4d-390">Windows Server: 2012 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-390">Windows Server: 2012 R2 SP1+</span></span>
* <span data-ttu-id="f9a4d-391">macOS: 10.12+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-391">macOS: 10.12+</span></span>
* <span data-ttu-id="f9a4d-392">RHEL: 6+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-392">RHEL: 6+</span></span>
* <span data-ttu-id="f9a4d-393">Fedora: 26+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-393">Fedora: 26+</span></span>
* <span data-ttu-id="f9a4d-394">Ubuntu: 16.04+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-394">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="f9a4d-395">Debian: 9+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-395">Debian: 9+</span></span>
* <span data-ttu-id="f9a4d-396">SLES: 12+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-396">SLES: 12+</span></span>
* <span data-ttu-id="f9a4d-397">openSUSE: 42.3+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-397">openSUSE: 42.3+</span></span>
* <span data-ttu-id="f9a4d-398">Alpine: 3.8+</span><span class="sxs-lookup"><span data-stu-id="f9a4d-398">Alpine: 3.8+</span></span>

<span data-ttu-id="f9a4d-399">Il supporto dei chip è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f9a4d-399">Chip support follows:</span></span>

* <span data-ttu-id="f9a4d-400">x64 in Windows, macOS e Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-400">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="f9a4d-401">x86 in Windows</span><span class="sxs-lookup"><span data-stu-id="f9a4d-401">x86 on Windows</span></span>
* <span data-ttu-id="f9a4d-402">ARM32 in Windows e Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-402">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="f9a4d-403">ARM64 in Linux</span><span class="sxs-lookup"><span data-stu-id="f9a4d-403">ARM64 on Linux</span></span>

<span data-ttu-id="f9a4d-404">Per Linux, ARM32 è supportato in Debian 9+ e Ubuntu 16.04+.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-404">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="f9a4d-405">Per ARM64, è uguale a ARM32 con l'aggiunta di Alpine 3.8.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-405">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="f9a4d-406">Queste sono le stesse versioni di tali distribuzioni supportate per x64.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-406">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="f9a4d-407">Le immagini Docker per .NET Core 3.0 sono disponibili in [microsoft/dotnet nell'Hub Docker](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="f9a4d-407">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="f9a4d-408">È in corso il processo di adozione di [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) ed è previsto che le immagini finali di .NET Core 3.0 vengano pubblicate solo in MCR.</span><span class="sxs-lookup"><span data-stu-id="f9a4d-408">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
