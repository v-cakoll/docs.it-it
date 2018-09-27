---
title: 'Convenzioni di scrittura codice F #'
description: 'Informazioni su termini e le linee guida generali durante la scrittura di codice F #.'
ms.date: 05/14/2018
ms.openlocfilehash: b9afd1fbfbd9d8e04d9bfaa07615de045b7e05fe
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47237406"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="e49ba-103">Convenzioni di scrittura codice F #</span><span class="sxs-lookup"><span data-stu-id="e49ba-103">F# coding conventions</span></span>

<span data-ttu-id="e49ba-104">Le seguenti convenzioni vengono formulate dall'esperienza di utilizzo di grandi dimensioni F # le basi di codice.</span><span class="sxs-lookup"><span data-stu-id="e49ba-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="e49ba-105">Il [cinque principi del buon codice F #](index.md#five-principles-of-good-f-code) sono alla base di ogni raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="e49ba-106">Che sono correlati i [indicazioni per la progettazione di componente F #](component-design-guidelines.md), ma sono applicabili a qualsiasi codice F #, non solo i componenti come le librerie.</span><span class="sxs-lookup"><span data-stu-id="e49ba-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="e49ba-107">Organizzazione del codice</span><span class="sxs-lookup"><span data-stu-id="e49ba-107">Organizing code</span></span>

<span data-ttu-id="e49ba-108">F # offre due modi per organizzare il codice: moduli e spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="e49ba-109">Questi sono simili, ma hanno le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="e49ba-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="e49ba-110">Gli spazi dei nomi vengono compilate come spazi dei nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="e49ba-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="e49ba-111">I moduli vengono compilati come le classi statiche.</span><span class="sxs-lookup"><span data-stu-id="e49ba-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="e49ba-112">Gli spazi dei nomi sono sempre di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="e49ba-112">Namespaces are always top level.</span></span> <span data-ttu-id="e49ba-113">I moduli possono essere nidificati all'interno di altri moduli e livello principale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="e49ba-114">Gli spazi dei nomi possono estendersi su più file.</span><span class="sxs-lookup"><span data-stu-id="e49ba-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="e49ba-115">I moduli non possono.</span><span class="sxs-lookup"><span data-stu-id="e49ba-115">Modules cannot.</span></span>
* <span data-ttu-id="e49ba-116">I moduli possono essere decorati con `[<RequireQualifiedAccess>]` e `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="e49ba-117">Le linee guida seguenti consentono di usarle per organizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="e49ba-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="e49ba-118">Preferire gli spazi dei nomi di primo livello</span><span class="sxs-lookup"><span data-stu-id="e49ba-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="e49ba-119">Per il codice utilizzabile pubblicamente, gli spazi dei nomi sono preferenziali per i moduli di primo livello.</span><span class="sxs-lookup"><span data-stu-id="e49ba-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="e49ba-120">Poiché vengono compilati come spazi dei nomi .NET, sono utilizzabili dal codice c# con alcun problema.</span><span class="sxs-lookup"><span data-stu-id="e49ba-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="e49ba-121">Uso di un modulo di primo livello potrebbe non essere visualizzati diverso quando viene chiamato solo da F #, ma per c# consumer, i chiamanti potrebbero rimanere sorpresi per dover qualificare `MyClass` con il `MyCode` modulo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="e49ba-122">Applicare attentamente `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="e49ba-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="e49ba-123">Il `[<AutoOpen>]` costrutto possa inquinare l'ambito di ciò che è disponibile ai chiamanti e la risposta a un elemento da cui provenienza è "magic".</span><span class="sxs-lookup"><span data-stu-id="e49ba-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="e49ba-124">Non si tratta in genere una cosa positiva.</span><span class="sxs-lookup"><span data-stu-id="e49ba-124">This is generally not a good thing.</span></span> <span data-ttu-id="e49ba-125">Un'eccezione a questa regola è la libreria di base F # se stessa (anche se questo fatto è anche un po' controverso).</span><span class="sxs-lookup"><span data-stu-id="e49ba-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="e49ba-126">Tuttavia, è utile se si ha la funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.</span><span class="sxs-lookup"><span data-stu-id="e49ba-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="e49ba-127">Ciò consente di dettagli di implementazione separato correttamente dall'API pubblica di una funzione senza doverla specificare completamente un helper ogni volta che viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="e49ba-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="e49ba-128">Inoltre, che espone i metodi di estensione e generatori di espressioni a livello di spazio dei nomi può essere accuratamente espresso con `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="e49ba-129">Usare `[<RequireQualifiedAccess>]` ogni volta che i nomi potrebbero essere in conflitto o si ritiene consente una migliore leggibilità</span><span class="sxs-lookup"><span data-stu-id="e49ba-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="e49ba-130">Aggiunta di `[<RequireQualifiedAccess>]` attributo a un modulo indica che il modulo non può essere aperta e che i riferimenti agli elementi del modulo richiedono esplicita completo di accesso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="e49ba-131">Ad esempio, il `Microsoft.FSharp.Collections.List` modulo dispone di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="e49ba-132">Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che possono entrare in conflitto con i nomi di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="e49ba-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="e49ba-133">Richiedere l'accesso completo può aumentare notevolmente la manutenibilità a lungo termine e capacità evolutiva di una libreria.</span><span class="sxs-lookup"><span data-stu-id="e49ba-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="e49ba-134">Ordinamento `open` istruzioni topologicamente</span><span class="sxs-lookup"><span data-stu-id="e49ba-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="e49ba-135">In F #, è importante l'ordine delle dichiarazioni, tra cui con `open` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="e49ba-136">A differenza di c#, si tratta in cui l'effetto della `using` e `using static` sono indipendenti l'ordinamento di tali istruzioni in un file.</span><span class="sxs-lookup"><span data-stu-id="e49ba-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="e49ba-137">In F #, possono nascondere elementi aperti in un ambito di altri utenti sono già presenti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="e49ba-138">Ciò significa che la ridisposizione delle `open` istruzioni è stato possibile modificare il significato del codice.</span><span class="sxs-lookup"><span data-stu-id="e49ba-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="e49ba-139">Di conseguenza, qualsiasi arbitrario l'ordinamento di tutti i `open` istruzioni (ad esempio, in ordine alfanumerico) è in genere sconsigliato, correre è generare un comportamento diverso che ci si aspetterebbe.</span><span class="sxs-lookup"><span data-stu-id="e49ba-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="e49ba-140">È invece consigliabile li Ordina [topologicamente](https://en.wikipedia.org/wiki/Topological_sorting); vale a dire, ordinare le `open` le istruzioni nell'ordine in cui _livelli_ del sistema sono definiti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="e49ba-141">In questo alfanumerico ordinamento all'interno di diversi livelli topologici inoltre può essere considerato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="e49ba-142">Ad esempio, ecco l'ordinamento topologico per il file F # del compilatore servizio pubblico API:</span><span class="sxs-lookup"><span data-stu-id="e49ba-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="e49ba-143">Si noti che un'interruzione di riga separa topologici livelli, con ogni livello da ordinare in ordine alfanumerico in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e49ba-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="e49ba-144">Normalmente, ciò consente di organizzare codice senza shadowing accidentalmente i valori.</span><span class="sxs-lookup"><span data-stu-id="e49ba-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="e49ba-145">Usare classi per contenere i valori che hanno effetti collaterali</span><span class="sxs-lookup"><span data-stu-id="e49ba-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="e49ba-146">Esistono molte volte quando un valore di inizializzazione può avere effetti collaterali, ad esempio creare un'istanza di un contesto a un database o altre risorse remote.</span><span class="sxs-lookup"><span data-stu-id="e49ba-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="e49ba-147">Si è tentati di inizializzazione di elementi in un modulo e usarlo in funzioni successive:</span><span class="sxs-lookup"><span data-stu-id="e49ba-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="e49ba-148">Ciò è spesso una buona idea per diversi motivi:</span><span class="sxs-lookup"><span data-stu-id="e49ba-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="e49ba-149">In primo luogo, configurazione dell'applicazione viene inserita nel codebase `dep1` e `dep2`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="e49ba-150">Questo è difficile da gestire nel codebase più grandi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="e49ba-151">I dati in secondo luogo, inizializzati in modo statico non devono includere i valori che non sono thread-safe se il componente verrà utilizzato più thread.</span><span class="sxs-lookup"><span data-stu-id="e49ba-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="e49ba-152">È chiaramente sospesa dal `dep3`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="e49ba-153">Infine, l'inizializzazione del modulo compila in un costruttore statico per l'intera unità di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="e49ba-154">Se si verifica un errore nell'inizializzazione valore associazione let in tale modulo, manifesta come un `TypeInitializationException` che viene quindi memorizzato nella cache per l'intera durata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="e49ba-155">Ciò può essere difficile da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="e49ba-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="e49ba-156">È in genere un'eccezione interna che è possibile tentare di ragionare sul, ma se non esiste, quindi non c'è la causa radice.</span><span class="sxs-lookup"><span data-stu-id="e49ba-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="e49ba-157">Usare invece solo una semplice classe per contenere le dipendenze:</span><span class="sxs-lookup"><span data-stu-id="e49ba-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="e49ba-158">Ciò consente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e49ba-158">This enables the following:</span></span>

1. <span data-ttu-id="e49ba-159">Eseguire il push di qualsiasi stato dipendente di fuori l'API stessa.</span><span class="sxs-lookup"><span data-stu-id="e49ba-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="e49ba-160">Configurazione a questo punto può essere eseguita all'esterno dell'API.</span><span class="sxs-lookup"><span data-stu-id="e49ba-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="e49ba-161">Errori di inizializzazione per i valori dipendenti non sono soggette a risolversi in un `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="e49ba-162">L'API è ora più facile da testare.</span><span class="sxs-lookup"><span data-stu-id="e49ba-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="e49ba-163">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="e49ba-163">Error management</span></span>

<span data-ttu-id="e49ba-164">Gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e maggior numero di sfumature e non esistono Nessun silver punti elenco nell'assicurare i sistemi sono a tolleranza di errore e anche un comportamento.</span><span class="sxs-lookup"><span data-stu-id="e49ba-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="e49ba-165">Le seguenti linee guida devono offrire indicazioni nella navigazione quest'area difficile.</span><span class="sxs-lookup"><span data-stu-id="e49ba-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="e49ba-166">Rappresentano casi di errore e lo stato non valido nei tipi intrinseci al dominio</span><span class="sxs-lookup"><span data-stu-id="e49ba-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="e49ba-167">Con [unioni discriminate](../language-reference/discriminated-unions.md), F # offre la possibilità di rappresentare lo stato del programma guasto nel sistema tipo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="e49ba-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e49ba-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="e49ba-169">In questo caso, esistono tre modi noti prelievo di denaro da un conto bancario può avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="e49ba-170">Ogni caso di errore è rappresentato nel tipo e può pertanto essere gestito in modo sicuro in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="e49ba-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="e49ba-171">In generale, se è possibile modellare i diversi modi per ottenere un determinato può **esito negativo** nel dominio, quindi la gestione del codice di errore non viene non è più considerato come qualcosa si devono affrontare oltre il flusso di programma normale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="e49ba-172">È semplicemente una parte del normale flusso di programma ma non considerata **eccezionali**.</span><span class="sxs-lookup"><span data-stu-id="e49ba-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="e49ba-173">Esistono due vantaggi principali a questo:</span><span class="sxs-lookup"><span data-stu-id="e49ba-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="e49ba-174">È più facile da gestire se il dominio viene modificato nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="e49ba-175">Casi di errore sono più semplici a unit test.</span><span class="sxs-lookup"><span data-stu-id="e49ba-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="e49ba-176">Utilizzare le eccezioni quando gli errori non possono essere rappresentati con i tipi</span><span class="sxs-lookup"><span data-stu-id="e49ba-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="e49ba-177">Non tutti gli errori possono essere rappresentati in un dominio del problema.</span><span class="sxs-lookup"><span data-stu-id="e49ba-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="e49ba-178">Questi tipi di errori vengono *eccezionali* in natura, pertanto la possibilità di generare e rilevare eccezioni in F #.</span><span class="sxs-lookup"><span data-stu-id="e49ba-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="e49ba-179">In primo luogo, si consiglia di leggere il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="e49ba-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="e49ba-180">Queste sono applicabili anche a F #.</span><span class="sxs-lookup"><span data-stu-id="e49ba-180">These are also applicable to F#.</span></span>

<span data-ttu-id="e49ba-181">I costrutti principali disponibili in F # per quanto riguarda la generazione di eccezioni da considerare nel seguente ordine di preferenza:</span><span class="sxs-lookup"><span data-stu-id="e49ba-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="e49ba-182">Funzione</span><span class="sxs-lookup"><span data-stu-id="e49ba-182">Function</span></span> | <span data-ttu-id="e49ba-183">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e49ba-183">Syntax</span></span> | <span data-ttu-id="e49ba-184">Scopo</span><span class="sxs-lookup"><span data-stu-id="e49ba-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="e49ba-185">Genera un `System.ArgumentNullException` con il nome dell'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="e49ba-186">Genera un `System.ArgumentException` con un nome dell'argomento specificato e un messaggio.</span><span class="sxs-lookup"><span data-stu-id="e49ba-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="e49ba-187">Genera un `System.InvalidOperationException` con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="e49ba-188">Meccanismo generico per la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="e49ba-189">Genera un `System.Exception` con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="e49ba-190">Genera un `System.Exception` con un messaggio in base la stringa di formato e i relativi input.</span><span class="sxs-lookup"><span data-stu-id="e49ba-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="e49ba-191">Uso `nullArg`, `invalidArg` e `invalidOp` come meccanismo per generare `ArgumentNullException`, `ArgumentException` e `InvalidOperationException` quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="e49ba-192">Il `failwith` e `failwithf` funzioni devono essere generalmente evitate perché essi elevare la base `Exception` digitare, non un'eccezione specifica.</span><span class="sxs-lookup"><span data-stu-id="e49ba-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="e49ba-193">In base il [linee guida di progettazione di eccezione](../../standard/design-guidelines/exceptions.md), che si desidera generare eccezioni più specifiche, quando possibile.</span><span class="sxs-lookup"><span data-stu-id="e49ba-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="e49ba-194">Usando la sintassi di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="e49ba-194">Using exception-handling syntax</span></span>

<span data-ttu-id="e49ba-195">F # supporta modelli di eccezione tramite la `try...with` sintassi:</span><span class="sxs-lookup"><span data-stu-id="e49ba-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="e49ba-196">Risoluzione delle differenze di funzionalità per eseguire in caso di un'eccezione con criteri di ricerca può essere difficile se si vuole mantenere il codice pulito.</span><span class="sxs-lookup"><span data-stu-id="e49ba-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="e49ba-197">Un modo per gestire questo problema consiste nell'utilizzare [modelli attivi](../language-reference/active-patterns.md) come mezzo per la funzionalità gruppo che circonda un caso di errore con un'eccezione se stesso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="e49ba-198">Si potrebbe ad esempio, utilizza un'API che, quando viene generata un'eccezione, include informazioni utili nei metadati dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="e49ba-199">Annullamento del wrapping di un valore utile nel corpo di eccezione acquisito all'interno di (modello attivo) e la restituzione di valore può essere utile in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="e49ba-200">Non usare monadic gestione degli errori per sostituire le eccezioni</span><span class="sxs-lookup"><span data-stu-id="e49ba-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="e49ba-201">Le eccezioni vengono interpretate come un po' tabù nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="e49ba-202">In effetti, le eccezioni violano purezza, pertanto è opportuno considerare li non abbastanza funzionale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="e49ba-203">Tuttavia, questo ignora la realtà di in cui deve essere eseguito codice e che possono verificarsi errori di runtime.</span><span class="sxs-lookup"><span data-stu-id="e49ba-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="e49ba-204">In generale, è possibile scrivere codice in base al presupposto che la maggior parte delle operazioni siano puri né totale, per ridurre al minimo spiacevoli sorprese.</span><span class="sxs-lookup"><span data-stu-id="e49ba-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="e49ba-205">È importante prendere in considerazione i seguenti punti di forza/aspetti fondamentali delle eccezioni rispetto alla loro rilevanza e può risultare appropriato nel runtime di .NET e lingue ecosistema nel suo complesso:</span><span class="sxs-lookup"><span data-stu-id="e49ba-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="e49ba-206">Contengono le informazioni di diagnostica dettagliate che sono molto utile durante il debug di un problema.</span><span class="sxs-lookup"><span data-stu-id="e49ba-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="e49ba-207">Sono ben noti dal runtime e altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="e49ba-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="e49ba-208">Possono ridurre boilerplate significativo quando vengono confrontati con il codice esce dal dirigendo verso *evitare* eccezioni mediante l'implementazione di alcuni subset di presentano una semantica in base ad hoc.</span><span class="sxs-lookup"><span data-stu-id="e49ba-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="e49ba-209">Questo terzo punto è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-209">This third point is critical.</span></span> <span data-ttu-id="e49ba-210">Per operazioni complesse non semplice, riesce a utilizzare le eccezioni può comportare la gestione di strutture simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e49ba-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="e49ba-211">Che può causare facilmente codice fragile, ad esempio criteri di ricerca in "stringly tipizzata" errori:</span><span class="sxs-lookup"><span data-stu-id="e49ba-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="e49ba-212">Inoltre, può essere tentato di inghiottire qualsiasi eccezione il desiderio di una funzione "semplice" che restituisce un tipo di "coloro":</span><span class="sxs-lookup"><span data-stu-id="e49ba-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="e49ba-213">Sfortunatamente, `tryReadAllText` può generare numerose eccezioni basate la miriade di operazioni che possono verificarsi in un file system, e questo codice rimuove da subito eventuali informazioni sul possibile effettivamente causa problemi nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="e49ba-214">Se questo codice viene sostituito con un tipo di risultato, quindi si ritorna al messaggio di errore "stringly tipizzata" analisi:</span><span class="sxs-lookup"><span data-stu-id="e49ba-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="e49ba-215">E inserire l'oggetto eccezione stesso nel `Error` costruttore impone solo è possibile gestire in modo corretto con il tipo di eccezione nel sito di chiamata invece che nella funzione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="e49ba-216">Eccezioni verificate, che sono notoriamente unfun affrontare il chiamante di un'API in modo efficace in modo da ottenere.</span><span class="sxs-lookup"><span data-stu-id="e49ba-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="e49ba-217">Una buona alternativa per gli esempi precedenti è rilevare *specifici* eccezioni e restituire un valore significativo nel contesto della nuova eccezione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="e49ba-218">Se si modifica il `tryReadAllText` funzionare nel modo seguente: `None` siano più facilmente comprensibili:</span><span class="sxs-lookup"><span data-stu-id="e49ba-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="e49ba-219">Invece di funzionare come un catch-all, questa funzione ora correttamente gestirà il caso quando un file non è stato trovato e assegnare tale significato per un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="e49ba-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="e49ba-220">Questo valore restituito può eseguire il mapping per tale scenario di errore, mentre non rimuovendo qualsiasi informazioni contestuali o imporre ai chiamanti di affrontare un caso che potrebbe non essere pertinente a questo punto nel codice.</span><span class="sxs-lookup"><span data-stu-id="e49ba-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="e49ba-221">I tipi, ad esempio `Result<'Success, 'Error>` appropriati per le operazioni di base in cui essi non sono annidati e tipi facoltativi di F # sono ideali per la rappresentazione quando un elemento è stato possibile restituire *qualcosa* o *nothing*.</span><span class="sxs-lookup"><span data-stu-id="e49ba-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="e49ba-222">Non sono una sostituzione per le eccezioni, tuttavia e non deve essere utilizzati nel tentativo per sostituire le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="e49ba-223">Piuttosto, si deve essere applicati con cautela per alcuni aspetti specifici di indirizzi di eccezione e criteri di gestione degli errori in modalità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="e49ba-224">Applicazione parziale e della programmazione senza punto</span><span class="sxs-lookup"><span data-stu-id="e49ba-224">Partial application and point-free programming</span></span>

<span data-ttu-id="e49ba-225">F # supporta applicazione parziale e, di conseguenza, sui vari modi al programma in uno stile privi di punti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="e49ba-226">Ciò può essere utile per il riutilizzo di codice all'interno di un modulo o l'implementazione di un elemento, ma non si tratta in genere per esporre pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="e49ba-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="e49ba-227">In generale, programmazione senza punto non è un essendo e in se stesso e può aggiungere un ostacolo significativo cognitivo per utenti che non sono si è immersi nello stile.</span><span class="sxs-lookup"><span data-stu-id="e49ba-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="e49ba-228">Non utilizzare applicazione parziale e currying nelle API pubbliche</span><span class="sxs-lookup"><span data-stu-id="e49ba-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="e49ba-229">Con l'eccezione piccolo, l'uso dell'applicazione parziali nelle API pubbliche può generare confusione per i consumer.</span><span class="sxs-lookup"><span data-stu-id="e49ba-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="e49ba-230">In genere `let`-sono valori associati nel codice F # **valori**, non **valori di funzione**.</span><span class="sxs-lookup"><span data-stu-id="e49ba-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="e49ba-231">Combinazione di valori e i valori di funzione può comportare il salvataggio di un numero ridotto di righe di codice a fronte di un notevole sovraccarico cognitivo, soprattutto se combinate con gli operatori, ad esempio `>>` comporre funzioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="e49ba-232">Considerare le implicazioni di strumenti per la programmazione senza punto</span><span class="sxs-lookup"><span data-stu-id="e49ba-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="e49ba-233">Funzioni sottoposte a currying non assegnata un'etichetta ai relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="e49ba-234">Ciò ha implicazioni in termini di strumenti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-234">This has tooling implications.</span></span> <span data-ttu-id="e49ba-235">Prendere in considerazione le due funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e49ba-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="e49ba-236">Entrambi sono funzioni valide, ma `funcWithApplication` è una funzione sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="e49ba-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="e49ba-237">Quando si posiziona i relativi tipi in un editor, viene visualizzato questo:</span><span class="sxs-lookup"><span data-stu-id="e49ba-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="e49ba-238">Nel sito di chiamata, le descrizioni comandi in strumenti quali Visual Studio non è di fornire informazioni significative quali la `string` e `int` rappresentano effettivamente i tipi di input.</span><span class="sxs-lookup"><span data-stu-id="e49ba-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="e49ba-239">Se si verifica senza punto di codice, ad esempio `funcWithApplication` è utilizzabile pubblicamente, è consigliabile eseguire un'espansione di η completa in modo che gli strumenti possono scegliere nell'inserimento nel nomi significativi per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="e49ba-240">Inoltre, il debug del codice senza punto può essere difficile, se non impossibile.</span><span class="sxs-lookup"><span data-stu-id="e49ba-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="e49ba-241">Strumenti di debug si basano sui valori associati ai nomi (ad esempio, `let` associazioni) in modo che sia possibile esaminare l'esecuzione durante l'esecuzione valori intermedi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="e49ba-242">Quando il codice non contiene valori per controllare, vi è nulla di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="e49ba-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="e49ba-243">In futuro, gli strumenti di debug potrebbero evolversi per sintetizzare questi valori in base a percorsi eseguiti in precedenza, ma non è una buona idea per salvaguardarsi la rilevanza nel *potenziali* funzionalità di debug.</span><span class="sxs-lookup"><span data-stu-id="e49ba-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="e49ba-244">Prendere in considerazione applicazione parziale come tecnica per ridurre boilerplate interno</span><span class="sxs-lookup"><span data-stu-id="e49ba-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="e49ba-245">A differenza al punto precedente, applicazione parziale è un ottimo strumento per ridurre boilerplate all'interno di un'applicazione o gli elementi interni più approfonditi di un'API.</span><span class="sxs-lookup"><span data-stu-id="e49ba-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="e49ba-246">Può essere utile per gli unit test l'implementazione di API più complicate, in cui boilerplate è spesso un problema da affrontare.</span><span class="sxs-lookup"><span data-stu-id="e49ba-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="e49ba-247">Ad esempio, il codice seguente viene illustrato come è possibile ottenere il risultato quali Framework di simulazione più offrono senza una dipendenza esterna su un framework di questo tipo e dover apprendere un correlati allestita l'API.</span><span class="sxs-lookup"><span data-stu-id="e49ba-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="e49ba-248">Ad esempio, prendere in considerazione la topografia di soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e49ba-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="e49ba-249">`ImplementationLogic.fsproj` potrebbe esporre il codice, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e49ba-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="e49ba-250">Gli unit test `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` è semplice:</span><span class="sxs-lookup"><span data-stu-id="e49ba-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="e49ba-251">Parzialmente applicando `doTransaction` con un contesto di creazione di versioni fittizie oggetto consente di chiamare la funzione in tutti gli unit test senza la necessità di costruire ogni volta che un contesto simulato:</span><span class="sxs-lookup"><span data-stu-id="e49ba-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="e49ba-252">Questa tecnica non deve essere applicata universalmente per l'intera codebase, ma è un buon metodo per ridurre boilerplate per elementi interni complicata e gli unit test di tali meccanismi interni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="e49ba-253">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="e49ba-253">Access control</span></span>

<span data-ttu-id="e49ba-254">F # offre più opzioni per la [controllo di accesso](../language-reference/access-control.md), ereditato da ciò che è disponibile nel runtime di .NET.</span><span class="sxs-lookup"><span data-stu-id="e49ba-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="e49ba-255">Questi non sono utilizzabili solo per i tipi: è possibile usarli per le funzioni, troppo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="e49ba-256">Non preferisce`public` tipi e membri fino a quando non è necessario che diventino utilizzabile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="e49ba-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="e49ba-257">Ciò riduce al minimo le due consumer per</span><span class="sxs-lookup"><span data-stu-id="e49ba-257">This also minimizes what consumers couple to</span></span>
* <span data-ttu-id="e49ba-258">Cercare di mantenere tutte le funzionalità di helper `private`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="e49ba-259">Si consideri l'uso di `[<AutoOpen>]` su un modulo privato delle funzioni di supporto se diventano numerosi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="e49ba-260">L'inferenza del tipo e generics</span><span class="sxs-lookup"><span data-stu-id="e49ba-260">Type inference and generics</span></span>

<span data-ttu-id="e49ba-261">L'inferenza del tipo può evitare la digitazione numerosi boilerplate.</span><span class="sxs-lookup"><span data-stu-id="e49ba-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="e49ba-262">E la generalizzazione automatica nel compilatore F # consentono di scrivere codice più generico quasi senza altre modifiche da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e49ba-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="e49ba-263">Tuttavia, queste funzionalità non sono universalmente valida.</span><span class="sxs-lookup"><span data-stu-id="e49ba-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="e49ba-264">Prendere in considerazione l'assegnazione di etichette i nomi di argomento con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza del tipo per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="e49ba-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="e49ba-265">Il motivo è che **si** deve essere nel controllo della forma dell'API, non il compilatore.</span><span class="sxs-lookup"><span data-stu-id="e49ba-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="e49ba-266">Anche se il compilatore può eseguire un processo correttamente all'inferenza di tipi per l'utente, è possibile avere la forma di apportare modifiche all'API se si affidano ai componenti interni sono stati modificati i tipi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="e49ba-267">È possibile che si desidera, ma quasi sicuramente comporterà una modifica sostanziale API consumer downstream dovrà affrontare.</span><span class="sxs-lookup"><span data-stu-id="e49ba-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="e49ba-268">In alternativa, se si controlla in modo esplicito la forma dell'API pubblica, è possibile controllare queste modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="e49ba-269">Nella terminologia DDD, può essere considerata come un livello anti-danneggiamento.</span><span class="sxs-lookup"><span data-stu-id="e49ba-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="e49ba-270">È consigliabile assegnare un nome significativo per gli argomenti generici.</span><span class="sxs-lookup"><span data-stu-id="e49ba-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="e49ba-271">A meno che non si scrive codice realmente generico che non è specifico per un particolare dominio, un nome significativo consente agli altri programmatori informazioni sul dominio che viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="e49ba-272">Ad esempio, un parametro di tipo denominato `'Document` nel contesto dell'interazione con un documento di database è molto più chiaro che i tipi di documento generico possono essere accettati dalla funzione o membro si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="e49ba-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="e49ba-273">Si consiglia di denominare i parametri di tipo generico con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="e49ba-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="e49ba-274">Questo è il modo generale per eseguire operazioni in .NET, pertanto è consigliabile usare PascalCase anziché snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="e49ba-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="e49ba-275">Infine, generalizzazione automatica non è sempre un enorme vantaggio per le persone che hanno familiarità con F # o una codebase di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="e49ba-276">È sovraccarico cognitivo usando i componenti che sono di tipo generici.</span><span class="sxs-lookup"><span data-stu-id="e49ba-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="e49ba-277">Inoltre, se automaticamente generalizzata di funzioni non vengono usate con diversi tipi di input (solo se sono destinati a essere usate come tali let), quindi non offre alcun vantaggio reale a tali da generico a quel punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="e49ba-278">Valutare sempre se si sta scrivendo codice effettivamente trarrà vantaggio dal generico.</span><span class="sxs-lookup"><span data-stu-id="e49ba-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="e49ba-279">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="e49ba-279">Performance</span></span>

<span data-ttu-id="e49ba-280">Valori di F # non sono modificabili per impostazione predefinita, che consente di evitare di determinate classi di bug (in particolare i che implicano parallelismo e concorrenza).</span><span class="sxs-lookup"><span data-stu-id="e49ba-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="e49ba-281">Tuttavia, in alcuni casi, per ottenere l'efficienza ottima (o persino ragionevole) del tempo di esecuzione o allocazioni di memoria, un intervallo di lavoro può essere implementato in modo ottimale tramite la modifica sul posto dello stato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="e49ba-282">Ciò è possibile in modo acconsenti esplicitamente con F # con la `mutable` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="e49ba-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="e49ba-283">Tuttavia, usare di `mutable` potrebbero sentirsi incompatibile con la purezza funzionale in F #.</span><span class="sxs-lookup"><span data-stu-id="e49ba-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="e49ba-284">Questo è tutto bene, se si modificano le aspettative da purezza al [trasparenza referenziale](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="e49ba-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="e49ba-285">La trasparenza referenziale - non purezza - è l'obiettivo finale durante la scrittura di funzioni F #.</span><span class="sxs-lookup"><span data-stu-id="e49ba-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="e49ba-286">In questo modo è possibile scrivere un'interfaccia funzionale tramite un'implementazione basata su Modifica per il codice critico delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="e49ba-287">Eseguire il wrapping di codice modificabile nelle interfacce non modificabile</span><span class="sxs-lookup"><span data-stu-id="e49ba-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="e49ba-288">Con la trasparenza referenziale come obiettivo, è fondamentale per scrivere codice che non espone il underbelly modificabile delle funzioni critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e49ba-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="e49ba-289">Ad esempio, il codice seguente implementa il `Array.contains` funzione nella libreria di base F #:</span><span class="sxs-lookup"><span data-stu-id="e49ba-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="e49ba-290">Chiamare questa funzione più volte non modifica la matrice sottostante e non è necessario mantenere qualsiasi stato modificabile all'utilizzo dello stesso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="e49ba-291">È trasparente referenziali, anche se quasi tutte le righe di codice in esso contenuti Usa mutation.</span><span class="sxs-lookup"><span data-stu-id="e49ba-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="e49ba-292">Prendere in considerazione che incapsula dati modificabili nelle classi</span><span class="sxs-lookup"><span data-stu-id="e49ba-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="e49ba-293">L'esempio precedente Usa una singola funzione per incapsulare operazioni usando dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="e49ba-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="e49ba-294">Ciò non è sempre sufficiente per set di dati più complessi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="e49ba-295">Prendere in considerazione i seguenti set di funzioni:</span><span class="sxs-lookup"><span data-stu-id="e49ba-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="e49ba-296">Questo codice sia efficiente, ma espongono la struttura di dati basati su mutation che i chiamanti sono responsabili della gestione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="e49ba-297">Ciò può essere incapsulato all'interno di una classe senza membri sottostanti che è possibile modificare:</span><span class="sxs-lookup"><span data-stu-id="e49ba-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="e49ba-298">`Closure1Table` incapsula la struttura di dati basati su mutation sottostante, pertanto senza imporre ai chiamanti di mantenere la struttura dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="e49ba-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="e49ba-299">Le classi sono un metodo efficace per incapsulare i dati e le routine che sono basati su mutation senza esporre i dettagli per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="e49ba-300">Preferisce `let mutable` alle celle di riferimento</span><span class="sxs-lookup"><span data-stu-id="e49ba-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="e49ba-301">Le celle di riferimento sono un modo per rappresentare il riferimento a un valore anziché il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="e49ba-302">Anche se possono essere usati per il codice critiche per le prestazioni, in genere non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="e49ba-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="e49ba-303">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e49ba-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="e49ba-304">L'uso di una cella di riferimento adesso "falsifica" tutto il codice successivo con la necessità di dereferenziazione e fare di nuovo riferimento i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="e49ba-305">Si consiglia di `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="e49ba-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="e49ba-306">A parte il singolo punto di mutazione durante l'espressione lambda, tutte le altre code che interessa `acc` possibile farlo in modo che non è diverso per l'utilizzo di un normale `let`-valore modificabile associato.</span><span class="sxs-lookup"><span data-stu-id="e49ba-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="e49ba-307">Ciò renderà più semplice la modifica nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="e49ba-308">Programmazione degli oggetti</span><span class="sxs-lookup"><span data-stu-id="e49ba-308">Object programming</span></span>

<span data-ttu-id="e49ba-309">F # offre supporto completo per gli oggetti e concetti (OO) orientate a oggetti.</span><span class="sxs-lookup"><span data-stu-id="e49ba-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="e49ba-310">Sebbene molti concetti orientato a oggetti sono potenti e utili, non tutte sono ideali per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e49ba-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="e49ba-311">Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità orientato a oggetti a livello generale.</span><span class="sxs-lookup"><span data-stu-id="e49ba-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="e49ba-312">**È consigliabile usare queste funzionalità in molte situazioni:**</span><span class="sxs-lookup"><span data-stu-id="e49ba-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="e49ba-313">La notazione del punto (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="e49ba-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="e49ba-314">Membri di istanza</span><span class="sxs-lookup"><span data-stu-id="e49ba-314">Instance members</span></span>
* <span data-ttu-id="e49ba-315">Costruttori impliciti</span><span class="sxs-lookup"><span data-stu-id="e49ba-315">Implicit constructors</span></span>
* <span data-ttu-id="e49ba-316">Membri statici</span><span class="sxs-lookup"><span data-stu-id="e49ba-316">Static members</span></span>
* <span data-ttu-id="e49ba-317">Notazione dell'indicizzatore (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="e49ba-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="e49ba-318">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="e49ba-318">Named and Optional arguments</span></span>
* <span data-ttu-id="e49ba-319">Interfacce e implementazioni di interfaccia</span><span class="sxs-lookup"><span data-stu-id="e49ba-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="e49ba-320">**Non raggiungere prima di tutto per queste funzionalità, ma con cautela applicarle quando essi sono utili risolvere un problema:**</span><span class="sxs-lookup"><span data-stu-id="e49ba-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="e49ba-321">Overload di un metodo</span><span class="sxs-lookup"><span data-stu-id="e49ba-321">Method overloading</span></span>
* <span data-ttu-id="e49ba-322">Dati modificabile incapsulati</span><span class="sxs-lookup"><span data-stu-id="e49ba-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="e49ba-323">Operatori nei tipi</span><span class="sxs-lookup"><span data-stu-id="e49ba-323">Operators on types</span></span>
* <span data-ttu-id="e49ba-324">Proprietà automatiche</span><span class="sxs-lookup"><span data-stu-id="e49ba-324">Auto properties</span></span>
* <span data-ttu-id="e49ba-325">Implementazione `IDisposable` e `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="e49ba-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="e49ba-326">Estensioni di tipo</span><span class="sxs-lookup"><span data-stu-id="e49ba-326">Type extensions</span></span>
* <span data-ttu-id="e49ba-327">Eventi</span><span class="sxs-lookup"><span data-stu-id="e49ba-327">Events</span></span>
* <span data-ttu-id="e49ba-328">Struct</span><span class="sxs-lookup"><span data-stu-id="e49ba-328">Structs</span></span>
* <span data-ttu-id="e49ba-329">Delegati</span><span class="sxs-lookup"><span data-stu-id="e49ba-329">Delegates</span></span>
* <span data-ttu-id="e49ba-330">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e49ba-330">Enums</span></span>

<span data-ttu-id="e49ba-331">**A meno che non è necessario utilizzarli in generale evitare queste funzionalità:**</span><span class="sxs-lookup"><span data-stu-id="e49ba-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="e49ba-332">Le gerarchie di ereditarietà in base al tipo e l'ereditarietà di implementazione</span><span class="sxs-lookup"><span data-stu-id="e49ba-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="e49ba-333">I valori null e `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="e49ba-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="e49ba-334">Preferire la composizione di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e49ba-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="e49ba-335">[Composizione dell'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) è un linguaggio di lunga durato che possa rispettare buon codice F #.</span><span class="sxs-lookup"><span data-stu-id="e49ba-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="e49ba-336">Il principio fondamentale è che non si devono esporre una classe di base e imporre ai chiamanti di ereditare da tale classe base per ottenere funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e49ba-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="e49ba-337">Usare le espressioni di oggetto per implementare le interfacce se non è necessaria una classe</span><span class="sxs-lookup"><span data-stu-id="e49ba-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="e49ba-338">[Espressioni di oggetto](../language-reference/object-expressions.md) consentono di implementare le interfacce in tempo reale, associazione l'interfaccia implementata da un valore senza la necessità di eseguire questa operazione all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="e49ba-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="e49ba-339">Ciò è utile, soprattutto se si _solo_ necessario implementare l'interfaccia e non sono necessari per una classe completa.</span><span class="sxs-lookup"><span data-stu-id="e49ba-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="e49ba-340">Ad esempio, ecco il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di correzione del codice se è stato aggiunto un simbolo che non hai un `open` informativa per:</span><span class="sxs-lookup"><span data-stu-id="e49ba-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="e49ba-341">Poiché non è necessario per una classe quando si interagisce con l'API di Visual Studio Code, le espressioni di oggetto sono uno strumento ideale per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="e49ba-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="e49ba-342">Sono anche utili per gli unit test, quando si desidera sottoporre a stub out un'interfaccia con le routine di test in modalità ad hoc.</span><span class="sxs-lookup"><span data-stu-id="e49ba-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="e49ba-343">Abbreviazioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="e49ba-343">Type Abbreviations</span></span>

<span data-ttu-id="e49ba-344">[Abbreviazioni di tipo](../language-reference/type-abbreviations.md) sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma della funzione o un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="e49ba-345">Ad esempio, viene assegnata un'etichetta per cosa è necessario definire un calcolo con l'alias seguente [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), una libreria di apprendimento avanzato:</span><span class="sxs-lookup"><span data-stu-id="e49ba-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="e49ba-346">Il `Computation` nome è un modo pratico per indicare qualsiasi funzione che corrisponde alla firma è l'aliasing.</span><span class="sxs-lookup"><span data-stu-id="e49ba-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="e49ba-347">Uso di abbreviazioni di tipo simile al seguente è utile e consente di codice più conciso.</span><span class="sxs-lookup"><span data-stu-id="e49ba-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="e49ba-348">Evitare di usare le abbreviazioni dei tipi per rappresentare il dominio</span><span class="sxs-lookup"><span data-stu-id="e49ba-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="e49ba-349">Sebbene le abbreviazioni dei tipi sono particolarmente utili per fornire un nome alle firme di funzione, possono essere poco chiaro quando l'abbreviazione degli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="e49ba-350">Prendere in considerazione questo abbreviazione:</span><span class="sxs-lookup"><span data-stu-id="e49ba-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="e49ba-351">Ciò può generare confusione in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="e49ba-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="e49ba-352">`BufferSize` non è un'astrazione; è semplicemente un altro nome per un numero intero.</span><span class="sxs-lookup"><span data-stu-id="e49ba-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="e49ba-353">Se `BufferSize` viene esposto in un'API pubblica, si possono facilmente essere interpretati erroneamente da indicare più della semplice `int`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="e49ba-354">In genere, i tipi di dominio dispone di più attributi a tali e non sono tipi primitivi, ad esempio `int`.</span><span class="sxs-lookup"><span data-stu-id="e49ba-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="e49ba-355">Questo abbreviazione viola questa ipotesi.</span><span class="sxs-lookup"><span data-stu-id="e49ba-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="e49ba-356">Le maiuscole e minuscole di `BufferSize` (PascalCase) implica che questo tipo contiene più dati.</span><span class="sxs-lookup"><span data-stu-id="e49ba-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="e49ba-357">Questo alias non offre una maggiore chiarezza confrontato con la fornitura di un argomento denominato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="e49ba-358">L'abbreviazione si manifesta in linguaggio intermedio compilato; è solo un numero intero e questo alias è un costrutto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e49ba-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="e49ba-359">In sintesi, il problema con le abbreviazioni dei tipi è però **non** astrazioni sui tipi che sono abbreviando.</span><span class="sxs-lookup"><span data-stu-id="e49ba-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="e49ba-360">Nell'esempio precedente, `BufferSize` è semplicemente un' `int` dietro le quinte, con nessuna dati aggiuntivi, né alcun vantaggio dal sistema di tipi oltre a ciò che `int` esiste già.</span><span class="sxs-lookup"><span data-stu-id="e49ba-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
