---
title: Convenzioni di codifica F#
description: Informazioni sulle linee guida generali e sui linguaggi durante la scrittura di codice F.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400309"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="f6031-103">Convenzioni di codifica F#</span><span class="sxs-lookup"><span data-stu-id="f6031-103">F# coding conventions</span></span>

<span data-ttu-id="f6031-104">Le convenzioni seguenti sono formulate dall'esperienza di lavoro con codebase F .</span><span class="sxs-lookup"><span data-stu-id="f6031-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="f6031-105">I [cinque principi di buon codice F ,](index.md#five-principles-of-good-f-code) sono alla base di ogni raccomandazione.</span><span class="sxs-lookup"><span data-stu-id="f6031-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="f6031-106">Sono correlati alle linee guida per la [progettazione](component-design-guidelines.md)dei componenti F , ma sono applicabili per qualsiasi codice F, non solo per i componenti, ad esempio le librerie.</span><span class="sxs-lookup"><span data-stu-id="f6031-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="f6031-107">Organizzazione del codice</span><span class="sxs-lookup"><span data-stu-id="f6031-107">Organizing code</span></span>

<span data-ttu-id="f6031-108">Funzionalità di F : due modi principali per organizzare il codice: moduli e spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f6031-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="f6031-109">Questi sono simili, ma hanno le seguenti differenze:</span><span class="sxs-lookup"><span data-stu-id="f6031-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="f6031-110">Gli spazi dei nomi vengono compilati come spazi dei nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="f6031-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="f6031-111">I moduli vengono compilati come classi statiche.</span><span class="sxs-lookup"><span data-stu-id="f6031-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="f6031-112">Gli spazi dei nomi sono sempre di primo livello.</span><span class="sxs-lookup"><span data-stu-id="f6031-112">Namespaces are always top level.</span></span> <span data-ttu-id="f6031-113">I moduli possono essere di primo livello e nidificati all'interno di altri moduli.</span><span class="sxs-lookup"><span data-stu-id="f6031-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="f6031-114">Gli spazi dei nomi possono estendersi su più file.</span><span class="sxs-lookup"><span data-stu-id="f6031-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="f6031-115">I moduli non possono.</span><span class="sxs-lookup"><span data-stu-id="f6031-115">Modules cannot.</span></span>
* <span data-ttu-id="f6031-116">I moduli possono `[<RequireQualifiedAccess>]` `[<AutoOpen>]`essere decorati con e .</span><span class="sxs-lookup"><span data-stu-id="f6031-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="f6031-117">Le linee guida seguenti consentono di utilizzarli per organizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="f6031-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="f6031-118">Preferisci gli spazi dei nomi al livello superiore</span><span class="sxs-lookup"><span data-stu-id="f6031-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="f6031-119">Per qualsiasi codice consumabile pubblicamente, gli spazi dei nomi sono preferenziali ai moduli al livello superiore.</span><span class="sxs-lookup"><span data-stu-id="f6031-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="f6031-120">Poiché vengono compilati come spazi dei nomi .NET, sono utilizzabili da C , senza problemi.</span><span class="sxs-lookup"><span data-stu-id="f6031-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="f6031-121">L'utilizzo di un modulo di primo livello potrebbe non essere diverso quando viene chiamato solo `MyClass` da `MyCode` F, ma per i consumer di C, i chiamanti potrebbero essere sorpresi di dover qualificarsi con il modulo.</span><span class="sxs-lookup"><span data-stu-id="f6031-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="f6031-122">Applicare con attenzione`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="f6031-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="f6031-123">Il `[<AutoOpen>]` costrutto può inquinare la portata di ciò che è disponibile per i chiamanti, e la risposta a dove qualcosa viene da è "magia".</span><span class="sxs-lookup"><span data-stu-id="f6031-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="f6031-124">Non è una buona cosa.</span><span class="sxs-lookup"><span data-stu-id="f6031-124">This is not a good thing.</span></span> <span data-ttu-id="f6031-125">Un'eccezione a questa regola è la libreria di base di F , anche se questo fatto è anche un po ' controverso).</span><span class="sxs-lookup"><span data-stu-id="f6031-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="f6031-126">Tuttavia, è una comodità se si dispone di funzionalità di supporto per un'API pubblica che si desidera organizzare separatamente da tale API pubblica.</span><span class="sxs-lookup"><span data-stu-id="f6031-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="f6031-127">In questo modo è possibile separare in modo pulito i dettagli di implementazione dall'API pubblica di una funzione senza dover qualificare completamente un helper ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f6031-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="f6031-128">Inoltre, l'esposizione di metodi di estensione e generatori di `[<AutoOpen>]`espressioni a livello di spazio dei nomi può essere espressa in modo non completo con .</span><span class="sxs-lookup"><span data-stu-id="f6031-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="f6031-129">Utilizzare `[<RequireQualifiedAccess>]` ogni volta che i nomi potrebbero entrare in conflitto o si ritiene che aiuta con la leggibilità</span><span class="sxs-lookup"><span data-stu-id="f6031-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="f6031-130">L'aggiunta dell'attributo `[<RequireQualifiedAccess>]` a un modulo indica che il modulo non può essere aperto e che i riferimenti agli elementi del modulo richiedono l'accesso completo esplicito.</span><span class="sxs-lookup"><span data-stu-id="f6031-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="f6031-131">Ad esempio, `Microsoft.FSharp.Collections.List` il modulo ha questo attributo.</span><span class="sxs-lookup"><span data-stu-id="f6031-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="f6031-132">Ciò è utile quando le funzioni e i valori nel modulo hanno nomi che potrebbero entrare in conflitto con i nomi in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="f6031-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="f6031-133">Richiedere l'accesso qualificato può aumentare notevolmente la manutenibilità a lungo termine e l'evolvabilità di una libreria.</span><span class="sxs-lookup"><span data-stu-id="f6031-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="f6031-134">Ordinare `open` le istruzioni in modo topologico</span><span class="sxs-lookup"><span data-stu-id="f6031-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="f6031-135">In F , l'ordine delle dichiarazioni è importante, ad esempio con `open` le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="f6031-136">Questo è a differenza di `using` c'è, in cui l'effetto di e `using static` è indipendente dall'ordine di tali istruzioni in un file.</span><span class="sxs-lookup"><span data-stu-id="f6031-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="f6031-137">In F , gli elementi aperti in un ambito possono nascondere altri già presenti.</span><span class="sxs-lookup"><span data-stu-id="f6031-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="f6031-138">Ciò significa che `open` le istruzioni di riordino potrebbero modificare il significato del codice.</span><span class="sxs-lookup"><span data-stu-id="f6031-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="f6031-139">Di conseguenza, qualsiasi ordinamento `open` arbitrario di tutte le istruzioni (ad esempio, alfanumericamente) non è consigliato, per esservi un comportamento diverso che ci si potrebbe aspettare.</span><span class="sxs-lookup"><span data-stu-id="f6031-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="f6031-140">Invece, si consiglia di ordinarli [topologicamente](https://en.wikipedia.org/wiki/Topological_sorting); ovvero ordinare le `open` istruzioni nell'ordine in cui sono definiti i _livelli_ del sistema.</span><span class="sxs-lookup"><span data-stu-id="f6031-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="f6031-141">Si può anche prendere in considerazione l'esecuzione di ordinamento alfanumerico all'interno di diversi livelli topologici.</span><span class="sxs-lookup"><span data-stu-id="f6031-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="f6031-142">Ad esempio, ecco l'ordinamento topologico per il file API pubblico del servizio del compilatore F .</span><span class="sxs-lookup"><span data-stu-id="f6031-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="f6031-143">Si noti che un'interruzione di riga separa i livelli topologici, con ogni livello ordinato alfanumericamente in seguito.</span><span class="sxs-lookup"><span data-stu-id="f6031-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="f6031-144">Questo organizza correttamente il codice senza eseguire accidentalmente lo shadowing dei valori.</span><span class="sxs-lookup"><span data-stu-id="f6031-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="f6031-145">Utilizzare le classi per contenere valori che hanno effetti collateraliUse classes to contain values that have side effects</span><span class="sxs-lookup"><span data-stu-id="f6031-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="f6031-146">Esistono molte volte quando l'inizializzazione di un valore può avere effetti collaterali, ad esempio la creazione di un'istanza di un contesto in un database o in un'altra risorsa remota.</span><span class="sxs-lookup"><span data-stu-id="f6031-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="f6031-147">Si è tentati di inizializzare tali elementi in un modulo e utilizzarlo nelle funzioni successive:It istempting to initialize such things in a module and use it in subsequent functions:</span><span class="sxs-lookup"><span data-stu-id="f6031-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="f6031-148">Questa è spesso una cattiva idea per alcuni motivi:</span><span class="sxs-lookup"><span data-stu-id="f6031-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="f6031-149">Innanzitutto, la configurazione dell'applicazione `dep1` `dep2`viene inserita nella codebase con e .</span><span class="sxs-lookup"><span data-stu-id="f6031-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="f6031-150">Questo è difficile da gestire in codebase più grandi.</span><span class="sxs-lookup"><span data-stu-id="f6031-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="f6031-151">In secondo luogo, i dati inizializzati in modo statico non devono includere valori che non sono thread-safe se il componente stesso utilizzerà più thread.</span><span class="sxs-lookup"><span data-stu-id="f6031-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="f6031-152">Questo è chiaramente `dep3`violato da .</span><span class="sxs-lookup"><span data-stu-id="f6031-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="f6031-153">Infine, l'inizializzazione del modulo viene compilata in un costruttore statico per l'intera unità di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f6031-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="f6031-154">Se si verifica un errore nell'inizializzazione del valore `TypeInitializationException` let-bound in tale modulo, si manifesta come un che viene quindi memorizzato nella cache per l'intera durata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6031-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="f6031-155">Questo può essere difficile da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="f6031-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="f6031-156">Di solito c'è un'eccezione interna che si può tentare di ragionare, ma se non c'è, allora non si può dire quale sia la causa principale.</span><span class="sxs-lookup"><span data-stu-id="f6031-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="f6031-157">Usare invece una classe semplice per contenere le dipendenze:Instead, just use a simple class to hold dependencies:</span><span class="sxs-lookup"><span data-stu-id="f6031-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="f6031-158">Ciò consente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f6031-158">This enables the following:</span></span>

1. <span data-ttu-id="f6031-159">Push di qualsiasi stato dipendente all'esterno dell'API stessa.</span><span class="sxs-lookup"><span data-stu-id="f6031-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="f6031-160">La configurazione può ora essere eseguita al di fuori dell'API.</span><span class="sxs-lookup"><span data-stu-id="f6031-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="f6031-161">Gli errori di inizializzazione per i `TypeInitializationException`valori dipendenti non si manifestano probabilmente come file .</span><span class="sxs-lookup"><span data-stu-id="f6031-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="f6031-162">L'API è ora più facile da testare.</span><span class="sxs-lookup"><span data-stu-id="f6031-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="f6031-163">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="f6031-163">Error management</span></span>

<span data-ttu-id="f6031-164">La gestione degli errori nei sistemi di grandi dimensioni è un'attività complessa e sfumata, e non ci sono proiettili d'argento nel garantire che i sistemi siano a tolleranza di errore e si comportino bene.</span><span class="sxs-lookup"><span data-stu-id="f6031-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="f6031-165">Le seguenti linee guida dovrebbero offrire indicazioni per la navigazione in questo spazio difficile.</span><span class="sxs-lookup"><span data-stu-id="f6031-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="f6031-166">Rappresentare i casi di errore e lo stato non valido nei tipi intrinseci al dominio</span><span class="sxs-lookup"><span data-stu-id="f6031-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="f6031-167">Con [le unioni discriminate](../language-reference/discriminated-unions.md), F , consente di rappresentare lo stato del programma difettoso nel sistema di tipi.</span><span class="sxs-lookup"><span data-stu-id="f6031-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="f6031-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f6031-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="f6031-169">In questo caso, ci sono tre modi noti che il prelievo di denaro da un conto bancario può fallire.</span><span class="sxs-lookup"><span data-stu-id="f6031-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="f6031-170">Ogni caso di errore è rappresentato nel tipo e può quindi essere gestito in modo sicuro in tutto il programma.</span><span class="sxs-lookup"><span data-stu-id="f6031-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="f6031-171">In generale, se è possibile modellare i diversi modi in cui può **verificarsi** un errore nel dominio, il codice di gestione degli errori non viene più considerato come un elemento analogo a quello che è necessario gestire oltre al normale flusso del programma.</span><span class="sxs-lookup"><span data-stu-id="f6031-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="f6031-172">È semplicemente una parte del normale flusso del programma, e non considerato **eccezionale**.</span><span class="sxs-lookup"><span data-stu-id="f6031-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="f6031-173">Ci sono due vantaggi principali a questo:</span><span class="sxs-lookup"><span data-stu-id="f6031-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="f6031-174">È più facile da gestire quando il dominio cambia nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f6031-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="f6031-175">I casi di errore sono più facili da unit test.</span><span class="sxs-lookup"><span data-stu-id="f6031-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="f6031-176">Utilizzare le eccezioni quando gli errori non possono essere rappresentati con i tipi</span><span class="sxs-lookup"><span data-stu-id="f6031-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="f6031-177">Non tutti gli errori possono essere rappresentati in un dominio problematico.</span><span class="sxs-lookup"><span data-stu-id="f6031-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="f6031-178">Questi tipi di errori sono di natura *eccezionale,* pertanto la possibilità di generare e intercettare le eccezioni in F.</span><span class="sxs-lookup"><span data-stu-id="f6031-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="f6031-179">In primo luogo, si consiglia di leggere le linee guida per la progettazione delle [eccezioni](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="f6031-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="f6031-180">Questi sono applicabili anche a F .</span><span class="sxs-lookup"><span data-stu-id="f6031-180">These are also applicable to F#.</span></span>

<span data-ttu-id="f6031-181">I costrutti principali disponibili in F , ai fini della generazione di eccezioni devono essere considerati nel seguente ordine di preferenza:</span><span class="sxs-lookup"><span data-stu-id="f6031-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="f6031-182">Funzione</span><span class="sxs-lookup"><span data-stu-id="f6031-182">Function</span></span> | <span data-ttu-id="f6031-183">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6031-183">Syntax</span></span> | <span data-ttu-id="f6031-184">Scopo</span><span class="sxs-lookup"><span data-stu-id="f6031-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="f6031-185">Genera `System.ArgumentNullException` un con il nome dell'argomento specificato.</span><span class="sxs-lookup"><span data-stu-id="f6031-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="f6031-186">Genera `System.ArgumentException` un con un messaggio e un nome di argomento specificati.</span><span class="sxs-lookup"><span data-stu-id="f6031-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="f6031-187">Genera `System.InvalidOperationException` un con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="f6031-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="f6031-188">Meccanismo generico per la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="f6031-189">Genera `System.Exception` un con il messaggio specificato.</span><span class="sxs-lookup"><span data-stu-id="f6031-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="f6031-190">Genera `System.Exception` un con un messaggio determinato dalla stringa di formato e dai relativi input.</span><span class="sxs-lookup"><span data-stu-id="f6031-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="f6031-191">Utilizzare `nullArg` `invalidArg` , `invalidOp` e come `ArgumentNullException`meccanismo per generare , `ArgumentException` e `InvalidOperationException` quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="f6031-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="f6031-192">Le `failwith` `failwithf` funzioni e in genere devono `Exception` essere evitate perché generano il tipo di base, non un'eccezione specifica.</span><span class="sxs-lookup"><span data-stu-id="f6031-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="f6031-193">In base alle Linee guida per la progettazione delle [eccezioni](../../standard/design-guidelines/exceptions.md), si desidera generare eccezioni più specifiche quando è possibile.</span><span class="sxs-lookup"><span data-stu-id="f6031-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="f6031-194">Utilizzo della sintassi di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="f6031-194">Using exception-handling syntax</span></span>

<span data-ttu-id="f6031-195">F , supporta i `try...with` modelli di eccezione tramite la sintassi:</span><span class="sxs-lookup"><span data-stu-id="f6031-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="f6031-196">La riconciliazione della funzionalità da eseguire in caso di eccezione con criteri di ricerca può essere un po' complessa se si desidera mantenere pulito il codice.</span><span class="sxs-lookup"><span data-stu-id="f6031-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="f6031-197">Uno di questi modi per gestire questa situazione consiste nell'utilizzare [i modelli attivi](../language-reference/active-patterns.md) come mezzo per raggruppare la funzionalità che circonda un caso di errore con un'eccezione stessa.</span><span class="sxs-lookup"><span data-stu-id="f6031-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="f6031-198">Ad esempio, è possibile utilizzare un'API che, quando genera un'eccezione, racchiude informazioni importanti nei metadati dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f6031-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="f6031-199">Annullare il wrapping di un valore utile nel corpo dell'eccezione acquisita all'interno del modello attivo e restituire tale valore può essere utile in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="f6031-200">Non utilizzare la gestione degli errori monadica per sostituire le eccezioni</span><span class="sxs-lookup"><span data-stu-id="f6031-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="f6031-201">Le eccezioni sono considerate un po' tabù nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="f6031-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="f6031-202">Infatti, le eccezioni violano la purezza, quindi è sicuro considerarle non abbastanza funzionali.</span><span class="sxs-lookup"><span data-stu-id="f6031-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="f6031-203">Tuttavia, questo ignora la realtà di dove deve essere eseguito il codice e che possono verificarsi errori di runtime.</span><span class="sxs-lookup"><span data-stu-id="f6031-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="f6031-204">In generale, scrivere codice sul presupposto che la maggior parte delle cose non sono né puro né totale, per ridurre al minimo spiacevoli sorprese.</span><span class="sxs-lookup"><span data-stu-id="f6031-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="f6031-205">È importante considerare i seguenti punti di forza/aspetti di base delle eccezioni in relazione alla loro pertinenza e appropriatezza nel runtime .NET e nell'ecosistema multilingua nel suo complesso:</span><span class="sxs-lookup"><span data-stu-id="f6031-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="f6031-206">Essi contengono informazioni diagnostiche dettagliate, che è molto utile quando si esegue il debug di un problema.</span><span class="sxs-lookup"><span data-stu-id="f6031-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="f6031-207">Sono ben compresi dal runtime e da altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="f6031-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="f6031-208">Possono ridurre boilerplate significativo rispetto al codice che va fuori del suo modo di *evitare* eccezioni implementando qualche sottoinsieme della loro semantica su una base ad hoc.</span><span class="sxs-lookup"><span data-stu-id="f6031-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="f6031-209">Questo terzo punto è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="f6031-209">This third point is critical.</span></span> <span data-ttu-id="f6031-210">Per le operazioni complesse non banali, la mancata utilizzo delle eccezioni può comportare la gestione di strutture come questa:</span><span class="sxs-lookup"><span data-stu-id="f6031-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="f6031-211">Che può facilmente portare a codice fragile come pattern matching su errori "tipizzati a stringa":</span><span class="sxs-lookup"><span data-stu-id="f6031-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="f6031-212">Inoltre, si può essere tentati di ingoiare qualsiasi eccezione nel desiderio di una funzione "semplice" che restituisce un tipo "bello":</span><span class="sxs-lookup"><span data-stu-id="f6031-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="f6031-213">Sfortunatamente, `tryReadAllText` può generare numerose eccezioni in base alla miriade di cose che possono accadere in un file system e questo codice elimina tutte le informazioni su ciò che potrebbe effettivamente andare storto nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="f6031-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="f6031-214">Se si sostituisce questo codice con un tipo di risultato, si torna all'analisi dei messaggi di errore "con tipo stringa":</span><span class="sxs-lookup"><span data-stu-id="f6031-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="f6031-215">E l'inserimento dell'oggetto eccezione stesso nel `Error` costruttore impone solo di gestire correttamente il tipo di eccezione nel sito di chiamata anziché nella funzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="f6031-216">In questo modo in modo efficace crea eccezioni controllate, che sono notoriamente poco divertente da gestire come chiamante di un'API.</span><span class="sxs-lookup"><span data-stu-id="f6031-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="f6031-217">Una buona alternativa agli esempi precedenti consiste nell'intercettare eccezioni *specifiche* e restituire un valore significativo nel contesto di tale eccezione.</span><span class="sxs-lookup"><span data-stu-id="f6031-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="f6031-218">Se si `tryReadAllText` modifica la `None` funzione come segue, ha più significato:</span><span class="sxs-lookup"><span data-stu-id="f6031-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="f6031-219">Invece di funzionare come un catch-all, questa funzione ora gestirà correttamente il caso quando un file non è stato trovato e assegnare tale significato a un ritorno.</span><span class="sxs-lookup"><span data-stu-id="f6031-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="f6031-220">Questo valore restituito può eseguire il mapping a tale caso di errore, senza eliminare le informazioni contestuali o forzare i chiamanti a gestire un caso che potrebbe non essere rilevante in quel punto del codice.</span><span class="sxs-lookup"><span data-stu-id="f6031-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="f6031-221">I tipi, ad `Result<'Success, 'Error>` esempio, sono appropriati per le operazioni di base in cui non sono annidati e i tipi facoltativi F , sono perfetti per rappresentare quando un elemento può restituire *qualcosa* o *niente.*</span><span class="sxs-lookup"><span data-stu-id="f6031-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="f6031-222">Tuttavia, non sostituiscono le eccezioni e non devono essere utilizzati nel tentativo di sostituire le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="f6031-223">Piuttosto, dovrebbero essere applicati con giudizio per affrontare aspetti specifici della politica di gestione delle eccezioni e degli errori in modi mirati.</span><span class="sxs-lookup"><span data-stu-id="f6031-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="f6031-224">Applicazione parziale e programmazione senza punti</span><span class="sxs-lookup"><span data-stu-id="f6031-224">Partial application and point-free programming</span></span>

<span data-ttu-id="f6031-225">F è supporta l'applicazione parziale e, pertanto, vari modi per programmare in uno stile senza punti.</span><span class="sxs-lookup"><span data-stu-id="f6031-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="f6031-226">Questo può essere utile per il riutilizzo del codice all'interno di un modulo o l'implementazione di qualcosa, ma non è qualcosa da esporre pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="f6031-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="f6031-227">In generale, la programmazione senza punti non è una virtù in sé e per sé e può aggiungere una barriera cognitiva significativa per le persone che non sono immerse nello stile.</span><span class="sxs-lookup"><span data-stu-id="f6031-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="f6031-228">Non usare applicazioni parziali e currying in API pubblicheDo not use partial application and currying in public APIs</span><span class="sxs-lookup"><span data-stu-id="f6031-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="f6031-229">Con poche eccezioni, l'uso dell'applicazione parziale nelle API pubbliche può creare confusione per i consumer.</span><span class="sxs-lookup"><span data-stu-id="f6031-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="f6031-230">In `let`genere, i valori associati a -e-bound nel codice F , sono **valori**, non **valori di funzione**.</span><span class="sxs-lookup"><span data-stu-id="f6031-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="f6031-231">La combinazione di valori e valori di funzione può comportare il salvataggio di un numero ridotto di `>>` righe di codice in cambio di un bel po ' di sovraccarico cognitivo, soprattutto se combinato con operatori come comporre funzioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="f6031-232">Considerare le implicazioni degli strumenti per la programmazione senza punti</span><span class="sxs-lookup"><span data-stu-id="f6031-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="f6031-233">Le funzioni sottoposte a currysima non etichettano i relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="f6031-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="f6031-234">Questo ha implicazioni di strumenti.</span><span class="sxs-lookup"><span data-stu-id="f6031-234">This has tooling implications.</span></span> <span data-ttu-id="f6031-235">Si considerino le due funzioni seguenti:Consider the following two functions:</span><span class="sxs-lookup"><span data-stu-id="f6031-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="f6031-236">Entrambe sono funzioni `funcWithApplication` valide, ma è una funzione sottoposta a currysima.</span><span class="sxs-lookup"><span data-stu-id="f6031-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="f6031-237">Quando si passa il mouse sui relativi tipi in un editor, viene visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f6031-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="f6031-238">Nel sito di chiamata, le descrizioni comandi negli strumenti come Visual `string` Studio `int` non foranno informazioni significative su ciò che i tipi di input e rappresentano effettivamente.</span><span class="sxs-lookup"><span data-stu-id="f6031-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="f6031-239">Se si incontra codice `funcWithApplication` senza punti come quello che è pubblicamente consumabile, si consiglia di fare un'espansione completa in modo che gli strumenti possono raccogliere nomi significativi per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f6031-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="f6031-240">Inoltre, il debug di codice privo di punti può essere difficile, se non impossibile.</span><span class="sxs-lookup"><span data-stu-id="f6031-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="f6031-241">Gli strumenti di debug si basano `let` su valori associati a nomi (ad esempio, associazioni) in modo che sia possibile esaminare i valori intermedi a metà dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="f6031-242">Quando il codice non ha valori da controllare, non c'è nulla di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="f6031-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="f6031-243">In futuro, gli strumenti di debug potrebbero evolvere per sintetizzare questi valori in base ai percorsi eseguiti in precedenza, ma non è una buona idea coprire le scommesse su *potenziali* funzionalità di debug.</span><span class="sxs-lookup"><span data-stu-id="f6031-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="f6031-244">Considerare l'applicazione parziale come una tecnica per ridurre la boilerplate interna</span><span class="sxs-lookup"><span data-stu-id="f6031-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="f6031-245">A differenza del punto precedente, l'applicazione parziale è uno strumento meraviglioso per ridurre boilerplate all'interno di un'applicazione o le profondità interne di un'API.</span><span class="sxs-lookup"><span data-stu-id="f6031-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="f6031-246">Può essere utile per unit test l'implementazione di API più complesse, in cui boilerplate è spesso un problema da gestire.</span><span class="sxs-lookup"><span data-stu-id="f6031-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="f6031-247">Ad esempio, il codice seguente mostra come è possibile ottenere ciò che la maggior parte dei framework di simulazione offrono senza prendere una dipendenza esterna da tale framework e dover imparare un'API su misura correlata.</span><span class="sxs-lookup"><span data-stu-id="f6031-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="f6031-248">Si consideri ad esempio la topografia della soluzione seguente:For example, consider the following solution toography:</span><span class="sxs-lookup"><span data-stu-id="f6031-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="f6031-249">`ImplementationLogic.fsproj`potrebbe esporre codice come:</span><span class="sxs-lookup"><span data-stu-id="f6031-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="f6031-250">Unit `Transactions.doTransaction` test `ImplementationLogic.Tests.fsproj` in è facile:</span><span class="sxs-lookup"><span data-stu-id="f6031-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="f6031-251">L'applicazione `doTransaction` parziale con un oggetto di contesto fittizio consente di chiamare la funzione in tutti gli unit test senza dover costruire ogni volta un contesto fittizio:Partially applying with a mocking context object lets you call the function in all of your unit tests without needing construct a mocked context each time:</span><span class="sxs-lookup"><span data-stu-id="f6031-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="f6031-252">Questa tecnica non deve essere applicata universalmente all'intera codebase, ma è un buon modo per ridurre boilerplate per interni complicati e unit test tali elementi interni.</span><span class="sxs-lookup"><span data-stu-id="f6031-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="f6031-253">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="f6031-253">Access control</span></span>

<span data-ttu-id="f6031-254">Per il controllo [di accesso,](../language-reference/access-control.md)f è disponibile più opzioni, ereditate da quelle disponibili nel runtime di .NET.</span><span class="sxs-lookup"><span data-stu-id="f6031-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="f6031-255">Questi non sono utilizzabili solo per i tipi - è possibile utilizzarli anche per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="f6031-256">Preferisci`public` tipi e membri non disponibili fino a quando non ne hai bisogno per essere pubblicamente consumabili.</span><span class="sxs-lookup"><span data-stu-id="f6031-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="f6031-257">Questo riduce al minimo anche ciò che i consumatori coppia a.</span><span class="sxs-lookup"><span data-stu-id="f6031-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="f6031-258">Sforzarsi di mantenere `private`tutte le funzionalità di supporto .</span><span class="sxs-lookup"><span data-stu-id="f6031-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="f6031-259">Si consideri `[<AutoOpen>]` l'uso di in un modulo privato di funzioni di supporto se diventano numerosi.</span><span class="sxs-lookup"><span data-stu-id="f6031-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="f6031-260">Inferenza del tipo e genericsType inference and generics</span><span class="sxs-lookup"><span data-stu-id="f6031-260">Type inference and generics</span></span>

<span data-ttu-id="f6031-261">L'inferenza del tipo può evitare di digitare un sacco di boilerplate.</span><span class="sxs-lookup"><span data-stu-id="f6031-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="f6031-262">E la generalizzazione automatica nel compilatore F , può aiutare a scrivere codice più generico senza quasi alcuno sforzo aggiuntivo da parte vostra.</span><span class="sxs-lookup"><span data-stu-id="f6031-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="f6031-263">Tuttavia, queste caratteristiche non sono universalmente buone.</span><span class="sxs-lookup"><span data-stu-id="f6031-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="f6031-264">Valutare la possibilità di etichettare i nomi degli argomenti con tipi espliciti nelle API pubbliche e non basarsi sull'inferenza dei tipi per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="f6031-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="f6031-265">Il motivo è che **si** dovrebbe avere il controllo della forma dell'API, non il compilatore.</span><span class="sxs-lookup"><span data-stu-id="f6031-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="f6031-266">Anche se il compilatore può eseguire un ottimo lavoro nell'inferenza dei tipi per l'utente, è possibile modificare la forma dell'API se gli elementi interni su cui si basa hanno tipi modificati.</span><span class="sxs-lookup"><span data-stu-id="f6031-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="f6031-267">Questo può essere quello che vuoi, ma quasi certamente si tradurrà in una modifica DELL'API di rottura che i consumatori a valle dovranno quindi affrontare.</span><span class="sxs-lookup"><span data-stu-id="f6031-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="f6031-268">Al contrario, se controlli in modo esplicito la forma dell'API pubblica, puoi controllare queste modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="f6031-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="f6031-269">In termini DDD, questo può essere considerato come un livello anti-corruzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="f6031-270">È consigliabile assegnare un nome significativo agli argomenti generici.</span><span class="sxs-lookup"><span data-stu-id="f6031-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="f6031-271">A meno che non si stia scrivendo codice veramente generico che non sia specifico di un particolare dominio, un nome significativo può aiutare altri programmatori a comprendere il dominio in cui stanno lavorando.</span><span class="sxs-lookup"><span data-stu-id="f6031-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="f6031-272">Ad esempio, un `'Document` parametro di tipo denominato nel contesto dell'interazione con un database di documenti rende più chiaro che i tipi di documento generici possono essere accettati dalla funzione o dal membro con cui si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="f6031-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="f6031-273">Valutare la possibilità di denominare i parametri di tipo generico con PascalCase.Consider naming generic type parameters with PascalCase.</span><span class="sxs-lookup"><span data-stu-id="f6031-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="f6031-274">Questo è il modo generale per eseguire operazioni in .NET, pertanto è consigliabile usare PascalCase anziché snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="f6031-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="f6031-275">Infine, la generalizzazione automatica non è sempre una manna per gli utenti che non hanno familiarità con F o una base di codice di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="f6031-276">L'utilizzo di componenti generici comporta un sovraccarico cognitivo.</span><span class="sxs-lookup"><span data-stu-id="f6031-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="f6031-277">Inoltre, se le funzioni generalizzate automaticamente non vengono utilizzate con tipi di input diversi (per non parlare se sono destinate a essere utilizzate come tali), non vi è alcun vantaggio reale per loro di essere generici in quel momento.</span><span class="sxs-lookup"><span data-stu-id="f6031-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="f6031-278">Considerare sempre se il codice che si sta scrivendo trarrà effettivamente vantaggio dall'essere generico.</span><span class="sxs-lookup"><span data-stu-id="f6031-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="f6031-279">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="f6031-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="f6031-280">Preferisci struct per tipi di dati di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="f6031-280">Prefer structs for small data types</span></span>

<span data-ttu-id="f6031-281">L'uso di struct (chiamati anche tipi di valore) può spesso comportare prestazioni più elevate per un codice perché in genere evita l'allocazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="f6031-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="f6031-282">Tuttavia, gli struct non sono sempre un pulsante "go faster": se la dimensione dei dati in uno struct supera i 16 byte, la copia dei dati può spesso comportare una maggiore produttività rispetto all'utilizzo di un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f6031-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="f6031-283">Per determinare se è necessario utilizzare uno struct, considerare le condizioni seguenti:To determine if you should use a struct, consider the following conditions:</span><span class="sxs-lookup"><span data-stu-id="f6031-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="f6031-284">Se le dimensioni dei dati sono di 16 byte o inferiori.</span><span class="sxs-lookup"><span data-stu-id="f6031-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="f6031-285">Se è probabile che molti di questi tipi di dati siano residenti in memoria in un programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="f6031-286">Se si applica la prima condizione, è in genere necessario usare uno struct.</span><span class="sxs-lookup"><span data-stu-id="f6031-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="f6031-287">Se si applicano entrambi, è necessario usare quasi sempre uno struct.</span><span class="sxs-lookup"><span data-stu-id="f6031-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="f6031-288">Ci possono essere alcuni casi in cui si applicano le condizioni precedenti, ma l'utilizzo di uno struct non è migliore o peggiore rispetto all'utilizzo di un tipo di riferimento, ma è probabile che siano rari.</span><span class="sxs-lookup"><span data-stu-id="f6031-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="f6031-289">È importante misurare sempre quando si apportano modifiche come questa, però, e non operare su ipotesi o intuizione.</span><span class="sxs-lookup"><span data-stu-id="f6031-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="f6031-290">Preferisci le tuple struct quando si raggruppano tipi di valori di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="f6031-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="f6031-291">Si considerino le due funzioni seguenti:Consider the following two functions:</span><span class="sxs-lookup"><span data-stu-id="f6031-291">Consider the following two functions:</span></span>

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

<span data-ttu-id="f6031-292">Quando si confrontano queste funzioni con uno strumento di benchmarking `runWithStructTuple` statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che la funzione che utilizza tuple struct viene eseguita il 40% più velocemente e non alloca memoria.</span><span class="sxs-lookup"><span data-stu-id="f6031-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="f6031-293">Tuttavia, questi risultati non saranno sempre il caso nel proprio codice.</span><span class="sxs-lookup"><span data-stu-id="f6031-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="f6031-294">Se si contrassegna `inline`una funzione come , il codice che utilizza tuple di riferimento può ottenere alcune ottimizzazioni aggiuntive o codice che verrà allocato potrebbe semplicemente essere ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="f6031-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="f6031-295">Si dovrebbe sempre misurare i risultati ogni volta che le prestazioni sono interessate, e non operare mai sulla base di presupposti o intuizioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="f6031-296">Preferisci i record struct quando il tipo di dati è piccolo</span><span class="sxs-lookup"><span data-stu-id="f6031-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="f6031-297">La regola generale descritta in precedenza vale anche per i [tipi di record F .](../language-reference/records.md)</span><span class="sxs-lookup"><span data-stu-id="f6031-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="f6031-298">Considerare i tipi di dati e le funzioni seguenti che li elaborano:Consider the following data types and functions that process them:</span><span class="sxs-lookup"><span data-stu-id="f6031-298">Consider the following data types and functions that process them:</span></span>

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

<span data-ttu-id="f6031-299">È simile al codice di tupla precedente, ma questa volta l'esempio usa record e una funzione interna inline.</span><span class="sxs-lookup"><span data-stu-id="f6031-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="f6031-300">Quando si confrontano queste funzioni con uno strumento di benchmarking `processStructPoint` statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che viene eseguito quasi il 60% più velocemente e non alloca nulla nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f6031-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="f6031-301">Preferire le unioni discriminate struct quando il tipo di dati è piccolo</span><span class="sxs-lookup"><span data-stu-id="f6031-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="f6031-302">Le osservazioni precedenti sulle prestazioni con tuple struct e record sono inoltre valida per [le unioni discriminate](../language-reference/discriminated-unions.md)di F .</span><span class="sxs-lookup"><span data-stu-id="f6031-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="f6031-303">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6031-303">Consider the following code:</span></span>

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

<span data-ttu-id="f6031-304">È comune definire unioni discriminate con un solo caso come questa per la modellazione di dominio.</span><span class="sxs-lookup"><span data-stu-id="f6031-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="f6031-305">Quando si confrontano queste funzioni con uno strumento di benchmarking statistico come [BenchmarkDotNet](https://benchmarkdotnet.org/), si noterà che `structReverseName` viene eseguito circa il 25% più velocemente rispetto `reverseName` alle stringhe di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="f6031-306">Per le stringhe di grandi dimensioni, entrambe le prestazioni più o meno lo stesso.</span><span class="sxs-lookup"><span data-stu-id="f6031-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="f6031-307">Quindi, in questo caso, è sempre preferibile usare uno struct.</span><span class="sxs-lookup"><span data-stu-id="f6031-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="f6031-308">Come accennato in precedenza, misurare sempre e non operare su presupposti o intuizioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="f6031-309">Anche se l'esempio precedente ha mostrato che una struttura Discriminateed Union ha prodotto prestazioni migliori, è comune avere unioni discriminate più grandi durante la modellazione di un dominio.</span><span class="sxs-lookup"><span data-stu-id="f6031-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="f6031-310">Tipi di dati più grandi di questo tipo potrebbero non funzionare altrettanto bene se sono struct a seconda delle operazioni su di essi, poiché potrebbero essere coinvolti più copie.</span><span class="sxs-lookup"><span data-stu-id="f6031-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="f6031-311">Programmazione funzionale e mutazione</span><span class="sxs-lookup"><span data-stu-id="f6031-311">Functional programming and mutation</span></span>

<span data-ttu-id="f6031-312">I valori di F , non sono modificabili per impostazione predefinita, che consente di evitare determinate classi di bug (in particolare quelli che coinvolgono la concorrenza e il parallelismo).</span><span class="sxs-lookup"><span data-stu-id="f6031-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="f6031-313">Tuttavia, in alcuni casi, al fine di ottenere un'efficienza ottimale (o anche ragionevole) del tempo di esecuzione o allocazioni di memoria, un intervallo di lavoro può essere implementato meglio utilizzando la mutazione di stato sul posto.</span><span class="sxs-lookup"><span data-stu-id="f6031-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="f6031-314">Ciò è possibile in una base opt-in con F , con la `mutable` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="f6031-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="f6031-315">L'uso di `mutable` in F , può essere in contrasto con la purezza funzionale.</span><span class="sxs-lookup"><span data-stu-id="f6031-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="f6031-316">Questo è comprensibile, ma la purezza funzionale ovunque può essere in contrasto con gli obiettivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="f6031-317">Un compromesso consiste nell'incapsulare la mutazione in modo che i chiamanti non devono preoccuparsi di ciò che accade quando chiamano una funzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="f6031-318">In questo modo è possibile scrivere un'interfaccia funzionale su un'implementazione basata su mutazione per il codice critico per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="f6031-319">Eseguire il wrapping di codice modificabile in interfacce non modificabiliWrap mutable code in unmutable interfaces</span><span class="sxs-lookup"><span data-stu-id="f6031-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="f6031-320">Con la trasparenza referenziale come obiettivo, è fondamentale scrivere codice che non esponga il ventre modificabile delle funzioni critiche per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f6031-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="f6031-321">Ad esempio, il codice `Array.contains` seguente implementa la funzione nella libreria di base di F , che segue:</span><span class="sxs-lookup"><span data-stu-id="f6031-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="f6031-322">La chiamata di questa funzione più volte non modifica la matrice sottostante, né richiede di mantenere qualsiasi stato modificabile nell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f6031-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="f6031-323">È referenzialmente trasparente, anche se quasi ogni riga di codice al suo interno utilizza la mutazione.</span><span class="sxs-lookup"><span data-stu-id="f6031-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="f6031-324">Considerare l'incapsulamento di dati modificabili nelle classiConsider encapsulating mutable data in classes</span><span class="sxs-lookup"><span data-stu-id="f6031-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="f6031-325">Nell'esempio precedente è stata utilizzata una singola funzione per incapsulare le operazioni utilizzando dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="f6031-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="f6031-326">Questo non è sempre sufficiente per set di dati più complessi.</span><span class="sxs-lookup"><span data-stu-id="f6031-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="f6031-327">Si considerino i seguenti set di funzioni:</span><span class="sxs-lookup"><span data-stu-id="f6031-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="f6031-328">Questo codice è performante, ma espone la struttura di dati basata sulla mutazione che i chiamanti sono responsabili della gestione.</span><span class="sxs-lookup"><span data-stu-id="f6031-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="f6031-329">È possibile eseguire il wrapping all'interno di una classe senza membri sottostanti che possono essere modificati:This can be wrapped inside of a class with no underlying members that can change:</span><span class="sxs-lookup"><span data-stu-id="f6031-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="f6031-330">`Closure1Table`incapsula la struttura di dati basata sulla mutazione sottostante, non costringendo i chiamanti a mantenere la struttura di dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="f6031-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="f6031-331">Le classi sono un modo efficace per incapsulare dati e routine basate su mutazioni senza esporre i dettagli ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="f6031-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="f6031-332">Preferire `let mutable` fare riferimento alle celle</span><span class="sxs-lookup"><span data-stu-id="f6031-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="f6031-333">Le celle di riferimento sono un modo per rappresentare il riferimento a un valore anziché il valore stesso.</span><span class="sxs-lookup"><span data-stu-id="f6031-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="f6031-334">Sebbene possano essere utilizzati per il codice critico per le prestazioni, non sono consigliati.</span><span class="sxs-lookup"><span data-stu-id="f6031-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="f6031-335">Prendere in considerazione gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6031-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="f6031-336">L'uso di una cella di riferimento ora "inquina" tutto il codice successivo con la dover dereferenziare e rireferenziare i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="f6031-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="f6031-337">Invece, `let mutable`considerare :</span><span class="sxs-lookup"><span data-stu-id="f6031-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="f6031-338">A parte il singolo punto di mutazione nel mezzo dell'espressione `acc` lambda, tutto il codice che tocca può farlo `let`in un modo che non è diverso dall'uso di un valore non modificabile associato a normal.</span><span class="sxs-lookup"><span data-stu-id="f6031-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="f6031-339">Questo renderà più facile cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f6031-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="f6031-340">Programmazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="f6031-340">Object programming</span></span>

<span data-ttu-id="f6031-341">F è il supporto completo per gli oggetti e concetti orientati agli oggetti (OO).</span><span class="sxs-lookup"><span data-stu-id="f6031-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="f6031-342">Anche se molti concetti di OO sono potenti e utili, non tutti sono ideali da usare.</span><span class="sxs-lookup"><span data-stu-id="f6031-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="f6031-343">Gli elenchi seguenti offrono indicazioni sulle categorie di funzionalità OO a livello generale.</span><span class="sxs-lookup"><span data-stu-id="f6031-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="f6031-344">**Considerare l'utilizzo di queste funzionalità in molte situazioni:Consider using these features in many situations:**</span><span class="sxs-lookup"><span data-stu-id="f6031-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="f6031-345">Notazione del`x.Length`punto ( )</span><span class="sxs-lookup"><span data-stu-id="f6031-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="f6031-346">Membri di istanza</span><span class="sxs-lookup"><span data-stu-id="f6031-346">Instance members</span></span>
* <span data-ttu-id="f6031-347">Costruttori impliciti</span><span class="sxs-lookup"><span data-stu-id="f6031-347">Implicit constructors</span></span>
* <span data-ttu-id="f6031-348">Membri statici</span><span class="sxs-lookup"><span data-stu-id="f6031-348">Static members</span></span>
* <span data-ttu-id="f6031-349">Notazione indicizzatore (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="f6031-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="f6031-350">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="f6031-350">Named and Optional arguments</span></span>
* <span data-ttu-id="f6031-351">Interfacce e implementazioni di interfacce</span><span class="sxs-lookup"><span data-stu-id="f6031-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="f6031-352">**Non raggiungere per queste caratteristiche prima, ma non applicarle giudiziosamente quando sono convenienti per risolvere un problema:**</span><span class="sxs-lookup"><span data-stu-id="f6031-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="f6031-353">Overload di un metodo</span><span class="sxs-lookup"><span data-stu-id="f6031-353">Method overloading</span></span>
* <span data-ttu-id="f6031-354">Dati modificabili incapsulatiEncapsulated mutable data</span><span class="sxs-lookup"><span data-stu-id="f6031-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="f6031-355">Operatori sui tipi</span><span class="sxs-lookup"><span data-stu-id="f6031-355">Operators on types</span></span>
* <span data-ttu-id="f6031-356">Proprietà automatiche</span><span class="sxs-lookup"><span data-stu-id="f6031-356">Auto properties</span></span>
* <span data-ttu-id="f6031-357">Implementazione `IDisposable` e`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="f6031-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="f6031-358">Estensioni del tipo</span><span class="sxs-lookup"><span data-stu-id="f6031-358">Type extensions</span></span>
* <span data-ttu-id="f6031-359">Eventi</span><span class="sxs-lookup"><span data-stu-id="f6031-359">Events</span></span>
* <span data-ttu-id="f6031-360">Struct</span><span class="sxs-lookup"><span data-stu-id="f6031-360">Structs</span></span>
* <span data-ttu-id="f6031-361">Delegati</span><span class="sxs-lookup"><span data-stu-id="f6031-361">Delegates</span></span>
* <span data-ttu-id="f6031-362">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="f6031-362">Enums</span></span>

<span data-ttu-id="f6031-363">**In genere evitare queste funzionalità a meno che non sia necessario utilizzarle:**</span><span class="sxs-lookup"><span data-stu-id="f6031-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="f6031-364">Gerarchie di tipi basate sull'ereditarietà e ereditarietà dell'implementazione</span><span class="sxs-lookup"><span data-stu-id="f6031-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="f6031-365">Null e`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="f6031-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="f6031-366">Preferire la composizione all'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="f6031-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="f6031-367">[La composizione sull'ereditarietà](https://en.wikipedia.org/wiki/Composition_over_inheritance) è un linguaggio di lunga data che può rispettare un buon codice F.</span><span class="sxs-lookup"><span data-stu-id="f6031-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="f6031-368">Il principio fondamentale è che non è necessario esporre una classe base e forzare i chiamanti a ereditare da tale classe di base per ottenere funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6031-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="f6031-369">Usare le espressioni di oggetto per implementare le interfacce se non è necessaria una classeUse object expressions to implement interfaces if you don't need a class</span><span class="sxs-lookup"><span data-stu-id="f6031-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="f6031-370">[Le espressioni di](../language-reference/object-expressions.md) oggetto consentono di implementare interfacce in tempo reale, associando l'interfaccia implementata a un valore senza dover eseguire questa operazione all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="f6031-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="f6031-371">Ciò è utile, soprattutto se è _necessario implementare solo_ l'interfaccia e non è necessario per una classe completa.</span><span class="sxs-lookup"><span data-stu-id="f6031-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="f6031-372">Ad esempio, ecco il codice che viene eseguito in [Ionide](http://ionide.io/) per fornire un'azione di `open` correzione del codice se è stato aggiunto un simbolo per il fatto per il seguente:</span><span class="sxs-lookup"><span data-stu-id="f6031-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="f6031-373">Poiché non è necessaria una classe quando si interagisce con l'API del codice di Visual Studio, le espressioni di oggetto sono uno strumento ideale per questo.</span><span class="sxs-lookup"><span data-stu-id="f6031-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="f6031-374">Sono inoltre utili per gli unit test, quando si desidera eseguire lo stub di un'interfaccia con routine di test in modo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="f6031-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="f6031-375">Considerare le abbreviazioni di tipo per abbreviare le firmeConsider Type Abbreviations to shorten signatures</span><span class="sxs-lookup"><span data-stu-id="f6031-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="f6031-376">[Abbreviazioni](../language-reference/type-abbreviations.md) di tipo sono un modo pratico per assegnare un'etichetta a un altro tipo, ad esempio una firma di funzione o un tipo più complesso.</span><span class="sxs-lookup"><span data-stu-id="f6031-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="f6031-377">Ad esempio, l'alias seguente assegna un'etichetta a ciò che è necessario per definire un calcolo con [CNTK](https://docs.microsoft.com/cognitive-toolkit/), una libreria di deep learning:</span><span class="sxs-lookup"><span data-stu-id="f6031-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="f6031-378">Il `Computation` nome è un modo pratico per indicare qualsiasi funzione che corrisponde alla firma che è aliasing.</span><span class="sxs-lookup"><span data-stu-id="f6031-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="f6031-379">L'utilizzo di abbreviazioni di tipo come questa è conveniente e consente codice più conciso.</span><span class="sxs-lookup"><span data-stu-id="f6031-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="f6031-380">Evitare di utilizzare abbreviazioni di tipo per rappresentare il dominio</span><span class="sxs-lookup"><span data-stu-id="f6031-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="f6031-381">Anche se le abbreviazioni di tipo sono utili per assegnare un nome alle firme delle funzioni, possono creare confusione quando si abbreviano altri tipi.</span><span class="sxs-lookup"><span data-stu-id="f6031-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="f6031-382">Si consideri questa abbreviazione:Consider this abbreviation:</span><span class="sxs-lookup"><span data-stu-id="f6031-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="f6031-383">Questo può essere fonte di confusione in diversi modi:This can be confusing in multiple ways:</span><span class="sxs-lookup"><span data-stu-id="f6031-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="f6031-384">`BufferSize`non è un'astrazione; è solo un altro nome per un numero intero.</span><span class="sxs-lookup"><span data-stu-id="f6031-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="f6031-385">Se `BufferSize` viene esposto in un'API pubblica, può essere `int`facilmente interpretato erroneamente per significare più di un semplice .</span><span class="sxs-lookup"><span data-stu-id="f6031-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="f6031-386">In genere, i tipi di dominio hanno più `int`attributi e non sono tipi primitivi come .</span><span class="sxs-lookup"><span data-stu-id="f6031-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="f6031-387">Questa abbreviazione viola tale ipotesi.</span><span class="sxs-lookup"><span data-stu-id="f6031-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="f6031-388">L'utilizzo `BufferSize` di maiuscole e minuscole di (PascalCase) implica che questo tipo contiene più dati.</span><span class="sxs-lookup"><span data-stu-id="f6031-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="f6031-389">Questo alias non offre maggiore chiarezza rispetto a fornire un argomento denominato a una funzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="f6031-390">L'abbreviazione non si manifesterà nel linguaggio intermedio compilato; è solo un numero intero e questo alias è un costrutto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f6031-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="f6031-391">In sintesi, la trappola con le abbreviazioni di tipo è che **non** sono astrazioni sui tipi che stanno abbreviando.</span><span class="sxs-lookup"><span data-stu-id="f6031-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="f6031-392">Nell'esempio precedente, `BufferSize` è `int` solo un sotto le coperte, senza dati aggiuntivi, `int` né alcun beneficio dal sistema di tipi oltre a quello che già ha.</span><span class="sxs-lookup"><span data-stu-id="f6031-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="f6031-393">Un approccio alternativo all'utilizzo delle abbreviazioni di tipo per rappresentare un dominio consiste nell'utilizzare unioni discriminate caso singolo.</span><span class="sxs-lookup"><span data-stu-id="f6031-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="f6031-394">Il campione precedente può essere modellato come segue:The previous sample can be modeled as follows:</span><span class="sxs-lookup"><span data-stu-id="f6031-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="f6031-395">Se si scrive codice che `BufferSize` opera in termini di e il relativo valore sottostante, è necessario costruirne uno anziché passare qualsiasi intero arbitrario:If you write code that operates in terms of and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span><span class="sxs-lookup"><span data-stu-id="f6031-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="f6031-396">In questo modo si riduce la probabilità di `send` passare erroneamente un `BufferSize` numero intero arbitrario nella funzione, perché il chiamante deve costruire un tipo per eseguire il wrapping di un valore prima di chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="f6031-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
