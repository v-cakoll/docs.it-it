---
title: 'Linee guida per la formattazione del codice F #'
description: 'Altre linee guida per la formattazione del codice F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 9c6e80509e9a5654e6514674d38c02e2a6b44e37
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734642"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="8bead-103">Linee guida per la formattazione del codice F #</span><span class="sxs-lookup"><span data-stu-id="8bead-103">F# code formatting guidelines</span></span>

<span data-ttu-id="8bead-104">Questo articolo offre linee guida per la modalità di formattazione del codice in modo che sia il codice F #:</span><span class="sxs-lookup"><span data-stu-id="8bead-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="8bead-105">In genere visualizzati come più leggibili</span><span class="sxs-lookup"><span data-stu-id="8bead-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="8bead-106">È in base alle convenzioni applicate formattando altri editor e strumenti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8bead-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="8bead-107">Simile ad altro codice online</span><span class="sxs-lookup"><span data-stu-id="8bead-107">Similar to other code online</span></span>

<span data-ttu-id="8bead-108">Queste indicazioni si basano [una guida completa alle convenzioni di formattazione F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) dal [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="8bead-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="8bead-109">Regole generali per il rientro</span><span class="sxs-lookup"><span data-stu-id="8bead-109">General rules for indentation</span></span>

<span data-ttu-id="8bead-110">F # per impostazione predefinita, utilizza gli spazi vuoti significativi.</span><span class="sxs-lookup"><span data-stu-id="8bead-110">F# uses significant white space by default.</span></span> <span data-ttu-id="8bead-111">Le linee guida seguenti sono utili per fornire istruzioni su come organizzare alcune problematiche di che ciò può essere imposti.</span><span class="sxs-lookup"><span data-stu-id="8bead-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="8bead-112">Uso di spazi</span><span class="sxs-lookup"><span data-stu-id="8bead-112">Using spaces</span></span>

<span data-ttu-id="8bead-113">Quando il rientro è necessario, è necessario utilizzare spazi, tabulazioni non.</span><span class="sxs-lookup"><span data-stu-id="8bead-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="8bead-114">È necessario almeno uno spazio.</span><span class="sxs-lookup"><span data-stu-id="8bead-114">At least one space is required.</span></span> <span data-ttu-id="8bead-115">L'organizzazione può creare gli standard di codifica per specificare il numero di spazi da utilizzare per il rientro. due, tre o quattro spazi del rientro a ogni livello in cui si verifica il rientro è tipico.</span><span class="sxs-lookup"><span data-stu-id="8bead-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="8bead-116">**Si consiglia di 4 spazi per il rientro.**</span><span class="sxs-lookup"><span data-stu-id="8bead-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="8bead-117">Ciò premesso, rientro dei programmi è una questione soggettiva.</span><span class="sxs-lookup"><span data-stu-id="8bead-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="8bead-118">Le variazioni sono OK, ma è la prima regola è necessario seguire *coerenza di rientro*.</span><span class="sxs-lookup"><span data-stu-id="8bead-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="8bead-119">Scegliere uno stile di rientro in genere accettato e usarlo in modo sistematico in tutta la codebase.</span><span class="sxs-lookup"><span data-stu-id="8bead-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="8bead-120">Formattazione di righe vuote</span><span class="sxs-lookup"><span data-stu-id="8bead-120">Formatting blank lines</span></span>

* <span data-ttu-id="8bead-121">Separati (funzione) e classe definizioni di primo livello con due righe vuote.</span><span class="sxs-lookup"><span data-stu-id="8bead-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="8bead-122">Le definizioni di metodo all'interno di una classe sono separate da una singola riga vuota.</span><span class="sxs-lookup"><span data-stu-id="8bead-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="8bead-123">Righe vuote aggiuntive possono essere usate (solo se necessario) per separare gruppi di funzioni correlate.</span><span class="sxs-lookup"><span data-stu-id="8bead-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="8bead-124">È possibile omettere le righe vuote tra una serie di istruzioni a riga singola correlati (ad esempio, un set di implementazioni fittizie).</span><span class="sxs-lookup"><span data-stu-id="8bead-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="8bead-125">Usare le righe vuote in funzioni, solo se necessario, per indicare sezioni logiche.</span><span class="sxs-lookup"><span data-stu-id="8bead-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="8bead-126">Formattazione di commenti</span><span class="sxs-lookup"><span data-stu-id="8bead-126">Formatting comments</span></span>

<span data-ttu-id="8bead-127">In genere preferire più commenti con barra doppia commenti del blocco di stile di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="8bead-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="8bead-128">Commenti inline devono convertire in maiuscolo la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="8bead-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="8bead-129">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="8bead-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="8bead-130">Usano la notazione camel per le funzioni e i valori associati a classe, espressione di associazione e con associazione a modello</span><span class="sxs-lookup"><span data-stu-id="8bead-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="8bead-131">È comune e accettati F # stile usano la notazione camel per tutti i nomi associati come variabili locali o in Criteri di corrispondenza e le definizioni di funzione.</span><span class="sxs-lookup"><span data-stu-id="8bead-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="8bead-132">In locale con associazione a funzioni nelle classi devono inoltre usano la notazione camel.</span><span class="sxs-lookup"><span data-stu-id="8bead-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="8bead-133">Usano la notazione camel per le funzioni pubbliche associata al modulo</span><span class="sxs-lookup"><span data-stu-id="8bead-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="8bead-134">Quando una funzione associata al modulo fa parte di un'API pubblica, è necessario utilizzare camelCase:</span><span class="sxs-lookup"><span data-stu-id="8bead-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="8bead-135">Usano la notazione camel per le funzioni e i valori associati a modulo interni e privati</span><span class="sxs-lookup"><span data-stu-id="8bead-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="8bead-136">Usano la notazione camel per i valori privati associata al modulo, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8bead-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="8bead-137">Funzioni ad hoc negli script</span><span class="sxs-lookup"><span data-stu-id="8bead-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="8bead-138">Valori che compongono l'implementazione interna di un tipo o un modulo</span><span class="sxs-lookup"><span data-stu-id="8bead-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="8bead-139">Usano la notazione camel per i parametri</span><span class="sxs-lookup"><span data-stu-id="8bead-139">Use camelCase for parameters</span></span>

<span data-ttu-id="8bead-140">Tutti i parametri devono usano la notazione camel in base alle convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="8bead-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="8bead-141">Per i moduli usano la notazione Pascal</span><span class="sxs-lookup"><span data-stu-id="8bead-141">Use PascalCase for modules</span></span>

<span data-ttu-id="8bead-142">Tutti i moduli (livello superiore, interni, privati, annidati) utilizzino PascalCase.</span><span class="sxs-lookup"><span data-stu-id="8bead-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="8bead-143">Usano la notazione Pascal per le dichiarazioni di tipi, membri e le etichette</span><span class="sxs-lookup"><span data-stu-id="8bead-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="8bead-144">Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="8bead-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="8bead-145">I membri all'interno di tipi e le etichette per i record e unioni discriminate devono inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="8bead-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="8bead-146">Usano la notazione Pascal per i costrutti intrinseci per .NET</span><span class="sxs-lookup"><span data-stu-id="8bead-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="8bead-147">Spazi dei nomi, le eccezioni, eventi e progetto /`.dll` nomi dovrebbero inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="8bead-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="8bead-148">Non solo si rende il consumo da altri linguaggi .NET sembrano più naturali agli utenti, è anche coerenza con le convenzioni di denominazione .NET che probabile incontrare.</span><span class="sxs-lookup"><span data-stu-id="8bead-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="8bead-149">Evitare caratteri di sottolineatura nei nomi</span><span class="sxs-lookup"><span data-stu-id="8bead-149">Avoid underscores in names</span></span>

<span data-ttu-id="8bead-150">In passato, alcune librerie F # sono utilizzati caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="8bead-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="8bead-151">Tuttavia, questo è non è più diffuso, in parte perché è in conflitto con le convenzioni di denominazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="8bead-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="8bead-152">Ciò premesso, alcuni programmatori F # usano caratteri di sottolineatura frequentemente, in parte per motivi storici e tolleranza d'errore e riguardo è importante.</span><span class="sxs-lookup"><span data-stu-id="8bead-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="8bead-153">Tuttavia, tenere presente che lo stile è spesso disliked da altri utenti che dispongono di una scelta sull'opportunità di usarlo.</span><span class="sxs-lookup"><span data-stu-id="8bead-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="8bead-154">Alcune eccezioni includono l'interoperabilità con i componenti nativi, in cui i caratteri di sottolineatura sono molto comuni.</span><span class="sxs-lookup"><span data-stu-id="8bead-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="8bead-155">Usare gli operatori standard F #</span><span class="sxs-lookup"><span data-stu-id="8bead-155">Use standard F# operators</span></span>

<span data-ttu-id="8bead-156">Gli operatori seguenti vengono definiti nella libreria standard di F # e devono essere usati invece di definire gli equivalenti.</span><span class="sxs-lookup"><span data-stu-id="8bead-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="8bead-157">Utilizzo di questi operatori è consigliata perché tende a rendere il codice più leggibile e idiomatico.</span><span class="sxs-lookup"><span data-stu-id="8bead-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="8bead-158">Gli sviluppatori con esperienza in OCaml o altri linguaggi di programmazione funzionale possono essere abituati a diversi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="8bead-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="8bead-159">Nell'elenco seguente sono riepilogati gli operatori F # consigliati.</span><span class="sxs-lookup"><span data-stu-id="8bead-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="8bead-160">Utilizzare la sintassi di prefisso per i generics (`Foo<T>`) anziché la sintassi in forma suffissa (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="8bead-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="8bead-161">F # eredita sia lo stile di Machine Learning suffisso di denominazione dei tipi generici (ad esempio, `int list`), nonché il prefisso stile .NET (ad esempio, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="8bead-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="8bead-162">Preferisce lo stile di .NET, ad eccezione di quattro tipi specifici:</span><span class="sxs-lookup"><span data-stu-id="8bead-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="8bead-163">Per gli elenchi F #, utilizzare la forma suffissa: `int list` anziché `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="8bead-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="8bead-164">Per opzioni di F #, utilizzare la forma suffissa: `int option` anziché `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="8bead-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="8bead-165">Per le matrici di F #, usare il nome sintattico `int[]` invece `int array` o `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="8bead-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="8bead-166">Per le celle di riferimento, usare `int ref` invece `ref<int>` o `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="8bead-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="8bead-167">Per tutti gli altri tipi, usare la forma prefissa.</span><span class="sxs-lookup"><span data-stu-id="8bead-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="8bead-168">Formattazione di tuple</span><span class="sxs-lookup"><span data-stu-id="8bead-168">Formatting tuples</span></span>

<span data-ttu-id="8bead-169">Creazione di un'istanza di tupla devono essere racchiusi tra parentesi, e le virgole di delimitazione all'interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="8bead-169">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="8bead-170">Viene comunemente accettato per omettere le parentesi nei criteri di ricerca di tuple:</span><span class="sxs-lookup"><span data-stu-id="8bead-170">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="8bead-171">Formattazione di dichiarazioni di unione discriminata</span><span class="sxs-lookup"><span data-stu-id="8bead-171">Formatting discriminated union declarations</span></span>

<span data-ttu-id="8bead-172">Impostare un rientro `|` nella definizione del tipo da 4 spazi:</span><span class="sxs-lookup"><span data-stu-id="8bead-172">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="8bead-173">Formattazione di unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="8bead-173">Formatting discriminated unions</span></span>

<span data-ttu-id="8bead-174">Un'istanza le unioni discriminate suddivisi su più righe deve fornire dati in essi contenuti un nuovo ambito con rientro:</span><span class="sxs-lookup"><span data-stu-id="8bead-174">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="8bead-175">La parentesi di chiusura può essere anche in una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="8bead-175">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="8bead-176">Dichiarazioni di record di formattazione</span><span class="sxs-lookup"><span data-stu-id="8bead-176">Formatting record declarations</span></span>

<span data-ttu-id="8bead-177">Impostare un rientro `{` nel tipo di definizione da 4 spazi e avviare l'elenco dei campi nella stessa riga:</span><span class="sxs-lookup"><span data-stu-id="8bead-177">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address : string
      City : string
      Zip : string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address : string
    City : string
    Zip : string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
    
// Unusual in F#
type PostalAddress =
    { 
        Address : string
        City : string
        Zip : string
    }
```

<span data-ttu-id="8bead-178">Inserire il token di apertura nella stessa riga e il token di chiusura in una nuova riga è valida, ma tenere presente che è necessario usare il [sintassi dettagliata](../language-reference/verbose-syntax.md) per definire i membri (il `with` parola chiave):</span><span class="sxs-lookup"><span data-stu-id="8bead-178">Placing the opening token on the same line and the closing token on a new line is also fine, but be aware that you need to use the [verbose syntax](../language-reference/verbose-syntax.md) to define members (the `with` keyword):</span></span>

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address : string
    City : string
    Zip : string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a><span data-ttu-id="8bead-179">Formattazione di record</span><span class="sxs-lookup"><span data-stu-id="8bead-179">Formatting records</span></span>

<span data-ttu-id="8bead-180">Record brevi possono essere scritti in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="8bead-180">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="8bead-181">Record più lunghe deve utilizzare le nuove righe per le etichette:</span><span class="sxs-lookup"><span data-stu-id="8bead-181">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="8bead-182">Inserire il token di apertura nella stessa riga e il token di chiusura in una nuova riga è valida:</span><span class="sxs-lookup"><span data-stu-id="8bead-182">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

```fsharp
let rainbow = {
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
```

<span data-ttu-id="8bead-183">Per gli elementi di elenco e la matrice si applicano le stesse regole.</span><span class="sxs-lookup"><span data-stu-id="8bead-183">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="8bead-184">Formattazione di elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="8bead-184">Formatting lists and arrays</span></span>

<span data-ttu-id="8bead-185">Scrivere `x :: l` con spazi prima e dopo il `::` operator (`::` è un operatore di infissi, di conseguenza precedute e seguito da spazi) e `[1; 2; 3]` (`;` è un delimitatore, quindi seguito da uno spazio).</span><span class="sxs-lookup"><span data-stu-id="8bead-185">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="8bead-186">Usare sempre almeno uno spazio tra due operatori simile a parentesi graffa distinti.</span><span class="sxs-lookup"><span data-stu-id="8bead-186">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="8bead-187">Ad esempio, lasciare uno spazio tra un `[` e un `{`.</span><span class="sxs-lookup"><span data-stu-id="8bead-187">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="8bead-188">Gli elenchi e matrici suddivisi su più righe seguono una regola simile dei record:</span><span class="sxs-lookup"><span data-stu-id="8bead-188">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a><span data-ttu-id="8bead-189">Formattazione se le espressioni</span><span class="sxs-lookup"><span data-stu-id="8bead-189">Formatting if expressions</span></span>

<span data-ttu-id="8bead-190">Rientro di istruzioni condizionali varia a seconda di dimensioni delle espressioni che li compongono.</span><span class="sxs-lookup"><span data-stu-id="8bead-190">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="8bead-191">Se `cond`, `e1` e `e2` sono brevi, è sufficiente scriverli su un'unica riga:</span><span class="sxs-lookup"><span data-stu-id="8bead-191">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="8bead-192">Se uno dei due `cond`, `e1` o `e2` sono più lunghi, ma non su più righe:</span><span class="sxs-lookup"><span data-stu-id="8bead-192">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="8bead-193">Se le espressioni sono su più righe:</span><span class="sxs-lookup"><span data-stu-id="8bead-193">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="8bead-194">Più istruzioni condizionali, con `elif` e `else` vengono rientrate nello stesso ambito come il `if`:</span><span class="sxs-lookup"><span data-stu-id="8bead-194">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="8bead-195">Costrutti di modello corrispondenti</span><span class="sxs-lookup"><span data-stu-id="8bead-195">Pattern matching constructs</span></span>

<span data-ttu-id="8bead-196">Usare un `|` per ogni clausola di una corrispondenza con alcun rientro.</span><span class="sxs-lookup"><span data-stu-id="8bead-196">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="8bead-197">Se l'espressione è breve, è possibile utilizzare una singola riga se ogni sottoespressione anche è semplice.</span><span class="sxs-lookup"><span data-stu-id="8bead-197">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="8bead-198">Se l'espressione a destra del criterio corrispondente freccia è troppo grande, spostarlo alla riga seguente, con rientro un unico passaggio dai `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="8bead-198">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="8bead-199">Criteri di ricerca di funzioni anonime, a partire da `function`, devono in genere non impostare un rientro troppo lontano.</span><span class="sxs-lookup"><span data-stu-id="8bead-199">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="8bead-200">Ad esempio, è bene il rientro di un ambito come segue:</span><span class="sxs-lookup"><span data-stu-id="8bead-200">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="8bead-201">Criteri di ricerca nelle funzioni definite dal `let` oppure `let rec` deve essere rientrati 4 spazi dopo l'avvio di `let`, anche se `function` parola chiave viene usata:</span><span class="sxs-lookup"><span data-stu-id="8bead-201">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="8bead-202">Non è consigliabile allineare le frecce.</span><span class="sxs-lookup"><span data-stu-id="8bead-202">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="8bead-203">Formattazione try / with espressioni</span><span class="sxs-lookup"><span data-stu-id="8bead-203">Formatting try/with expressions</span></span>

<span data-ttu-id="8bead-204">Criteri di ricerca nel tipo di eccezione devono essere rientrato allo stesso livello `with`.</span><span class="sxs-lookup"><span data-stu-id="8bead-204">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="8bead-205">Formattazione dell'applicazione di parametro (funzione)</span><span class="sxs-lookup"><span data-stu-id="8bead-205">Formatting function parameter application</span></span>

<span data-ttu-id="8bead-206">In generale, la maggior parte delle applicazione di parametro di funzione viene eseguita nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="8bead-206">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="8bead-207">Se si vuole applicare parametri a una funzione in una nuova riga, impostare un rientro per un ambito.</span><span class="sxs-lookup"><span data-stu-id="8bead-207">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="8bead-208">Le stesse linee guida applicano per le espressioni lambda come argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="8bead-208">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="8bead-209">Se il corpo di un'espressione lambda, il corpo può contenere un'altra riga, rientrata in base a un ambito</span><span class="sxs-lookup"><span data-stu-id="8bead-209">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="8bead-210">Tuttavia, se il corpo di un'espressione lambda su più righe, è consigliabile estrarla factoring in funzioni separate piuttosto che dispone di un costrutto multilinea applicato come un singolo argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="8bead-210">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="8bead-211">Gli operatori infissi di formattazione</span><span class="sxs-lookup"><span data-stu-id="8bead-211">Formatting infix operators</span></span>

<span data-ttu-id="8bead-212">Operatori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="8bead-212">Separate operators by spaces.</span></span> <span data-ttu-id="8bead-213">Sono evidenti eccezioni a questa regola il `!` e `.` operatori.</span><span class="sxs-lookup"><span data-stu-id="8bead-213">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="8bead-214">Le espressioni di infissi sono OK lineup nella stessa colonna:</span><span class="sxs-lookup"><span data-stu-id="8bead-214">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="8bead-215">Formattazione operatori pipeline</span><span class="sxs-lookup"><span data-stu-id="8bead-215">Formatting pipeline operators</span></span>

<span data-ttu-id="8bead-216">Pipeline `|>` operatori devono essere inserito sotto le espressioni operano in base a.</span><span class="sxs-lookup"><span data-stu-id="8bead-216">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="8bead-217">Formattazione di moduli</span><span class="sxs-lookup"><span data-stu-id="8bead-217">Formatting modules</span></span>

<span data-ttu-id="8bead-218">Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non debba essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="8bead-218">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="8bead-219">Elementi Namespace non sono necessario impostare un rientro.</span><span class="sxs-lookup"><span data-stu-id="8bead-219">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="8bead-220">Formattazione di espressioni di oggetto e interfacce</span><span class="sxs-lookup"><span data-stu-id="8bead-220">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="8bead-221">Interfacce e le espressioni di oggetto devono essere allineate nello stesso modo con `member` viene applicato un rientro dopo 4 spazi.</span><span class="sxs-lookup"><span data-stu-id="8bead-221">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="8bead-222">Spazi vuoti nelle espressioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="8bead-222">Formatting white space in expressions</span></span>

<span data-ttu-id="8bead-223">Evitare gli spazi vuoti estranei nelle espressioni F #.</span><span class="sxs-lookup"><span data-stu-id="8bead-223">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="8bead-224">Gli argomenti denominati non necessario anche spazio che racchiudono il `=`:</span><span class="sxs-lookup"><span data-stu-id="8bead-224">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
