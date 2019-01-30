---
title: F#linee guida per la formattazione del codice
description: Per ulteriori linee guida per la formattazione, vedere F# codice.
ms.date: 11/26/2018
ms.openlocfilehash: b80a66f582d9fb8a2ec940ab565823483e7e4eea
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254822"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="c4561-103">F#linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="c4561-103">F# code formatting guidelines</span></span>

<span data-ttu-id="c4561-104">Questo articolo offre linee guida per la modalità di formattazione del codice in modo che il F# codice è:</span><span class="sxs-lookup"><span data-stu-id="c4561-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="c4561-105">In genere visualizzati come più leggibili</span><span class="sxs-lookup"><span data-stu-id="c4561-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="c4561-106">È in base alle convenzioni applicate formattando altri editor e strumenti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4561-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="c4561-107">Simile ad altro codice online</span><span class="sxs-lookup"><span data-stu-id="c4561-107">Similar to other code online</span></span>

<span data-ttu-id="c4561-108">Queste indicazioni si basano [una guida completa alla F# convenzioni di formattazione](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) dal [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="c4561-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="c4561-109">Regole generali per il rientro</span><span class="sxs-lookup"><span data-stu-id="c4561-109">General rules for indentation</span></span>

<span data-ttu-id="c4561-110">F#Per impostazione predefinita, utilizza gli spazi vuoti significativi.</span><span class="sxs-lookup"><span data-stu-id="c4561-110">F# uses significant white space by default.</span></span> <span data-ttu-id="c4561-111">Le linee guida seguenti sono utili per fornire istruzioni su come organizzare alcune problematiche di che ciò può essere imposti.</span><span class="sxs-lookup"><span data-stu-id="c4561-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="c4561-112">Uso di spazi</span><span class="sxs-lookup"><span data-stu-id="c4561-112">Using spaces</span></span>

<span data-ttu-id="c4561-113">Quando il rientro è necessario, è necessario utilizzare spazi, tabulazioni non.</span><span class="sxs-lookup"><span data-stu-id="c4561-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="c4561-114">È necessario almeno uno spazio.</span><span class="sxs-lookup"><span data-stu-id="c4561-114">At least one space is required.</span></span> <span data-ttu-id="c4561-115">L'organizzazione può creare gli standard di codifica per specificare il numero di spazi da utilizzare per il rientro. due, tre o quattro spazi del rientro a ogni livello in cui si verifica il rientro è tipico.</span><span class="sxs-lookup"><span data-stu-id="c4561-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="c4561-116">**Si consiglia di 4 spazi per il rientro.**</span><span class="sxs-lookup"><span data-stu-id="c4561-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="c4561-117">Ciò premesso, rientro dei programmi è una questione soggettiva.</span><span class="sxs-lookup"><span data-stu-id="c4561-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="c4561-118">Le variazioni sono OK, ma è la prima regola è necessario seguire *coerenza di rientro*.</span><span class="sxs-lookup"><span data-stu-id="c4561-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="c4561-119">Scegliere uno stile di rientro in genere accettato e usarlo in modo sistematico in tutta la codebase.</span><span class="sxs-lookup"><span data-stu-id="c4561-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="c4561-120">Formattazione di spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="c4561-120">Formatting white space</span></span>

<span data-ttu-id="c4561-121">F#è sensibile gli spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="c4561-121">F# is white space sensitive.</span></span> <span data-ttu-id="c4561-122">Sebbene la maggior parte delle semantica da spazi vuoti viene analizzata rientro corretto, esistono alcuni altri aspetti da considerare.</span><span class="sxs-lookup"><span data-stu-id="c4561-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="c4561-123">Formattazione di operatori nelle espressioni aritmetiche</span><span class="sxs-lookup"><span data-stu-id="c4561-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="c4561-124">Usare sempre uno spazio bianco intorno binarie espressioni aritmetiche:</span><span class="sxs-lookup"><span data-stu-id="c4561-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="c4561-125">Unario `-` gli operatori devono avere sempre il valore che vengono ricompilati impedendo seguono immediatamente:</span><span class="sxs-lookup"><span data-stu-id="c4561-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="c4561-126">Aggiunta di un carattere di spazio vuoto dopo la `-` operatore può generare confusione per gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c4561-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="c4561-127">In breve, è importante sempre:</span><span class="sxs-lookup"><span data-stu-id="c4561-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="c4561-128">Operatori binari snippet di inclusione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="c4561-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="c4561-129">Assenza di spazio vuoto finale dopo un operatore unario</span><span class="sxs-lookup"><span data-stu-id="c4561-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="c4561-130">La linea guida per l'operatore aritmetico binaria è particolarmente importante.</span><span class="sxs-lookup"><span data-stu-id="c4561-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="c4561-131">Esito negativo racchiudere un file binario `-` operatore, in combinazione con determinate opzioni di formattazione, potrebbe causare per interpretarlo come unario `-`.</span><span class="sxs-lookup"><span data-stu-id="c4561-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="c4561-132">Racchiudere una definizione di operatore personalizzato con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="c4561-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="c4561-133">Usare sempre gli spazi vuoti per racchiudere una definizione di operatore:</span><span class="sxs-lookup"><span data-stu-id="c4561-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="c4561-134">Per qualsiasi operatore personalizzato che inizia con `*`, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare ambiguità un compilatore.</span><span class="sxs-lookup"><span data-stu-id="c4561-134">For any custom operator that starts with `*`, you'll need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="c4561-135">Per questo motivo, è consigliabile che è sufficiente racchiudere le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="c4561-135">Because of this, it's recommended that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="c4561-136">Racchiudere le frecce di parametro di funzione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="c4561-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="c4561-137">Quando si definisce la firma di una funzione, usare uno spazio bianco intorno di `->` simbolo:</span><span class="sxs-lookup"><span data-stu-id="c4561-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="c4561-138">Formattazione di righe vuote</span><span class="sxs-lookup"><span data-stu-id="c4561-138">Formatting blank lines</span></span>

* <span data-ttu-id="c4561-139">Separati (funzione) e classe definizioni di primo livello con due righe vuote.</span><span class="sxs-lookup"><span data-stu-id="c4561-139">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="c4561-140">Le definizioni di metodo all'interno di una classe sono separate da una singola riga vuota.</span><span class="sxs-lookup"><span data-stu-id="c4561-140">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="c4561-141">Righe vuote aggiuntive possono essere usate (solo se necessario) per separare gruppi di funzioni correlate.</span><span class="sxs-lookup"><span data-stu-id="c4561-141">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="c4561-142">È possibile omettere le righe vuote tra una serie di istruzioni a riga singola correlati (ad esempio, un set di implementazioni fittizie).</span><span class="sxs-lookup"><span data-stu-id="c4561-142">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="c4561-143">Usare le righe vuote in funzioni, solo se necessario, per indicare sezioni logiche.</span><span class="sxs-lookup"><span data-stu-id="c4561-143">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="c4561-144">Formattazione di commenti</span><span class="sxs-lookup"><span data-stu-id="c4561-144">Formatting comments</span></span>

<span data-ttu-id="c4561-145">In genere preferire più commenti con barra doppia commenti del blocco di stile di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="c4561-145">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="c4561-146">Commenti inline devono convertire in maiuscolo la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="c4561-146">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="c4561-147">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c4561-147">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="c4561-148">Usano la notazione camel per le funzioni e i valori associati a classe, espressione di associazione e con associazione a modello</span><span class="sxs-lookup"><span data-stu-id="c4561-148">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="c4561-149">È comune e accettati F# usano la notazione camel per tutti i nomi associati come variabili locali o nei criteri di corrispondenza e definizioni di funzioni di stile.</span><span class="sxs-lookup"><span data-stu-id="c4561-149">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="c4561-150">In locale con associazione a funzioni nelle classi devono inoltre usano la notazione camel.</span><span class="sxs-lookup"><span data-stu-id="c4561-150">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="c4561-151">Usano la notazione camel per le funzioni pubbliche associata al modulo</span><span class="sxs-lookup"><span data-stu-id="c4561-151">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="c4561-152">Quando una funzione associata al modulo fa parte di un'API pubblica, è necessario utilizzare camelCase:</span><span class="sxs-lookup"><span data-stu-id="c4561-152">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="c4561-153">Usano la notazione camel per le funzioni e i valori associati a modulo interni e privati</span><span class="sxs-lookup"><span data-stu-id="c4561-153">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="c4561-154">Usano la notazione camel per i valori privati associata al modulo, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4561-154">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="c4561-155">Funzioni ad hoc negli script</span><span class="sxs-lookup"><span data-stu-id="c4561-155">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="c4561-156">Valori che compongono l'implementazione interna di un tipo o un modulo</span><span class="sxs-lookup"><span data-stu-id="c4561-156">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="c4561-157">Usano la notazione camel per i parametri</span><span class="sxs-lookup"><span data-stu-id="c4561-157">Use camelCase for parameters</span></span>

<span data-ttu-id="c4561-158">Tutti i parametri devono usano la notazione camel in base alle convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="c4561-158">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="c4561-159">Per i moduli usano la notazione Pascal</span><span class="sxs-lookup"><span data-stu-id="c4561-159">Use PascalCase for modules</span></span>

<span data-ttu-id="c4561-160">Tutti i moduli (livello superiore, interni, privati, annidati) utilizzino PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c4561-160">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="c4561-161">Usano la notazione Pascal per le dichiarazioni di tipi, membri e le etichette</span><span class="sxs-lookup"><span data-stu-id="c4561-161">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="c4561-162">Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c4561-162">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="c4561-163">I membri all'interno di tipi e le etichette per i record e unioni discriminate devono inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="c4561-163">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="c4561-164">Usano la notazione Pascal per i costrutti intrinseci per .NET</span><span class="sxs-lookup"><span data-stu-id="c4561-164">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="c4561-165">Spazi dei nomi, le eccezioni, eventi e progetto /`.dll` nomi dovrebbero inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="c4561-165">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="c4561-166">Non solo si rende il consumo da altri linguaggi .NET sembrano più naturali agli utenti, è anche coerenza con le convenzioni di denominazione .NET che probabile incontrare.</span><span class="sxs-lookup"><span data-stu-id="c4561-166">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="c4561-167">Evitare caratteri di sottolineatura nei nomi</span><span class="sxs-lookup"><span data-stu-id="c4561-167">Avoid underscores in names</span></span>

<span data-ttu-id="c4561-168">In passato, alcune F# librerie hanno utilizzati caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="c4561-168">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="c4561-169">Tuttavia, questo è non è più diffuso, in parte perché è in conflitto con le convenzioni di denominazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="c4561-169">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="c4561-170">Ciò premesso, alcune F# programmatori di utilizzare caratteri di sottolineatura frequentemente, in parte per motivi storici e tolleranza d'errore e riguardo è importante.</span><span class="sxs-lookup"><span data-stu-id="c4561-170">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="c4561-171">Tuttavia, tenere presente che lo stile è spesso disliked da altri utenti che dispongono di una scelta sull'opportunità di usarlo.</span><span class="sxs-lookup"><span data-stu-id="c4561-171">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="c4561-172">Alcune eccezioni includono l'interoperabilità con i componenti nativi, in cui i caratteri di sottolineatura sono molto comuni.</span><span class="sxs-lookup"><span data-stu-id="c4561-172">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="c4561-173">Standard di utilizzo F# operatori</span><span class="sxs-lookup"><span data-stu-id="c4561-173">Use standard F# operators</span></span>

<span data-ttu-id="c4561-174">Gli operatori seguenti vengono definiti di F# libreria standard e deve essere usato invece di definire gli equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c4561-174">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="c4561-175">Utilizzo di questi operatori è consigliata perché tende a rendere il codice più leggibile e idiomatico.</span><span class="sxs-lookup"><span data-stu-id="c4561-175">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="c4561-176">Gli sviluppatori con esperienza in OCaml o altri linguaggi di programmazione funzionale possono essere abituati a diversi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="c4561-176">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="c4561-177">L'elenco seguente riepiloga l'elemento consigliato F# operatori.</span><span class="sxs-lookup"><span data-stu-id="c4561-177">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="c4561-178">Utilizzare la sintassi di prefisso per i generics (`Foo<T>`) anziché la sintassi in forma suffissa (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="c4561-178">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="c4561-179">F#eredita sia lo stile di Machine Learning suffisso di denominazione dei tipi generici (ad esempio, `int list`), nonché il prefisso stile .NET (ad esempio, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="c4561-179">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="c4561-180">Preferisce lo stile di .NET, ad eccezione di quattro tipi specifici:</span><span class="sxs-lookup"><span data-stu-id="c4561-180">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="c4561-181">Per F# gli elenchi, usare la forma suffissa: `int list` anziché da `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="c4561-181">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="c4561-182">Per F# opzioni, utilizzare la forma suffissa: `int option` anziché da `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="c4561-182">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="c4561-183">Per F# le matrici, usare il nome sintattico `int[]` anziché da `int array` oppure `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="c4561-183">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="c4561-184">Per le celle di riferimento, usare `int ref` invece `ref<int>` o `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="c4561-184">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="c4561-185">Per tutti gli altri tipi, usare la forma prefissa.</span><span class="sxs-lookup"><span data-stu-id="c4561-185">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="c4561-186">Formattazione di tuple</span><span class="sxs-lookup"><span data-stu-id="c4561-186">Formatting tuples</span></span>

<span data-ttu-id="c4561-187">Creazione di un'istanza di tupla devono essere racchiusi tra parentesi, e le virgole di delimitazione all'interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="c4561-187">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="c4561-188">Viene comunemente accettato per omettere le parentesi nei criteri di ricerca di tuple:</span><span class="sxs-lookup"><span data-stu-id="c4561-188">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="c4561-189">Viene anche comunemente accettato per omettere le parentesi, se la tupla è il valore restituito di una funzione:</span><span class="sxs-lookup"><span data-stu-id="c4561-189">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```
<span data-ttu-id="c4561-190">In sintesi, preferisce le creazioni di istanze di racchiusi tra parentesi tuple, ma quando si usano le tuple per criteri di ricerca o un valore restituito, viene considerato corretto evitare le parentesi.</span><span class="sxs-lookup"><span data-stu-id="c4561-190">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="c4561-191">Formattazione di dichiarazioni di unione discriminata</span><span class="sxs-lookup"><span data-stu-id="c4561-191">Formatting discriminated union declarations</span></span>

<span data-ttu-id="c4561-192">Impostare un rientro `|` nella definizione del tipo da 4 spazi:</span><span class="sxs-lookup"><span data-stu-id="c4561-192">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="c4561-193">Formattazione di unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="c4561-193">Formatting discriminated unions</span></span>

<span data-ttu-id="c4561-194">Un'istanza le unioni discriminate suddivisi su più righe deve fornire dati in essi contenuti un nuovo ambito con rientro:</span><span class="sxs-lookup"><span data-stu-id="c4561-194">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="c4561-195">La parentesi di chiusura può essere anche in una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-195">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="c4561-196">Dichiarazioni di record di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-196">Formatting record declarations</span></span>

<span data-ttu-id="c4561-197">Impostare un rientro `{` nel tipo di definizione da 4 spazi e avviare l'elenco dei campi nella stessa riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-197">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
// Unusual in F#
type PostalAddress =
    { 
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="c4561-198">Risultare se si sta dichiarando le implementazioni di interfaccia o i membri nel record consiste nell'inserire il token di apertura su una nuova riga e il token di chiusura in una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-198">Placing the opening token on a new line and the closing token on a new line is preferrable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    { 
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="c4561-199">Formattazione di record</span><span class="sxs-lookup"><span data-stu-id="c4561-199">Formatting records</span></span>

<span data-ttu-id="c4561-200">Record brevi possono essere scritti in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-200">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="c4561-201">Record più lunghe deve utilizzare le nuove righe per le etichette:</span><span class="sxs-lookup"><span data-stu-id="c4561-201">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="c4561-202">Inserire l'apertura il contenuto a schede ambito su un token in una nuova riga, e il token di chiusura in una nuova riga è risultare se si è:</span><span class="sxs-lookup"><span data-stu-id="c4561-202">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferrable if you are:</span></span>

* <span data-ttu-id="c4561-203">Spostamento record all'interno di codice con ambiti diversi rientro</span><span class="sxs-lookup"><span data-stu-id="c4561-203">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="c4561-204">Piping in una funzione</span><span class="sxs-lookup"><span data-stu-id="c4561-204">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }
    
type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="c4561-205">Per gli elementi di elenco e la matrice si applicano le stesse regole.</span><span class="sxs-lookup"><span data-stu-id="c4561-205">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="c4561-206">Formattazione di elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="c4561-206">Formatting lists and arrays</span></span>

<span data-ttu-id="c4561-207">Scrivere `x :: l` con spazi prima e dopo il `::` operator (`::` è un operatore di infissi, di conseguenza precedute e seguito da spazi).</span><span class="sxs-lookup"><span data-stu-id="c4561-207">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="c4561-208">Elenco e le matrici dichiarate in un'unica riga devono avere uno spazio dopo la parentesi di apertura e prima della parentesi di chiusura:</span><span class="sxs-lookup"><span data-stu-id="c4561-208">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="c4561-209">Usare sempre almeno uno spazio tra due operatori simile a parentesi graffa distinti.</span><span class="sxs-lookup"><span data-stu-id="c4561-209">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="c4561-210">Ad esempio, lasciare uno spazio tra un `[` e un `{`.</span><span class="sxs-lookup"><span data-stu-id="c4561-210">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="c4561-211">Si applica la stessa delle linee guida per gli elenchi o matrici di tuple.</span><span class="sxs-lookup"><span data-stu-id="c4561-211">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="c4561-212">Gli elenchi e matrici suddivisi su più righe seguono una regola simile dei record:</span><span class="sxs-lookup"><span data-stu-id="c4561-212">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="c4561-213">E come con i record, dichiarando l'apertura e la parentesi di chiusura in una riga separata facilitare lo spostamento di codice intorno e il piping nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="c4561-213">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="c4561-214">Formattazione se le espressioni</span><span class="sxs-lookup"><span data-stu-id="c4561-214">Formatting if expressions</span></span>

<span data-ttu-id="c4561-215">Rientro di istruzioni condizionali varia a seconda di dimensioni delle espressioni che li compongono.</span><span class="sxs-lookup"><span data-stu-id="c4561-215">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="c4561-216">Se `cond`, `e1` e `e2` sono brevi, è sufficiente scriverli su un'unica riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-216">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="c4561-217">Se uno dei due `cond`, `e1` o `e2` sono più lunghi, ma non su più righe:</span><span class="sxs-lookup"><span data-stu-id="c4561-217">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="c4561-218">Se le espressioni sono su più righe:</span><span class="sxs-lookup"><span data-stu-id="c4561-218">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="c4561-219">Più istruzioni condizionali, con `elif` e `else` vengono rientrate nello stesso ambito come il `if`:</span><span class="sxs-lookup"><span data-stu-id="c4561-219">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="c4561-220">Costrutti di modello corrispondenti</span><span class="sxs-lookup"><span data-stu-id="c4561-220">Pattern matching constructs</span></span>

<span data-ttu-id="c4561-221">Usare un `|` per ogni clausola di una corrispondenza con alcun rientro.</span><span class="sxs-lookup"><span data-stu-id="c4561-221">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="c4561-222">Se l'espressione è breve, è possibile utilizzare una singola riga se ogni sottoespressione anche è semplice.</span><span class="sxs-lookup"><span data-stu-id="c4561-222">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="c4561-223">Se l'espressione a destra del criterio corrispondente freccia è troppo grande, spostarlo alla riga seguente, con rientro un unico passaggio dai `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="c4561-223">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="c4561-224">Criteri di ricerca di funzioni anonime, a partire da `function`, devono in genere non impostare un rientro troppo lontano.</span><span class="sxs-lookup"><span data-stu-id="c4561-224">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="c4561-225">Ad esempio, è bene il rientro di un ambito come segue:</span><span class="sxs-lookup"><span data-stu-id="c4561-225">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="c4561-226">Criteri di ricerca nelle funzioni definite dal `let` oppure `let rec` deve essere rientrati 4 spazi dopo l'avvio di `let`, anche se `function` parola chiave viene usata:</span><span class="sxs-lookup"><span data-stu-id="c4561-226">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="c4561-227">Non è consigliabile allineare le frecce.</span><span class="sxs-lookup"><span data-stu-id="c4561-227">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="c4561-228">Formattazione try / with espressioni</span><span class="sxs-lookup"><span data-stu-id="c4561-228">Formatting try/with expressions</span></span>

<span data-ttu-id="c4561-229">Criteri di ricerca nel tipo di eccezione devono essere rientrato allo stesso livello `with`.</span><span class="sxs-lookup"><span data-stu-id="c4561-229">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="c4561-230">Formattazione dell'applicazione di parametro (funzione)</span><span class="sxs-lookup"><span data-stu-id="c4561-230">Formatting function parameter application</span></span>

<span data-ttu-id="c4561-231">In generale, la maggior parte delle applicazione di parametro di funzione viene eseguita nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="c4561-231">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="c4561-232">Se si vuole applicare parametri a una funzione in una nuova riga, impostare un rientro per un ambito.</span><span class="sxs-lookup"><span data-stu-id="c4561-232">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="c4561-233">Le stesse linee guida applicano per le espressioni lambda come argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="c4561-233">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="c4561-234">Se il corpo di un'espressione lambda, il corpo può contenere un'altra riga, rientrata in base a un ambito</span><span class="sxs-lookup"><span data-stu-id="c4561-234">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="c4561-235">Tuttavia, se il corpo di un'espressione lambda su più righe, è consigliabile estrarla factoring in funzioni separate piuttosto che dispone di un costrutto multilinea applicato come un singolo argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="c4561-235">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="c4561-236">Gli operatori infissi di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-236">Formatting infix operators</span></span>

<span data-ttu-id="c4561-237">Operatori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="c4561-237">Separate operators by spaces.</span></span> <span data-ttu-id="c4561-238">Sono evidenti eccezioni a questa regola il `!` e `.` operatori.</span><span class="sxs-lookup"><span data-stu-id="c4561-238">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="c4561-239">Le espressioni di infissi sono OK lineup nella stessa colonna:</span><span class="sxs-lookup"><span data-stu-id="c4561-239">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="c4561-240">Formattazione operatori pipeline</span><span class="sxs-lookup"><span data-stu-id="c4561-240">Formatting pipeline operators</span></span>

<span data-ttu-id="c4561-241">Pipeline `|>` operatori devono essere inserito sotto le espressioni operano in base a.</span><span class="sxs-lookup"><span data-stu-id="c4561-241">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="c4561-242">Formattazione di moduli</span><span class="sxs-lookup"><span data-stu-id="c4561-242">Formatting modules</span></span>

<span data-ttu-id="c4561-243">Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non debba essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="c4561-243">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="c4561-244">Elementi Namespace non sono necessario impostare un rientro.</span><span class="sxs-lookup"><span data-stu-id="c4561-244">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="c4561-245">Formattazione di espressioni di oggetto e interfacce</span><span class="sxs-lookup"><span data-stu-id="c4561-245">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="c4561-246">Interfacce e le espressioni di oggetto devono essere allineate nello stesso modo con `member` viene applicato un rientro dopo 4 spazi.</span><span class="sxs-lookup"><span data-stu-id="c4561-246">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="c4561-247">Spazi vuoti nelle espressioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-247">Formatting white space in expressions</span></span>

<span data-ttu-id="c4561-248">Evitare gli spazi vuoti estranei nel F# le espressioni.</span><span class="sxs-lookup"><span data-stu-id="c4561-248">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="c4561-249">Gli argomenti denominati non necessario anche spazio che racchiudono il `=`:</span><span class="sxs-lookup"><span data-stu-id="c4561-249">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="c4561-250">Attributi di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-250">Formatting attributes</span></span>

<span data-ttu-id="c4561-251">[Gli attributi](../language-reference/attributes.md) vengono inseriti sopra un costrutto:</span><span class="sxs-lookup"><span data-stu-id="c4561-251">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="c4561-252">Gli attributi dei parametri di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-252">Formatting attributes on parameters</span></span>

<span data-ttu-id="c4561-253">Gli attributi possono essere anche punti di parametri.</span><span class="sxs-lookup"><span data-stu-id="c4561-253">Attributes can also be places on parameters.</span></span> <span data-ttu-id="c4561-254">In questo caso, inserire quindi sulla stessa riga come parametro e prima del nome:</span><span class="sxs-lookup"><span data-stu-id="c4561-254">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="c4561-255">Formattazione di più attributi</span><span class="sxs-lookup"><span data-stu-id="c4561-255">Formatting multiple attributes</span></span>

<span data-ttu-id="c4561-256">Quando vengono applicati più attributi a un costrutto che non è un parametro, devono essere posizionate in modo che sia presente un attributo per riga:</span><span class="sxs-lookup"><span data-stu-id="c4561-256">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="c4561-257">Quando applicato a un parametro, devono essere nella stessa riga e separati da un `;` separatore.</span><span class="sxs-lookup"><span data-stu-id="c4561-257">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="c4561-258">Valori letterali di formattazione</span><span class="sxs-lookup"><span data-stu-id="c4561-258">Formatting literals</span></span>

<span data-ttu-id="c4561-259">[F#valori letterali](../language-reference/literals.md) utilizzando il `Literal` attributo dovrebbe deve inserire l'attributo su una riga e usare camelCase di denominazione:</span><span class="sxs-lookup"><span data-stu-id="c4561-259">[F# literals](../language-reference/literals.md) using the `Literal` attribute should should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="c4561-260">Evitare di inserire l'attributo sulla stessa riga come valore.</span><span class="sxs-lookup"><span data-stu-id="c4561-260">Avoid placing the attribute on the same line as the value.</span></span>
