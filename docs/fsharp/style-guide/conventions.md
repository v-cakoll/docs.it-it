---
title: Convenzioni di codifica F#
description: Informazioni su linee guida generali e idiomi F# per la scrittura di codice.
ms.date: 01/15/2020
ms.openlocfilehash: ca86bcf714d2fb4ee5f173ee54ba12c317f9abe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737818"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="50896-103">Convenzioni di codifica F#</span><span class="sxs-lookup"><span data-stu-id="50896-103">F# coding conventions</span></span>

<span data-ttu-id="50896-104">Le convenzioni seguenti sono formulate dall'esperienza di utilizzo F# di codebase di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="50896-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="50896-105">I [cinque principi del codice F# valido](index.md#five-principles-of-good-f-code) sono la base di ogni raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="50896-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="50896-106">Sono correlati alle [ F# linee guida di progettazione dei componenti](component-design-guidelines.md), ma sono applicabili a F# qualsiasi codice, non solo a componenti come le librerie.</span><span class="sxs-lookup"><span data-stu-id="50896-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="50896-107">Organizzazione del codice</span><span class="sxs-lookup"><span data-stu-id="50896-107">Organizing code</span></span>

<span data-ttu-id="50896-108">F#in sono disponibili due modalità principali per organizzare il codice: moduli e spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="50896-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="50896-109">Queste sono simili, ma presentano le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="50896-110">Gli spazi dei nomi vengono compilati come spazi dei nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="50896-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="50896-111">I moduli vengono compilati come classi statiche.</span><span class="sxs-lookup"><span data-stu-id="50896-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="50896-112">Gli spazi dei nomi sono sempre di primo livello.</span><span class="sxs-lookup"><span data-stu-id="50896-112">Namespaces are always top level.</span></span> <span data-ttu-id="50896-113">I moduli possono essere di primo livello e annidati all'interno di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="50896-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="50896-114">Gli spazi dei nomi possono estendersi su più file.</span><span class="sxs-lookup"><span data-stu-id="50896-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="50896-115">I moduli non possono.</span><span class="sxs-lookup"><span data-stu-id="50896-115">Modules cannot.</span></span>
* <span data-ttu-id="50896-116">I moduli possono essere decorati con `[<RequireQualifiedAccess>]` e `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="50896-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="50896-117">Le linee guida seguenti consentiranno di usare questi elementi per organizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="50896-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="50896-118">Preferire gli spazi dei nomi al livello superiore</span><span class="sxs-lookup"><span data-stu-id="50896-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="50896-119">Per qualsiasi codice utilizzabile pubblicamente, gli spazi dei nomi sono preferenziali per i moduli al livello superiore.</span><span class="sxs-lookup"><span data-stu-id="50896-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="50896-120">Poiché sono compilati come spazi dei nomi .NET, sono utilizzabili C# da senza problemi.</span><span class="sxs-lookup"><span data-stu-id="50896-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="50896-121">L'uso di un modulo di primo livello potrebbe non essere diverso quando viene F#chiamato solo da C# , ma per gli utenti, i chiamanti possono essere sorpresi con la necessità di qualificare `MyClass` con il modulo di `MyCode`.</span><span class="sxs-lookup"><span data-stu-id="50896-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="50896-122">Applicare con attenzione `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="50896-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="50896-123">Il costrutto di `[<AutoOpen>]` può inquinare l'ambito di ciò che è disponibile per i chiamanti e la risposta da cui provengono gli elementi sono "Magic".</span><span class="sxs-lookup"><span data-stu-id="50896-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="50896-124">Questo non è un aspetto positivo.</span><span class="sxs-lookup"><span data-stu-id="50896-124">This is not a good thing.</span></span> <span data-ttu-id="50896-125">Un'eccezione a questa regola è rappresentata dalla F# libreria principale, anche se questo fatto è anche un po' controversa.</span><span class="sxs-lookup"><span data-stu-id="50896-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="50896-126">Tuttavia, si tratta di una praticità se si dispone di funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.</span><span class="sxs-lookup"><span data-stu-id="50896-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="50896-127">In questo modo è possibile separare correttamente i dettagli di implementazione dall'API pubblica di una funzione senza dover qualificare completamente un helper ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="50896-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="50896-128">Inoltre, l'esposizione di metodi di estensione e generatori di espressioni a livello di spazio dei nomi può essere espressa in modo accurato con `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="50896-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="50896-129">Usare `[<RequireQualifiedAccess>]` ogni volta che i nomi possono essere in conflitto o si ritiene che contribuisca alla leggibilità</span><span class="sxs-lookup"><span data-stu-id="50896-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="50896-130">L'aggiunta dell'attributo `[<RequireQualifiedAccess>]` a un modulo indica che il modulo potrebbe non essere aperto e che i riferimenti agli elementi del modulo richiedono un accesso qualificato esplicito.</span><span class="sxs-lookup"><span data-stu-id="50896-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="50896-131">Ad esempio, il modulo `Microsoft.FSharp.Collections.List` dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="50896-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="50896-132">Questa operazione è utile quando le funzioni e i valori nel modulo hanno nomi che probabilmente sono in conflitto con i nomi in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="50896-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="50896-133">La richiesta di accesso qualificato può aumentare significativamente la gestibilità a lungo termine e la evolvibilità di una libreria.</span><span class="sxs-lookup"><span data-stu-id="50896-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="50896-134">Ordinare `open` istruzioni in modo topologico</span><span class="sxs-lookup"><span data-stu-id="50896-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="50896-135">In F#, l'ordine delle dichiarazioni è importante, incluso con le istruzioni `open`.</span><span class="sxs-lookup"><span data-stu-id="50896-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="50896-136">Questo è diverso da C#, in cui l'effetto di `using` e `using static` è indipendente dall'ordine di tali istruzioni in un file.</span><span class="sxs-lookup"><span data-stu-id="50896-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="50896-137">In F#gli elementi aperti in un ambito possono nascondere altri elementi già presenti.</span><span class="sxs-lookup"><span data-stu-id="50896-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="50896-138">Questo significa che il riordino di `open` le istruzioni potrebbe modificare il significato del codice.</span><span class="sxs-lookup"><span data-stu-id="50896-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="50896-139">Di conseguenza, non è consigliabile usare qualsiasi ordinamento arbitrario di tutte le istruzioni `open` (ad esempio, in modo alfanumerico), perché non si genera un comportamento diverso che ci si potrebbe aspettare.</span><span class="sxs-lookup"><span data-stu-id="50896-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="50896-140">È invece consigliabile ordinarle in modo [topologico](https://en.wikipedia.org/wiki/Topological_sorting); ovvero ordinare le istruzioni `open` nell'ordine in cui sono definiti i _livelli_ del sistema.</span><span class="sxs-lookup"><span data-stu-id="50896-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="50896-141">È anche possibile prendere in considerazione l'ordinamento alfanumerico in livelli topologici diversi.</span><span class="sxs-lookup"><span data-stu-id="50896-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="50896-142">Ecco ad esempio l'ordinamento topologico per il F# file API pubblico del servizio del compilatore:</span><span class="sxs-lookup"><span data-stu-id="50896-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="50896-143">Si noti che un'interruzioni di riga separa i livelli topologici, in cui ogni livello viene ordinato in ordine alfanumerico in seguito.</span><span class="sxs-lookup"><span data-stu-id="50896-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="50896-144">In questo modo, il codice viene organizzato in modo semplice senza ombreggiatura accidentale dei valori.</span><span class="sxs-lookup"><span data-stu-id="50896-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="50896-145">Usare classi per contenere valori con effetti collaterali</span><span class="sxs-lookup"><span data-stu-id="50896-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="50896-146">In molti casi l'inizializzazione di un valore può avere effetti collaterali, ad esempio la creazione di un'istanza di un contesto in un database o in un'altra risorsa remota.</span><span class="sxs-lookup"><span data-stu-id="50896-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="50896-147">Si tenta di inizializzare tali elementi in un modulo e di utilizzarlo nelle funzioni successive:</span><span class="sxs-lookup"><span data-stu-id="50896-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="50896-148">Spesso si tratta di una cattiva idea per alcuni motivi:</span><span class="sxs-lookup"><span data-stu-id="50896-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="50896-149">Per prima cosa, viene effettuato il push della configurazione dell'applicazione nella codebase con `dep1` e `dep2`.</span><span class="sxs-lookup"><span data-stu-id="50896-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="50896-150">Questa operazione è difficile da gestire nelle codebase più grandi.</span><span class="sxs-lookup"><span data-stu-id="50896-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="50896-151">In secondo luogo, i dati inizializzati staticamente non devono includere valori non thread-safe se il componente utilizzerà più thread.</span><span class="sxs-lookup"><span data-stu-id="50896-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="50896-152">Questo è chiaramente violato da `dep3`.</span><span class="sxs-lookup"><span data-stu-id="50896-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="50896-153">Infine, l'inizializzazione del modulo viene compilata in un costruttore statico per l'intera unità di compilazione.</span><span class="sxs-lookup"><span data-stu-id="50896-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="50896-154">Se si verifica un errore durante l'inizializzazione del valore associato al limite, si manifesterà come un `TypeInitializationException` che viene quindi memorizzato nella cache per l'intera durata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="50896-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="50896-155">Questa operazione può essere difficile da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="50896-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="50896-156">Esiste in genere un'eccezione interna a cui è possibile tentare di ragionare, ma in caso contrario, non viene indicato quale sia la causa principale.</span><span class="sxs-lookup"><span data-stu-id="50896-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="50896-157">In alternativa, è sufficiente usare una classe semplice per mantenere le dipendenze:</span><span class="sxs-lookup"><span data-stu-id="50896-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="50896-158">Ciò consente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="50896-158">This enables the following:</span></span>

1. <span data-ttu-id="50896-159">Push di qualsiasi stato dipendente al di fuori dell'API stessa.</span><span class="sxs-lookup"><span data-stu-id="50896-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="50896-160">È ora possibile eseguire la configurazione al di fuori dell'API.</span><span class="sxs-lookup"><span data-stu-id="50896-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="50896-161">Gli errori nell'inizializzazione per i valori dipendenti non possono essere manifesti come `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="50896-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="50896-162">L'API è ora più facile da testare.</span><span class="sxs-lookup"><span data-stu-id="50896-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="50896-163">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="50896-163">Error management</span></span>

<span data-ttu-id="50896-164">La gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e sfumata e non ci sono Bulletti Silver per garantire che i sistemi siano a tolleranza d'errore e si comportino correttamente.</span><span class="sxs-lookup"><span data-stu-id="50896-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="50896-165">Le linee guida seguenti forniscono indicazioni per l'esplorazione di questo spazio difficile.</span><span class="sxs-lookup"><span data-stu-id="50896-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="50896-166">Rappresentano i casi di errore e lo stato non valido nei tipi intrinseci al dominio</span><span class="sxs-lookup"><span data-stu-id="50896-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="50896-167">Con le [unioni discriminate](../language-reference/discriminated-unions.md), F# offre la possibilità di rappresentare lo stato del programma difettoso nel sistema di tipi.</span><span class="sxs-lookup"><span data-stu-id="50896-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="50896-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50896-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="50896-169">In questo caso, è possibile che si verifichino tre modi noti per ritirare denaro da un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="50896-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="50896-170">Ogni caso di errore è rappresentato nel tipo e può quindi essere gestito in modo sicuro in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="50896-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="50896-171">In generale, se è possibile modellare i diversi modi in cui un problema può **avere esito negativo** nel dominio, il codice di gestione degli errori non viene più considerato come un elemento che è necessario gestire oltre al normale flusso di programma.</span><span class="sxs-lookup"><span data-stu-id="50896-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="50896-172">È semplicemente una parte del normale flusso di programma e non è considerata **eccezionale**.</span><span class="sxs-lookup"><span data-stu-id="50896-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="50896-173">Questa operazione presenta due vantaggi principali:</span><span class="sxs-lookup"><span data-stu-id="50896-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="50896-174">È più facile da gestire quando il dominio cambia nel tempo.</span><span class="sxs-lookup"><span data-stu-id="50896-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="50896-175">I casi di errore sono più facili da unit test.</span><span class="sxs-lookup"><span data-stu-id="50896-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="50896-176">Usare le eccezioni quando non è possibile rappresentare gli errori con i tipi</span><span class="sxs-lookup"><span data-stu-id="50896-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="50896-177">Non tutti gli errori possono essere rappresentati in un dominio di problema.</span><span class="sxs-lookup"><span data-stu-id="50896-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="50896-178">Questi tipi di errori sono di natura *eccezionale* , quindi la possibilità di generare e rilevare eccezioni in F#.</span><span class="sxs-lookup"><span data-stu-id="50896-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="50896-179">Prima di tutto, è consigliabile leggere le [linee guida](../../standard/design-guidelines/exceptions.md)per la progettazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="50896-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="50896-180">Sono applicabili anche a F#.</span><span class="sxs-lookup"><span data-stu-id="50896-180">These are also applicable to F#.</span></span>

<span data-ttu-id="50896-181">I costrutti principali disponibili in F# ai fini della generazione di eccezioni devono essere considerati nell'ordine di preferenza seguente:</span><span class="sxs-lookup"><span data-stu-id="50896-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="50896-182">Funzione</span><span class="sxs-lookup"><span data-stu-id="50896-182">Function</span></span> | <span data-ttu-id="50896-183">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50896-183">Syntax</span></span> | <span data-ttu-id="50896-184">Scopo</span><span class="sxs-lookup"><span data-stu-id="50896-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="50896-185">Genera un `System.ArgumentNullException` con il nome dell'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="50896-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="50896-186">Genera un `System.ArgumentException` con un nome e un messaggio di argomento specificati.</span><span class="sxs-lookup"><span data-stu-id="50896-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="50896-187">Genera un `System.InvalidOperationException` con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="50896-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="50896-188">Meccanismo di utilizzo generale per la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="50896-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="50896-189">Genera un `System.Exception` con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="50896-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="50896-190">Genera un `System.Exception` con un messaggio determinato dalla stringa di formato e dai relativi input.</span><span class="sxs-lookup"><span data-stu-id="50896-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="50896-191">Utilizzare `nullArg`, `invalidArg` e `invalidOp` come meccanismo per generare `ArgumentNullException`, `ArgumentException` e `InvalidOperationException` quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="50896-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="50896-192">È in genere consigliabile evitare le funzioni `failwith` e `failwithf` perché generano il tipo di `Exception` di base, non un'eccezione specifica.</span><span class="sxs-lookup"><span data-stu-id="50896-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="50896-193">Come per le [linee guida di progettazione delle eccezioni](../../standard/design-guidelines/exceptions.md), si desidera generare eccezioni più specifiche quando possibile.</span><span class="sxs-lookup"><span data-stu-id="50896-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="50896-194">Uso della sintassi di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="50896-194">Using exception-handling syntax</span></span>

<span data-ttu-id="50896-195">F#supporta i modelli di eccezione tramite la sintassi `try...with`:</span><span class="sxs-lookup"><span data-stu-id="50896-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="50896-196">La riconciliazione delle funzionalità da eseguire in caso di eccezione con criteri di ricerca può risultare un po' difficile se si desidera che il codice venga pulito.</span><span class="sxs-lookup"><span data-stu-id="50896-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="50896-197">Un modo per gestire questa situazione consiste nell'usare i [criteri attivi](../language-reference/active-patterns.md) come mezzo per raggruppare le funzionalità che racchiudono un caso di errore con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="50896-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="50896-198">È possibile, ad esempio, che si stia consumando un'API che, quando viene generata un'eccezione, racchiuda informazioni importanti nei metadati dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="50896-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="50896-199">L'annullamento del wrapping di un valore utile nel corpo dell'eccezione acquisita all'interno del criterio attivo e la restituzione di tale valore può essere utile in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="50896-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="50896-200">Non utilizzare la gestione di errori monadici per sostituire le eccezioni</span><span class="sxs-lookup"><span data-stu-id="50896-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="50896-201">Le eccezioni vengono considerate un tabù nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="50896-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="50896-202">In realtà, le eccezioni violano la purezza, quindi è sicuro considerarle non molto funzionanti.</span><span class="sxs-lookup"><span data-stu-id="50896-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="50896-203">Tuttavia, in questo modo si ignora la realtà in cui il codice deve essere eseguito e possono verificarsi errori di Runtime.</span><span class="sxs-lookup"><span data-stu-id="50896-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="50896-204">In generale, scrivere codice sul presupposto che la maggior parte degli elementi non sia pura né totale, per ridurre al minimo le sorprese spiacevoli.</span><span class="sxs-lookup"><span data-stu-id="50896-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="50896-205">È importante considerare i seguenti punti di forza/aspetti delle eccezioni in relazione alla pertinenza e all'idoneità nel Runtime .NET e nell'ecosistema tra più linguaggi:</span><span class="sxs-lookup"><span data-stu-id="50896-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="50896-206">Contengono informazioni di diagnostica dettagliate, molto utili per il debug di un problema.</span><span class="sxs-lookup"><span data-stu-id="50896-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="50896-207">Sono ben comprensibili per il runtime e altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="50896-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="50896-208">Possono ridurre lo standard significativo se confrontato con il codice che non viene più utilizzato per *evitare* eccezioni implementando alcuni subset della loro semantica in modo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="50896-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="50896-209">Questo terzo punto è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="50896-209">This third point is critical.</span></span> <span data-ttu-id="50896-210">Per operazioni complesse non semplici, l'impossibilità di usare le eccezioni può comportare la gestione di strutture come le seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="50896-211">In questo modo è possibile ottenere facilmente codice fragile, ad esempio i criteri di ricerca sugli errori "tipizzati in modo stringa":</span><span class="sxs-lookup"><span data-stu-id="50896-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="50896-212">Inoltre, può essere tentata di inghiottire qualsiasi eccezione nel desiderio di una funzione "semplice" che restituisce un tipo "più gradevole":</span><span class="sxs-lookup"><span data-stu-id="50896-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="50896-213">Sfortunatamente, `tryReadAllText` possibile generare numerose eccezioni in base alla miriade di elementi che possono verificarsi in un file system e questo codice elimina tutte le informazioni sul problema che potrebbe essere effettivamente errato nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="50896-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="50896-214">Se si sostituisce questo codice con un tipo di risultato, si tornerà all'analisi dei messaggi di errore "stringa tipizzata":</span><span class="sxs-lookup"><span data-stu-id="50896-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="50896-215">L'inserimento dell'oggetto eccezione nel costruttore `Error` impone semplicemente di gestire correttamente il tipo di eccezione nel sito di chiamata anziché nella funzione.</span><span class="sxs-lookup"><span data-stu-id="50896-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="50896-216">Questa operazione crea efficacemente le eccezioni controllate, che sono notoriamente Unfun per gestire come un chiamante di un'API.</span><span class="sxs-lookup"><span data-stu-id="50896-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="50896-217">Una valida alternativa agli esempi precedenti è l'intercettazione di eccezioni *specifiche* e la restituzione di un valore significativo nel contesto di tale eccezione.</span><span class="sxs-lookup"><span data-stu-id="50896-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="50896-218">Se si modifica la funzione `tryReadAllText` come indicato di seguito, `None` ha un significato maggiore:</span><span class="sxs-lookup"><span data-stu-id="50896-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="50896-219">Anziché funzionare come catch-all, questa funzione gestirà correttamente il caso in cui un file non è stato trovato e assegna tale significato a un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="50896-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="50896-220">Questo valore restituito può essere mappato a tale caso di errore, senza scartare eventuali informazioni contestuali o forzare i chiamanti a gestire un caso che potrebbe non essere pertinente in quel punto del codice.</span><span class="sxs-lookup"><span data-stu-id="50896-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="50896-221">I tipi come `Result<'Success, 'Error>` sono appropriati per le operazioni di base in cui non sono F# annidati e i tipi facoltativi sono perfetti per la rappresentazione quando un elemento può restituire *qualcosa* o *nulla*.</span><span class="sxs-lookup"><span data-stu-id="50896-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="50896-222">Non sono tuttavia una sostituzione per le eccezioni e non devono essere usate nel tentativo di sostituire le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="50896-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="50896-223">Ma devono essere applicati in modo sensato per risolvere specifici aspetti dei criteri di gestione degli errori e delle eccezioni in modi mirati.</span><span class="sxs-lookup"><span data-stu-id="50896-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="50896-224">Programmazione parziale di applicazioni e senza punto</span><span class="sxs-lookup"><span data-stu-id="50896-224">Partial application and point-free programming</span></span>

<span data-ttu-id="50896-225">F#supporta applicazioni parziali e, di conseguenza, diversi modi per programmare in uno stile senza punto.</span><span class="sxs-lookup"><span data-stu-id="50896-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="50896-226">Questo può essere utile per il riutilizzo del codice all'interno di un modulo o l'implementazione di un elemento, ma non è un elemento da esporre pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="50896-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="50896-227">In generale, la programmazione senza punti non è una virtù di per sé e può aggiungere una barriera cognitiva significativa per gli utenti che non sono immersi nello stile.</span><span class="sxs-lookup"><span data-stu-id="50896-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="50896-228">Non usare applicazioni parziali e currying nelle API pubbliche</span><span class="sxs-lookup"><span data-stu-id="50896-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="50896-229">Con poche eccezioni, l'uso di applicazioni parziali in API pubbliche può creare confusione per i consumer.</span><span class="sxs-lookup"><span data-stu-id="50896-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="50896-230">In genere, i valori associati a F# `let`nel codice sono **valori**, non **valori di funzione**.</span><span class="sxs-lookup"><span data-stu-id="50896-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="50896-231">La combinazione di valori e valori di funzione può comportare il salvataggio di un numero ridotto di righe di codice in Exchange per un notevole sovraccarico cognitivo, soprattutto se combinato con operatori quali `>>` per comporre funzioni.</span><span class="sxs-lookup"><span data-stu-id="50896-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="50896-232">Considerare le implicazioni degli strumenti per la programmazione senza punti</span><span class="sxs-lookup"><span data-stu-id="50896-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="50896-233">Le funzioni sottoposte a currying non etichettano gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="50896-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="50896-234">Questa operazione ha implicazioni sugli strumenti.</span><span class="sxs-lookup"><span data-stu-id="50896-234">This has tooling implications.</span></span> <span data-ttu-id="50896-235">Prendere in considerazione le due funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="50896-236">Entrambe sono funzioni valide, ma `funcWithApplication` è una funzione sottoposta a currying.</span><span class="sxs-lookup"><span data-stu-id="50896-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="50896-237">Quando si passa il mouse sui tipi in un editor, viene visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="50896-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="50896-238">Nel sito di chiamata, le descrizioni comandi degli strumenti, ad esempio Visual Studio, non forniranno informazioni significative per quanto riguarda effettivamente i tipi di input `string` e `int`.</span><span class="sxs-lookup"><span data-stu-id="50896-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="50896-239">Se si riscontra codice senza punti, ad esempio `funcWithApplication` che può essere utilizzato pubblicamente, è consigliabile eseguire un'espansione η completa, in modo che gli strumenti possano prelevare nomi significativi per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="50896-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="50896-240">Inoltre, il debug del codice senza punto può risultare complesso, se non è impossibile.</span><span class="sxs-lookup"><span data-stu-id="50896-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="50896-241">Gli strumenti di debug si basano sui valori associati ai nomi, ad esempio `let` bindings, in modo da poter ispezionare i valori intermedi a metà dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50896-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="50896-242">Quando il codice non ha valori da ispezionare, non è necessario eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="50896-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="50896-243">In futuro, gli strumenti di debug possono evolversi per sintetizzare questi valori in base ai percorsi eseguiti in precedenza, ma non è una scelta ideale per coprire le scommesse sulle *potenziali* funzionalità di debug.</span><span class="sxs-lookup"><span data-stu-id="50896-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="50896-244">Si consideri un'applicazione parziale come tecnica per ridurre lo standard interno</span><span class="sxs-lookup"><span data-stu-id="50896-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="50896-245">A differenza del punto precedente, l'applicazione parziale è uno strumento straordinario per la riduzione di standard all'interno di un'applicazione o degli elementi interni più profondi di un'API.</span><span class="sxs-lookup"><span data-stu-id="50896-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="50896-246">Può essere utile per eseguire unit test dell'implementazione di API più complesse, dove lo standard è spesso un problema da affrontare.</span><span class="sxs-lookup"><span data-stu-id="50896-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="50896-247">Il codice seguente, ad esempio, Mostra come è possibile eseguire la maggior parte dei framework di simulazione senza assumere una dipendenza esterna su un Framework di questo tipo ed è necessario apprendere un'API su misura correlata.</span><span class="sxs-lookup"><span data-stu-id="50896-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="50896-248">Si consideri ad esempio la seguente topografia di soluzioni:</span><span class="sxs-lookup"><span data-stu-id="50896-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="50896-249">`ImplementationLogic.fsproj` possibile esporre codice, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="50896-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="50896-250">Il testing unità `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` è facile:</span><span class="sxs-lookup"><span data-stu-id="50896-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="50896-251">L'applicazione parziale di `doTransaction` con un oggetto contesto fittizio consente di chiamare la funzione in tutti gli unit test senza la necessità di creare un contesto fittizio ogni volta:</span><span class="sxs-lookup"><span data-stu-id="50896-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="50896-252">Questa tecnica non deve essere applicata universalmente all'intera codebase, ma è un modo efficace per ridurre gli standard per gli elementi interni complessi e per il testing degli unit test.</span><span class="sxs-lookup"><span data-stu-id="50896-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="50896-253">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="50896-253">Access control</span></span>

<span data-ttu-id="50896-254">F#include più opzioni per il [controllo di accesso](../language-reference/access-control.md), ereditate da quanto disponibile nel Runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="50896-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="50896-255">Questi non sono semplicemente utilizzabili per i tipi. è anche possibile usarli per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="50896-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="50896-256">Preferisce i tipi e i membri non`public` fino a quando non sono necessari per essere pubblicamente utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="50896-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="50896-257">Ciò consente anche di ridurre al minimo le coppie di consumer.</span><span class="sxs-lookup"><span data-stu-id="50896-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="50896-258">Si impegna a garantire la `private`di tutte le funzionalità di supporto.</span><span class="sxs-lookup"><span data-stu-id="50896-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="50896-259">Si consideri l'uso di `[<AutoOpen>]` in un modulo privato di funzioni helper se diventano numerose.</span><span class="sxs-lookup"><span data-stu-id="50896-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="50896-260">Inferenza del tipo e generics</span><span class="sxs-lookup"><span data-stu-id="50896-260">Type inference and generics</span></span>

<span data-ttu-id="50896-261">L'inferenza del tipo può evitare di digitare una grande quantità di standard.</span><span class="sxs-lookup"><span data-stu-id="50896-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="50896-262">E la generalizzazione automatica nel F# compilatore può essere utile per scrivere codice più generico senza alcuna ulteriore operazione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50896-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="50896-263">Tuttavia, queste funzionalità non sono universalmente valide.</span><span class="sxs-lookup"><span data-stu-id="50896-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="50896-264">È consigliabile assegnare etichette ai nomi degli argomenti con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza del tipo per.</span><span class="sxs-lookup"><span data-stu-id="50896-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="50896-265">Il motivo **è che è necessario avere** il controllo della forma dell'API, non del compilatore.</span><span class="sxs-lookup"><span data-stu-id="50896-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="50896-266">Sebbene il compilatore possa eseguire un processo ottimale per l'inferenza dei tipi, è possibile che la forma dell'API venga modificata se gli elementi interni sui quali si basano i tipi modificati.</span><span class="sxs-lookup"><span data-stu-id="50896-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="50896-267">Questo potrebbe essere quello che si desidera, ma quasi certamente comporterà una modifica dell'API di rilievo che i consumer downstream dovranno gestire.</span><span class="sxs-lookup"><span data-stu-id="50896-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="50896-268">Se invece si controlla in modo esplicito la forma dell'API pubblica, è possibile controllare queste modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="50896-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="50896-269">Nei termini DDD, questo può essere considerato come un livello Anti-danneggiamento.</span><span class="sxs-lookup"><span data-stu-id="50896-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="50896-270">Provare a assegnare un nome significativo agli argomenti generici.</span><span class="sxs-lookup"><span data-stu-id="50896-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="50896-271">A meno che non si stia scrivendo codice realmente generico che non è specifico di un determinato dominio, un nome significativo può aiutare gli altri programmatori a comprendere il dominio in cui stanno lavorando.</span><span class="sxs-lookup"><span data-stu-id="50896-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="50896-272">Ad esempio, un parametro di tipo denominato `'Document` nel contesto dell'interazione con un database di documenti rende più chiaro che i tipi di documenti generici possono essere accettati dalla funzione o dal membro che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="50896-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="50896-273">Prendere in considerazione la denominazione di parametri di tipo generico con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="50896-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="50896-274">Questo è il modo generale per eseguire operazioni in .NET, quindi è consigliabile usare PascalCase anziché snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="50896-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="50896-275">Infine, la generalizzazione automatica non è sempre un vantaggio per gli utenti che non F# hanno familiarità con o con una codebase di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="50896-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="50896-276">L'utilizzo di componenti generici comporta un sovraccarico cognitivo.</span><span class="sxs-lookup"><span data-stu-id="50896-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="50896-277">Inoltre, se le funzioni generalizzate automaticamente non vengono usate con tipi di input diversi (indipendentemente dal fatto che siano destinate a essere usate come tali), non vi è alcun vantaggio reale che sia generico in quel momento.</span><span class="sxs-lookup"><span data-stu-id="50896-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="50896-278">Tenere sempre presente che il codice che si sta scrivendo trarrà vantaggio dal fatto che sia generico.</span><span class="sxs-lookup"><span data-stu-id="50896-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="50896-279">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="50896-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="50896-280">Preferire gli struct per i tipi di dati di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="50896-280">Prefer structs for small data types</span></span>

<span data-ttu-id="50896-281">L'uso di struct (detti anche tipi di valore) può spesso comportare prestazioni più elevate per il codice, perché in genere evita l'allocazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="50896-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="50896-282">Tuttavia, gli struct non sono sempre un pulsante "Go Faster": se le dimensioni dei dati in uno struct superano i 16 byte, la copia dei dati può spesso comportare un tempo di utilizzo maggiore della CPU rispetto all'utilizzo di un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="50896-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="50896-283">Per determinare se è necessario usare uno struct, tenere presenti le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="50896-284">Se le dimensioni dei dati sono pari a 16 byte o inferiori.</span><span class="sxs-lookup"><span data-stu-id="50896-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="50896-285">Se è probabile che molti di questi tipi di dati siano residenti in memoria in un programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50896-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="50896-286">Se si applica la prima condizione, in genere è consigliabile usare uno struct.</span><span class="sxs-lookup"><span data-stu-id="50896-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="50896-287">Se si applicano entrambe le condizioni, è consigliabile utilizzare quasi sempre uno struct.</span><span class="sxs-lookup"><span data-stu-id="50896-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="50896-288">Potrebbero esserci casi in cui si applicano le condizioni precedenti, ma l'uso di uno struct non è migliore o peggiore rispetto all'uso di un tipo riferimento, ma è probabile che sia raro.</span><span class="sxs-lookup"><span data-stu-id="50896-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="50896-289">È importante misurare sempre quando si apportano modifiche come questa, ma non agire su presupposto o intuizione.</span><span class="sxs-lookup"><span data-stu-id="50896-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="50896-290">Preferisci Tuple struct quando si raggruppano tipi valore piccoli</span><span class="sxs-lookup"><span data-stu-id="50896-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="50896-291">Prendere in considerazione le due funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="50896-292">Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che la funzione `runWithStructTuple` che usa le tuple struct viene eseguita più velocemente del 40% e non alloca memoria.</span><span class="sxs-lookup"><span data-stu-id="50896-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="50896-293">Tuttavia, questi risultati non sono sempre il caso nel codice.</span><span class="sxs-lookup"><span data-stu-id="50896-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="50896-294">Se si contrassegna una funzione come `inline`, il codice che usa le tuple di riferimento può ottenere alcune ottimizzazioni aggiuntive oppure il codice che verrebbe allocato potrebbe essere semplicemente ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="50896-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="50896-295">È consigliabile misurare sempre i risultati ogni volta che le prestazioni sono interessate e non funzionano mai in base a presupposti o all'intuizione.</span><span class="sxs-lookup"><span data-stu-id="50896-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="50896-296">Preferire i record struct quando il tipo di dati è ridotto</span><span class="sxs-lookup"><span data-stu-id="50896-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="50896-297">La regola empirica descritta in precedenza include anche [ F# ](../language-reference/records.md)per i tipi di record.</span><span class="sxs-lookup"><span data-stu-id="50896-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="50896-298">Considerare i tipi di dati e le funzioni seguenti che li elaborano:</span><span class="sxs-lookup"><span data-stu-id="50896-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="50896-299">Questa operazione è simile al codice della tupla precedente, ma questa volta nell'esempio vengono usati i record e una funzione interna inline.</span><span class="sxs-lookup"><span data-stu-id="50896-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="50896-300">Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `processStructPoint` viene eseguito quasi il 60% più velocemente e non alloca nulla nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="50896-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="50896-301">Preferisce le unioni discriminate struct quando il tipo di dati è ridotto</span><span class="sxs-lookup"><span data-stu-id="50896-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="50896-302">Le osservazioni precedenti sulle prestazioni con tuple e record di struct contengono anche per [ F# le unioni discriminate](../language-reference/discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="50896-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="50896-303">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="50896-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string
    
    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="50896-304">È comune definire unioni discriminate a caso singolo come questa per la modellazione di dominio.</span><span class="sxs-lookup"><span data-stu-id="50896-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="50896-305">Quando si esegue il benchmark di queste funzioni con uno strumento di benchmark statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `structReverseName` viene eseguito circa il 25% più velocemente rispetto `reverseName` per le stringhe di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="50896-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="50896-306">Per le stringhe di grandi dimensioni, entrambe le prestazioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="50896-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="50896-307">Quindi, in questo caso, è sempre preferibile usare uno struct.</span><span class="sxs-lookup"><span data-stu-id="50896-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="50896-308">Come indicato in precedenza, misurare sempre e non operare su presupposti o intuizioni.</span><span class="sxs-lookup"><span data-stu-id="50896-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="50896-309">Sebbene nell'esempio precedente sia stata illustrata un'unione discriminata struct che ha prodotto prestazioni migliori, è comune disporre di unioni discriminate più grandi durante la modellazione di un dominio.</span><span class="sxs-lookup"><span data-stu-id="50896-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="50896-310">I tipi di dati più grandi, ad esempio, potrebbero non funzionare anche se sono struct a seconda delle operazioni su di essi, dal momento che potrebbero essere necessarie altre operazioni di copia.</span><span class="sxs-lookup"><span data-stu-id="50896-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="50896-311">Programmazione funzionale e mutazione</span><span class="sxs-lookup"><span data-stu-id="50896-311">Functional programming and mutation</span></span>

<span data-ttu-id="50896-312">F#per impostazione predefinita, i valori non sono modificabili, che consente di evitare determinate classi di bug (soprattutto quelli che coinvolgono la concorrenza e il parallelismo).</span><span class="sxs-lookup"><span data-stu-id="50896-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="50896-313">Tuttavia, in alcuni casi, per ottenere l'efficienza ottimale (o anche ragionevole) del tempo di esecuzione o delle allocazioni di memoria, è possibile implementare una sezione di lavoro in modo ottimale tramite la mutazione sul posto dello stato.</span><span class="sxs-lookup"><span data-stu-id="50896-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="50896-314">Questa operazione è possibile in base al consenso esplicito F# con la parola chiave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="50896-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="50896-315">L'uso di `mutable` F# in può essere in contrasto con la purezza funzionale.</span><span class="sxs-lookup"><span data-stu-id="50896-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="50896-316">Questa operazione è comprensibile, ma la purezza funzionale può essere in contrasto con gli obiettivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="50896-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="50896-317">Un compromesso consiste nell'incapsulare la mutazione in modo che i chiamanti non debbano preoccuparsi di ciò che accade quando chiamano una funzione.</span><span class="sxs-lookup"><span data-stu-id="50896-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="50896-318">In questo modo è possibile scrivere un'interfaccia funzionale su un'implementazione basata sulla mutazione per il codice critico per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="50896-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="50896-319">Eseguire il wrapping del codice modificabile nelle interfacce non modificabili</span><span class="sxs-lookup"><span data-stu-id="50896-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="50896-320">Con la trasparenza referenziale come obiettivo, è fondamentale scrivere codice che non esponga la parte mutevole delle funzioni critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="50896-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="50896-321">Il codice seguente, ad esempio, implementa la funzione `Array.contains` nella F# libreria principale:</span><span class="sxs-lookup"><span data-stu-id="50896-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="50896-322">La chiamata di questa funzione più volte non comporta la modifica della matrice sottostante né la necessità di mantenere uno stato modificabile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="50896-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="50896-323">È referenzialemente trasparente, anche se quasi ogni riga di codice all'interno di essa usa la mutazione.</span><span class="sxs-lookup"><span data-stu-id="50896-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="50896-324">Considerare l'incapsulamento dei dati modificabili nelle classi</span><span class="sxs-lookup"><span data-stu-id="50896-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="50896-325">Nell'esempio precedente è stata usata una singola funzione per incapsulare le operazioni usando dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="50896-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="50896-326">Questa operazione non è sempre sufficiente per set di dati più complessi.</span><span class="sxs-lookup"><span data-stu-id="50896-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="50896-327">Considerare i set di funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50896-327">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="50896-328">Questo codice è efficiente, ma espone la struttura dei dati basata sulla mutazione che i chiamanti sono responsabili della gestione.</span><span class="sxs-lookup"><span data-stu-id="50896-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="50896-329">Questa operazione può essere racchiusa all'interno di una classe senza membri sottostanti che possono cambiare:</span><span class="sxs-lookup"><span data-stu-id="50896-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="50896-330">`Closure1Table` incapsula la struttura dei dati basata sulla mutazione sottostante, quindi non impone ai chiamanti di mantenere la struttura dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="50896-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="50896-331">Le classi sono un modo efficace per incapsulare i dati e le routine che sono basati sulla mutazione senza esporre i dettagli ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="50896-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="50896-332">Preferisci `let mutable` alle celle di riferimento</span><span class="sxs-lookup"><span data-stu-id="50896-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="50896-333">Le celle di riferimento rappresentano un modo per rappresentare il riferimento a un valore anziché il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="50896-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="50896-334">Sebbene possano essere utilizzate per codice critico per le prestazioni, non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="50896-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="50896-335">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="50896-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="50896-336">L'uso di una cella di riferimento ora "inquina" tutto il codice successivo con la necessità di dereferenziare e rifare riferimento ai dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="50896-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="50896-337">In alternativa, prendere in considerazione `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="50896-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="50896-338">Oltre all'unico punto di mutazione al centro dell'espressione lambda, tutto il resto del codice che tocca `acc` può eseguire questa operazione in modo che non sia diverso dall'utilizzo di un normale valore non modificabile associato a `let`.</span><span class="sxs-lookup"><span data-stu-id="50896-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="50896-339">In questo modo sarà più semplice cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="50896-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="50896-340">Programmazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="50896-340">Object programming</span></span>

<span data-ttu-id="50896-341">F#dispone del supporto completo per oggetti e concetti orientati a oggetti (OO).</span><span class="sxs-lookup"><span data-stu-id="50896-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="50896-342">Sebbene molti concetti di OO siano potenti e utili, non tutti sono ideali da usare.</span><span class="sxs-lookup"><span data-stu-id="50896-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="50896-343">Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità OO a un livello elevato.</span><span class="sxs-lookup"><span data-stu-id="50896-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="50896-344">**Considerare l'uso di queste funzionalità in molte situazioni:**</span><span class="sxs-lookup"><span data-stu-id="50896-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="50896-345">Notazione del punto (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="50896-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="50896-346">Membri di istanza</span><span class="sxs-lookup"><span data-stu-id="50896-346">Instance members</span></span>
* <span data-ttu-id="50896-347">Costruttori impliciti</span><span class="sxs-lookup"><span data-stu-id="50896-347">Implicit constructors</span></span>
* <span data-ttu-id="50896-348">Membri statici</span><span class="sxs-lookup"><span data-stu-id="50896-348">Static members</span></span>
* <span data-ttu-id="50896-349">Notazione indicizzatore (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="50896-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="50896-350">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="50896-350">Named and Optional arguments</span></span>
* <span data-ttu-id="50896-351">Interfacce e implementazioni di interfaccia</span><span class="sxs-lookup"><span data-stu-id="50896-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="50896-352">**Non raggiungere innanzitutto queste funzionalità, ma è possibile applicarle in modo accurato quando sono utili per risolvere un problema:**</span><span class="sxs-lookup"><span data-stu-id="50896-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="50896-353">Overload di un metodo</span><span class="sxs-lookup"><span data-stu-id="50896-353">Method overloading</span></span>
* <span data-ttu-id="50896-354">Dati modificabili incapsulati</span><span class="sxs-lookup"><span data-stu-id="50896-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="50896-355">Operatori sui tipi</span><span class="sxs-lookup"><span data-stu-id="50896-355">Operators on types</span></span>
* <span data-ttu-id="50896-356">Proprietà automatiche</span><span class="sxs-lookup"><span data-stu-id="50896-356">Auto properties</span></span>
* <span data-ttu-id="50896-357">Implementazione di `IDisposable` e `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="50896-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="50896-358">Estensioni di tipo</span><span class="sxs-lookup"><span data-stu-id="50896-358">Type extensions</span></span>
* <span data-ttu-id="50896-359">Events</span><span class="sxs-lookup"><span data-stu-id="50896-359">Events</span></span>
* <span data-ttu-id="50896-360">Strutture</span><span class="sxs-lookup"><span data-stu-id="50896-360">Structs</span></span>
* <span data-ttu-id="50896-361">Delegati</span><span class="sxs-lookup"><span data-stu-id="50896-361">Delegates</span></span>
* <span data-ttu-id="50896-362">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="50896-362">Enums</span></span>

<span data-ttu-id="50896-363">**In genere, evitare queste funzionalità, a meno che non sia necessario usarle:**</span><span class="sxs-lookup"><span data-stu-id="50896-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="50896-364">Gerarchie di tipo e ereditarietà di implementazione basate su ereditarietà</span><span class="sxs-lookup"><span data-stu-id="50896-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="50896-365">Valori null e `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="50896-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="50896-366">Preferisci composizione sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="50896-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="50896-367">La [composizione sull'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) è un idioma di lunga durata F# a cui è possibile aderire il codice valido.</span><span class="sxs-lookup"><span data-stu-id="50896-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="50896-368">Il principio fondamentale è che non esporre una classe base e forzare i chiamanti a ereditare da tale classe di base per ottenere la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="50896-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="50896-369">Usare espressioni di oggetto per implementare le interfacce se non è necessaria una classe</span><span class="sxs-lookup"><span data-stu-id="50896-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="50896-370">Le [espressioni di oggetto](../language-reference/object-expressions.md) consentono di implementare interfacce in tempo reale, associando l'interfaccia implementata a un valore senza dover eseguire questa operazione all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="50896-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="50896-371">Questa operazione è utile, soprattutto se è necessario implementare _solo_ l'interfaccia e non è necessaria una classe completa.</span><span class="sxs-lookup"><span data-stu-id="50896-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="50896-372">Ecco, ad esempio, il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di correzione del codice se è stato aggiunto un simbolo per cui non si dispone di un'istruzione `open` per:</span><span class="sxs-lookup"><span data-stu-id="50896-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="50896-373">Poiché non è necessaria alcuna classe quando si interagisce con l'API Visual Studio Code, le espressioni di oggetto sono uno strumento ideale per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="50896-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="50896-374">Sono utili anche per il testing unità, quando si vuole eseguire lo stub di un'interfaccia con routine di test in modo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="50896-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="50896-375">Prendere in considerazione abbreviazioni di tipo per abbreviare le firme</span><span class="sxs-lookup"><span data-stu-id="50896-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="50896-376">Le [abbreviazioni di tipo](../language-reference/type-abbreviations.md) sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma di funzione o un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="50896-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="50896-377">Ad esempio, l'alias seguente assegna un'etichetta a ciò che è necessario per definire un calcolo con [CNTK](https://docs.microsoft.com/cognitive-toolkit/), una libreria Deep Learning:</span><span class="sxs-lookup"><span data-stu-id="50896-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="50896-378">Il nome del `Computation` è un modo pratico per indicare qualsiasi funzione corrispondente alla firma a cui è associato l'alias.</span><span class="sxs-lookup"><span data-stu-id="50896-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="50896-379">L'uso di abbreviazioni di tipo come questo è utile e consente di scrivere codice più conciso.</span><span class="sxs-lookup"><span data-stu-id="50896-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="50896-380">Evitare di usare le abbreviazioni di tipo per rappresentare il dominio</span><span class="sxs-lookup"><span data-stu-id="50896-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="50896-381">Sebbene le abbreviazioni di tipo siano utili per assegnare un nome alle firme di funzione, possono generare confusione quando abbreviare altri tipi.</span><span class="sxs-lookup"><span data-stu-id="50896-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="50896-382">Prendere in considerazione questa abbreviazione:</span><span class="sxs-lookup"><span data-stu-id="50896-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="50896-383">Questa operazione può generare confusione in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="50896-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="50896-384">`BufferSize` non è un'astrazione; si tratta semplicemente di un altro nome per un numero intero.</span><span class="sxs-lookup"><span data-stu-id="50896-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="50896-385">Se `BufferSize` è esposto in un'API pubblica, può essere facilmente interpretato in modo non semplice da `int`.</span><span class="sxs-lookup"><span data-stu-id="50896-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="50896-386">In genere, i tipi di dominio hanno più attributi e non sono tipi primitivi come `int`.</span><span class="sxs-lookup"><span data-stu-id="50896-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="50896-387">Questa abbreviazione viola questo presupposto.</span><span class="sxs-lookup"><span data-stu-id="50896-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="50896-388">La combinazione di maiuscole e minuscole di `BufferSize` (PascalCase) implica che questo tipo contenga più dati.</span><span class="sxs-lookup"><span data-stu-id="50896-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="50896-389">Questo alias non offre una maggiore chiarezza rispetto alla fornitura di un argomento denominato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="50896-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="50896-390">L'abbreviazione non si manifesterà in IL compilato IL; si tratta semplicemente di un intero e questo alias è un costrutto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="50896-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="50896-391">In breve, il trabocchetto con abbreviazioni di tipo è che **non** sono astrazioni sui tipi che sono abbreviare.</span><span class="sxs-lookup"><span data-stu-id="50896-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="50896-392">Nell'esempio precedente `BufferSize` è semplicemente una `int` sotto le quinte, senza dati aggiuntivi, né i vantaggi del sistema di tipi oltre a ciò che `int` già.</span><span class="sxs-lookup"><span data-stu-id="50896-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="50896-393">Un approccio alternativo all'uso delle abbreviazioni di tipo per rappresentare un dominio consiste nell'usare unioni discriminate a singolo caso.</span><span class="sxs-lookup"><span data-stu-id="50896-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="50896-394">L'esempio precedente può essere modellato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="50896-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="50896-395">Se si scrive codice che opera in termini di `BufferSize` e del relativo valore sottostante, è necessario crearne uno anziché passare qualsiasi Integer arbitrario:</span><span class="sxs-lookup"><span data-stu-id="50896-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="50896-396">In questo modo si riduce la probabilità che venga erroneamente passato un numero intero arbitrario nella funzione `send`, perché il chiamante deve costruire un tipo di `BufferSize` per eseguire il wrapping di un valore prima di chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="50896-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
