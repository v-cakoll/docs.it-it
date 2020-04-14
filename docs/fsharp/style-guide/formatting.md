---
title: Linee guida per la formattazione del codice F#
description: Informazioni sulle linee guida per la formattazione del codice F.
ms.date: 11/04/2019
ms.openlocfilehash: 2086b515b8ec9b69a44e2e65ca06fb320670dff2
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278938"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="791cc-103">Linee guida per la formattazione del codice F#</span><span class="sxs-lookup"><span data-stu-id="791cc-103">F# code formatting guidelines</span></span>

<span data-ttu-id="791cc-104">In questo articolo vengono fornite linee guida per la formattazione del codice in modo che il codice F .NET sia:This article offers guidelines for how to format your code so that your F's code is:</span><span class="sxs-lookup"><span data-stu-id="791cc-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="791cc-105">Generalmente considerato come più leggibile</span><span class="sxs-lookup"><span data-stu-id="791cc-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="791cc-106">È in conformità con le convenzioni applicate dagli strumenti di formattazione in Visual Studio e altri editor</span><span class="sxs-lookup"><span data-stu-id="791cc-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="791cc-107">Simile ad altro codice online</span><span class="sxs-lookup"><span data-stu-id="791cc-107">Similar to other code online</span></span>

<span data-ttu-id="791cc-108">Queste linee guida sono basate su [una guida completa alle convenzioni](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) di formattazione di F , di [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="791cc-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="791cc-109">Regole generali per il rientro</span><span class="sxs-lookup"><span data-stu-id="791cc-109">General rules for indentation</span></span>

<span data-ttu-id="791cc-110">Per impostazione predefinita, in F, per impostazione predefinita viene utilizzato uno spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="791cc-110">F# uses significant white space by default.</span></span> <span data-ttu-id="791cc-111">Le seguenti linee guida hanno lo scopo di fornire indicazioni su come destreggiarsi tra alcune sfide che questo può imporre.</span><span class="sxs-lookup"><span data-stu-id="791cc-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="791cc-112">Utilizzo degli spazi</span><span class="sxs-lookup"><span data-stu-id="791cc-112">Using spaces</span></span>

<span data-ttu-id="791cc-113">Quando è richiesto il rientro, è necessario utilizzare spazi, non tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="791cc-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="791cc-114">È necessario almeno uno spazio.</span><span class="sxs-lookup"><span data-stu-id="791cc-114">At least one space is required.</span></span> <span data-ttu-id="791cc-115">L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro; due, tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro è tipico.</span><span class="sxs-lookup"><span data-stu-id="791cc-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="791cc-116">**Si consigliano 4 spazi per rientro.**</span><span class="sxs-lookup"><span data-stu-id="791cc-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="791cc-117">Detto questo, l'indentazione dei programmi è una questione soggettiva.</span><span class="sxs-lookup"><span data-stu-id="791cc-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="791cc-118">Le variazioni sono OK, ma la prima regola da seguire è la *coerenza del rientro*.</span><span class="sxs-lookup"><span data-stu-id="791cc-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="791cc-119">Scegliere uno stile di rientro generalmente accettato e utilizzarlo sistematicamente in tutta la codebase.</span><span class="sxs-lookup"><span data-stu-id="791cc-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="791cc-120">Formattazione degli spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-120">Formatting white space</span></span>

<span data-ttu-id="791cc-121">Il f è sensibile allo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="791cc-121">F# is white space sensitive.</span></span> <span data-ttu-id="791cc-122">Anche se la maggior parte della semantica da spazi vuoti sono coperti da un rientro corretto, ci sono alcune altre cose da considerare.</span><span class="sxs-lookup"><span data-stu-id="791cc-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="791cc-123">Formattazione di operatori nelle espressioni aritmeticheFormatting operators in arithmetic expressions</span><span class="sxs-lookup"><span data-stu-id="791cc-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="791cc-124">Utilizzare sempre spazi vuoti intorno alle espressioni aritmetiche binarie:Always use white space around binary arithmetic expressions:</span><span class="sxs-lookup"><span data-stu-id="791cc-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="791cc-125">Gli `-` operatori unari devono sempre avere il valore che stanno negando immediatamente seguire:</span><span class="sxs-lookup"><span data-stu-id="791cc-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="791cc-126">L'aggiunta di un `-` carattere di spazio vuoto dopo l'operatore può causare confusione per gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="791cc-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="791cc-127">In sintesi, è importante:</span><span class="sxs-lookup"><span data-stu-id="791cc-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="791cc-128">Circondare gli operatori binari con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="791cc-129">Non avere mai spazi vuoti finali dopo un operatore unario</span><span class="sxs-lookup"><span data-stu-id="791cc-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="791cc-130">La linea guida dell'operatore aritmetico binario è particolarmente importante.</span><span class="sxs-lookup"><span data-stu-id="791cc-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="791cc-131">La mancata `-` circonciazione di un operatore binario, se `-`combinata con determinate scelte di formattazione, potrebbe comportare l'interpretazione come unario .</span><span class="sxs-lookup"><span data-stu-id="791cc-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="791cc-132">Racchiudere una definizione di operatore personalizzato con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="791cc-133">Utilizzare sempre spazi vuoti per racchiudere una definizione di operatore:</span><span class="sxs-lookup"><span data-stu-id="791cc-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="791cc-134">Per qualsiasi operatore `*` personalizzato che inizia con e che dispone di più di un carattere, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare un'ambiguità del compilatore.</span><span class="sxs-lookup"><span data-stu-id="791cc-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="791cc-135">Per questo motivo, è consigliabile racchiudere semplicemente le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="791cc-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="791cc-136">Frecce dei parametri della funzione surround con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="791cc-137">Quando si definisce la firma di `->` una funzione, utilizzare uno spazio bianco intorno al simbolo:</span><span class="sxs-lookup"><span data-stu-id="791cc-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="791cc-138">Argomenti della funzione surround con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-138">Surround function arguments with white space</span></span>

<span data-ttu-id="791cc-139">Quando si definisce una funzione, utilizzare uno spazio vuoto intorno a ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="791cc-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-very-long-member-definitions"></a><span data-ttu-id="791cc-140">Posizionare i parametri in una nuova riga per definizioni di membri molto lunghe</span><span class="sxs-lookup"><span data-stu-id="791cc-140">Place parameters on a new line for very long member definitions</span></span>

<span data-ttu-id="791cc-141">Se si dispone di una definizione di membro molto lunga, posizionare i parametri in nuove righe e applicare loro un rientro di un ambito.</span><span class="sxs-lookup"><span data-stu-id="791cc-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="791cc-142">Questo vale anche per i costruttori:This applies also to constructors:</span><span class="sxs-lookup"><span data-stu-id="791cc-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="791cc-143">Annotazioni del tipo</span><span class="sxs-lookup"><span data-stu-id="791cc-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="791cc-144">Annotazioni del tipo di argomento della funzione di blocco a destraRight-pad function argument type annotations</span><span class="sxs-lookup"><span data-stu-id="791cc-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="791cc-145">Quando si definiscono argomenti con annotazioni `:` di tipo, utilizzare uno spazio vuoto dopo il simbolo:</span><span class="sxs-lookup"><span data-stu-id="791cc-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="791cc-146">Racchiudere le annotazioni del tipo restituito con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="791cc-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="791cc-147">In un'annotazione di tipo funzione o tipo di valore let-bound (tipo `:` restituito nel caso di una funzione), utilizzare gli spazi vuoti prima e dopo il simbolo:</span><span class="sxs-lookup"><span data-stu-id="791cc-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="791cc-148">Formattazione di righe vuote</span><span class="sxs-lookup"><span data-stu-id="791cc-148">Formatting blank lines</span></span>

* <span data-ttu-id="791cc-149">Separare le definizioni di funzione e classe di primo livello con due righe vuote.</span><span class="sxs-lookup"><span data-stu-id="791cc-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="791cc-150">Le definizioni dei metodi all'interno di una classe sono separate da una singola riga vuota.</span><span class="sxs-lookup"><span data-stu-id="791cc-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="791cc-151">È possibile utilizzare (sparingly) righe vuote per separare gruppi di funzioni correlate.</span><span class="sxs-lookup"><span data-stu-id="791cc-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="791cc-152">Le righe vuote possono essere omesse tra un gruppo di one-liner correlati (ad esempio, un insieme di implementazioni fittizie).</span><span class="sxs-lookup"><span data-stu-id="791cc-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="791cc-153">Utilizzare righe vuote nelle funzioni, con parsimonia, per indicare le sezioni logiche.</span><span class="sxs-lookup"><span data-stu-id="791cc-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="791cc-154">Formattazione dei commenti</span><span class="sxs-lookup"><span data-stu-id="791cc-154">Formatting comments</span></span>

<span data-ttu-id="791cc-155">In genere preferiscono più commenti a doppia barra rispetto ai commenti di blocco in stile ML.</span><span class="sxs-lookup"><span data-stu-id="791cc-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="791cc-156">I commenti in linea devono scrivere in maiuscolo la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="791cc-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="791cc-157">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="791cc-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="791cc-158">Usare camelCase per funzioni e valori associati a classi, espressioni e modelliUse camelCase for class-bound, expression-bound and pattern-bound values and functions</span><span class="sxs-lookup"><span data-stu-id="791cc-158">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="791cc-159">È comune e accettato lo stile di F , utilizzare camelCase per tutti i nomi associati come variabili locali o in corrispondenze di modelli e definizioni di funzione.</span><span class="sxs-lookup"><span data-stu-id="791cc-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="791cc-160">Anche le funzioni associate localmente nelle classi devono usare camelCase.Locally-bound functions in classes should also use camelCase.</span><span class="sxs-lookup"><span data-stu-id="791cc-160">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="791cc-161">Usare camelCase per le funzioni pubbliche associate ai moduliUse camelCase for module-bound public functions</span><span class="sxs-lookup"><span data-stu-id="791cc-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="791cc-162">Quando una funzione associata a un modulo fa parte di un'API pubblica, deve usare camelCase:When a module-bound function is part of a public API, it should use camelCase:</span><span class="sxs-lookup"><span data-stu-id="791cc-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="791cc-163">Usare camelCase per funzioni e valori interni e privati associati a moduliUse camelCase for internal and private module-bound values and functions</span><span class="sxs-lookup"><span data-stu-id="791cc-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="791cc-164">Utilizzare camelCase per i valori associati a moduli privati, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="791cc-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="791cc-165">Funzioni ad hoc negli script</span><span class="sxs-lookup"><span data-stu-id="791cc-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="791cc-166">Valori che costituiscono l'implementazione interna di un modulo o di un tipo</span><span class="sxs-lookup"><span data-stu-id="791cc-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="791cc-167">Utilizzare camelCase per i parametri</span><span class="sxs-lookup"><span data-stu-id="791cc-167">Use camelCase for parameters</span></span>

<span data-ttu-id="791cc-168">Tutti i parametri devono utilizzare camelCase in base alle convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="791cc-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="791cc-169">Utilizzare PascalCase per i moduliUse PascalCase for modules</span><span class="sxs-lookup"><span data-stu-id="791cc-169">Use PascalCase for modules</span></span>

<span data-ttu-id="791cc-170">Tutti i moduli (di livello superiore, interno, privato, annidato) devono utilizzare PascalCase.All modules (top-level, internal, private, nested) should use PascalCase.</span><span class="sxs-lookup"><span data-stu-id="791cc-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="791cc-171">Utilizzare PascalCase per dichiarazioni di tipo, membri ed etichetteUse PascalCase for type declarations, members, and labels</span><span class="sxs-lookup"><span data-stu-id="791cc-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="791cc-172">Classi, interfacce, struct, enumerazioni, delegati, record e unioni discriminate devono essere tutti denominati con PascalCase.Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span><span class="sxs-lookup"><span data-stu-id="791cc-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="791cc-173">Anche i membri all'interno di tipi ed etichette per i record e le unioni discriminate devono utilizzare PascalCase.Members within types and labels for records and discriminated unions should also use PascalCase.</span><span class="sxs-lookup"><span data-stu-id="791cc-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="791cc-174">Utilizzare PascalCase per i costrutti intrinseci a .NETUse PascalCase for constructs intrinsic to .NET</span><span class="sxs-lookup"><span data-stu-id="791cc-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="791cc-175">Anche gli spazi dei nomi,`.dll` le eccezioni, gli eventi e i nomi di progetto devono usare PascalCase.Namespaces, exceptions, events, and project/ names should also use PascalCase.</span><span class="sxs-lookup"><span data-stu-id="791cc-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="791cc-176">Questo non solo rende il consumo da altri linguaggi .NET sentire più naturale per i consumatori, è anche coerente con le convenzioni di denominazione .NET che si rischia di incontrare.</span><span class="sxs-lookup"><span data-stu-id="791cc-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="791cc-177">Evitare i caratteri di sottolineatura nei nomi</span><span class="sxs-lookup"><span data-stu-id="791cc-177">Avoid underscores in names</span></span>

<span data-ttu-id="791cc-178">Storicamente, alcune librerie di F , hanno usato caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="791cc-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="791cc-179">Tuttavia, questo non è più ampiamente accettato, in parte perché si contrae con le convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="791cc-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="791cc-180">Detto questo, alcuni programmatori F , utilizzare sottolineature pesantemente, in parte per motivi storici, e la tolleranza e il rispetto è importante.</span><span class="sxs-lookup"><span data-stu-id="791cc-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="791cc-181">Tuttavia, essere consapevoli del fatto che lo stile è spesso antipatico da altri che hanno una scelta su se usarlo.</span><span class="sxs-lookup"><span data-stu-id="791cc-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="791cc-182">Alcune eccezioni includono l'interoperabilità con i componenti nativi, dove i caratteri di sottolineatura sono molto comuni.</span><span class="sxs-lookup"><span data-stu-id="791cc-182">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="791cc-183">Usare gli operatori standard di F</span><span class="sxs-lookup"><span data-stu-id="791cc-183">Use standard F# operators</span></span>

<span data-ttu-id="791cc-184">Gli operatori seguenti sono definiti nella libreria standard di F e devono essere usati invece di definire equivalenti.</span><span class="sxs-lookup"><span data-stu-id="791cc-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="791cc-185">L'utilizzo di questi operatori è consigliato in quanto tende a rendere il codice più leggibile e idiomatico.</span><span class="sxs-lookup"><span data-stu-id="791cc-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="791cc-186">Gli sviluppatori con un background in OCaml o altro linguaggio di programmazione funzionale possono essere abituati a diversi idiomi.</span><span class="sxs-lookup"><span data-stu-id="791cc-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="791cc-187">Nell'elenco seguente vengono riepilogati gli operatori consigliati di F.</span><span class="sxs-lookup"><span data-stu-id="791cc-187">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="791cc-188">Utilizzare la sintassi`Foo<T>`del prefisso per i`T Foo`generics ( ) nella preferenza per postfix syntax ( )</span><span class="sxs-lookup"><span data-stu-id="791cc-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="791cc-189">Il valore di Fè eredita sia lo stile ML `int list`suffisso di denominazione dei tipi `list<int>`generici ( ad esempio , ) sia lo stile .NET del prefisso (ad esempio, ).</span><span class="sxs-lookup"><span data-stu-id="791cc-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="791cc-190">Preferire lo stile .NET, ad eccezione di cinque tipi specifici:</span><span class="sxs-lookup"><span data-stu-id="791cc-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="791cc-191">Per gli elenchi F, utilizzare `int list` la `list<int>`forma suffissa: anziché .</span><span class="sxs-lookup"><span data-stu-id="791cc-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="791cc-192">Per le opzioni Di F, `int option` utilizzare `option<int>`la forma suffissa: anziché .</span><span class="sxs-lookup"><span data-stu-id="791cc-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="791cc-193">Per le opzioni di valore F `int voption` , `voption<int>`utilizzare la forma suffissa: anziché .</span><span class="sxs-lookup"><span data-stu-id="791cc-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="791cc-194">Per le matrici F, utilizzare `int[]` il `int array` nome `array<int>`sintattico anziché o .</span><span class="sxs-lookup"><span data-stu-id="791cc-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="791cc-195">Per le celle `int ref` di `ref<int>` `Ref<int>`riferimento, utilizzare anziché o .</span><span class="sxs-lookup"><span data-stu-id="791cc-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="791cc-196">Per tutti gli altri tipi, utilizzare la forma del prefisso.</span><span class="sxs-lookup"><span data-stu-id="791cc-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="791cc-197">Formattazione di tuple</span><span class="sxs-lookup"><span data-stu-id="791cc-197">Formatting tuples</span></span>

<span data-ttu-id="791cc-198">La creazione di un'istanza di una tupla deve essere racchiusa tra parentesi e le virgole di delimitazione all'interno devono essere seguite da un singolo spazio, ad esempio: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="791cc-198">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="791cc-199">È comunemente accettato per omettere le parentesi nel criterio di ricerca delle tuple:It is commonly accepted to omit parentheses in pattern matching of tuples:</span><span class="sxs-lookup"><span data-stu-id="791cc-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="791cc-200">È anche comunemente accettato per omettere le parentesi se la tupla è il valore restituito di una funzione:It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span><span class="sxs-lookup"><span data-stu-id="791cc-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="791cc-201">In sintesi, preferire le istanze di tupla tra parentesi, ma quando si usano tuple per criteri di ricerca o un valore restituito, è considerato fine per evitare le parentesi.</span><span class="sxs-lookup"><span data-stu-id="791cc-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="791cc-202">Formattazione delle dichiarazioni di unione discriminate</span><span class="sxs-lookup"><span data-stu-id="791cc-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="791cc-203">Rientro `|` nella definizione del tipo di 4 spazi:</span><span class="sxs-lookup"><span data-stu-id="791cc-203">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="791cc-204">Formattazione delle unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="791cc-204">Formatting discriminated unions</span></span>

<span data-ttu-id="791cc-205">Unioni discriminate istanziate di istanziate che si dividono su più righe devono fornire ai dati contenuti un nuovo ambito con rientro:Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span><span class="sxs-lookup"><span data-stu-id="791cc-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="791cc-206">La parentesi di chiusura può anche essere su una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="791cc-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="791cc-207">Formattazione delle dichiarazioni di record</span><span class="sxs-lookup"><span data-stu-id="791cc-207">Formatting record declarations</span></span>

<span data-ttu-id="791cc-208">Applicare `{` un rientro nella definizione del tipo di 4 spazi e iniziare l'elenco dei campi sulla stessa riga:</span><span class="sxs-lookup"><span data-stu-id="791cc-208">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="791cc-209">Inserire il token di apertura in una nuova riga e il token di chiusura in una nuova riga è preferibile se si dichiarano le implementazioni dell'interfaccia o i membri nel record:</span><span class="sxs-lookup"><span data-stu-id="791cc-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="791cc-210">Formattazione dei record</span><span class="sxs-lookup"><span data-stu-id="791cc-210">Formatting records</span></span>

<span data-ttu-id="791cc-211">I record brevi possono essere scritti in un'unica riga:</span><span class="sxs-lookup"><span data-stu-id="791cc-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="791cc-212">I record più lunghi devono utilizzare nuove righe per le etichette:</span><span class="sxs-lookup"><span data-stu-id="791cc-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="791cc-213">L'inserimento del token di apertura in una nuova riga, il contenuto a schede in un ambito e il token di chiusura su una nuova riga è preferibile se si è:</span><span class="sxs-lookup"><span data-stu-id="791cc-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="791cc-214">Spostamento di record nel codice con ambiti di rientro diversi</span><span class="sxs-lookup"><span data-stu-id="791cc-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="791cc-215">Trasformare in una funzione</span><span class="sxs-lookup"><span data-stu-id="791cc-215">Piping them into a function</span></span>

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

<span data-ttu-id="791cc-216">Le stesse regole si applicano agli elementi di elenco e matrice.</span><span class="sxs-lookup"><span data-stu-id="791cc-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="791cc-217">Formattazione delle espressioni di record di copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="791cc-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="791cc-218">Un'espressione di record di copia e aggiornamento è ancora un record, pertanto si applicano linee guida simili.</span><span class="sxs-lookup"><span data-stu-id="791cc-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="791cc-219">Le espressioni brevi possono essere inserite in un'unica riga:</span><span class="sxs-lookup"><span data-stu-id="791cc-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="791cc-220">Le espressioni più lunghe devono utilizzare nuove righe:Longer expressions should use new lines:</span><span class="sxs-lookup"><span data-stu-id="791cc-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="791cc-221">E come con le linee guida di record, si consiglia di dedicare righe separate per le parentesi graffe e far rientrare un ambito a destra con l'espressione.</span><span class="sxs-lookup"><span data-stu-id="791cc-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="791cc-222">Si noti che in alcuni casi speciali, ad esempio il wrapping di un valore con un optional senza parentesi, potrebbe essere necessario mantenere una parentesi graffa su una riga:Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span><span class="sxs-lookup"><span data-stu-id="791cc-222">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="791cc-223">Formattazione di elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="791cc-223">Formatting lists and arrays</span></span>

<span data-ttu-id="791cc-224">Scrivere `x :: l` con gli `::` spazi`::` intorno all'operatore (è un operatore infisso, quindi circondato da spazi).</span><span class="sxs-lookup"><span data-stu-id="791cc-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="791cc-225">Gli elenchi e le matrici dichiarati su una singola riga devono avere uno spazio dopo la parentesi quadra di apertura e prima della parentesi quadra di chiusura:</span><span class="sxs-lookup"><span data-stu-id="791cc-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="791cc-226">Utilizzare sempre almeno uno spazio tra due operatori simili a parentesi graffe distinti.</span><span class="sxs-lookup"><span data-stu-id="791cc-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="791cc-227">Ad esempio, lasciare uno `[` spazio `{`tra a e un .</span><span class="sxs-lookup"><span data-stu-id="791cc-227">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="791cc-228">La stessa linea guida si applica per elenchi o matrici di tuple.</span><span class="sxs-lookup"><span data-stu-id="791cc-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="791cc-229">Gli elenchi e le matrici suddivisi su più righe seguono una regola simile a quella dei record:</span><span class="sxs-lookup"><span data-stu-id="791cc-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="791cc-230">E come con i record, dichiarando le parentesi di apertura e chiusura sulla propria riga renderà più facile lo spostamento del codice e delle tubazioni nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="791cc-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="791cc-231">Quando si generano matrici ed `->` elenchi `do ... yield` a livello di codice, preferire quando viene sempre generato un valore:When generating arrays and lists programmatically, prefer over when a value is always generated:</span><span class="sxs-lookup"><span data-stu-id="791cc-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="791cc-232">Le versioni precedenti del linguaggio `yield` F , richiedevano la specifica in situazioni in cui i dati possono essere generati in modo condizionale o se possono essere presenti espressioni consecutive da valutare.</span><span class="sxs-lookup"><span data-stu-id="791cc-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="791cc-233">Preferisci omettere queste parole chiave a meno che non sia necessario compilare con una versione del linguaggio F. precedente:Prefer omitting these `yield` keywords unless you must compile with an older F' language version:</span><span class="sxs-lookup"><span data-stu-id="791cc-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="791cc-234">In alcuni `do...yield` casi, può aiutare nella leggibilità.</span><span class="sxs-lookup"><span data-stu-id="791cc-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="791cc-235">Questi casi, anche se soggettivi, dovrebbero essere presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="791cc-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="791cc-236">Formattazione delle espressioni if</span><span class="sxs-lookup"><span data-stu-id="791cc-236">Formatting if expressions</span></span>

<span data-ttu-id="791cc-237">Il rientro delle condizioni dipende dalle dimensioni delle espressioni che le costituiscono.</span><span class="sxs-lookup"><span data-stu-id="791cc-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="791cc-238">Se `cond` `e1` , `e2` e sono brevi, è sufficiente scriverli su una riga:</span><span class="sxs-lookup"><span data-stu-id="791cc-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="791cc-239">Se `cond`uno `e1` `e2` dei due , o sono più lunghi, ma non multi-linea:</span><span class="sxs-lookup"><span data-stu-id="791cc-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="791cc-240">Se una qualsiasi delle espressioni è su più righe:</span><span class="sxs-lookup"><span data-stu-id="791cc-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="791cc-241">Più condizionali con `elif` e `else` sono rientrate `if`nello stesso ambito del :</span><span class="sxs-lookup"><span data-stu-id="791cc-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="791cc-242">Costrutti di criteri di ricercaPattern matching constructs</span><span class="sxs-lookup"><span data-stu-id="791cc-242">Pattern matching constructs</span></span>

<span data-ttu-id="791cc-243">Utilizzare `|` un per ogni clausola di una corrispondenza senza rientro.</span><span class="sxs-lookup"><span data-stu-id="791cc-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="791cc-244">Se l'espressione è breve, è possibile usare una singola riga se anche ogni sottoespressione è semplice.</span><span class="sxs-lookup"><span data-stu-id="791cc-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="791cc-245">Se l'espressione a destra della freccia di corrispondenza dei criteri è troppo grande, `match` / `|`spostarla nella riga seguente, rientrata di un passaggio rispetto alla proprietà .</span><span class="sxs-lookup"><span data-stu-id="791cc-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="791cc-246">I criteri di ricerca `function`delle funzioni anonime, a partire da , in genere non devono rientrare troppo.</span><span class="sxs-lookup"><span data-stu-id="791cc-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="791cc-247">Ad esempio, il rientro di un ambito come segue va bene:For example, indenting one scope as follows and am:</span><span class="sxs-lookup"><span data-stu-id="791cc-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="791cc-248">Criteri di ricerca `let` nelle `let rec` funzioni definite da o devono `let`essere `function` rientrate di 4 spazi dopo l'avvio di , anche se viene utilizzata la parola chiave:</span><span class="sxs-lookup"><span data-stu-id="791cc-248">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="791cc-249">Si sconsiglia di allineare le frecce.</span><span class="sxs-lookup"><span data-stu-id="791cc-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="791cc-250">Formattazione delle espressioni try/with</span><span class="sxs-lookup"><span data-stu-id="791cc-250">Formatting try/with expressions</span></span>

<span data-ttu-id="791cc-251">I criteri di ricerca sul tipo di eccezione `with`devono essere rientrati allo stesso livello di .</span><span class="sxs-lookup"><span data-stu-id="791cc-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="791cc-252">Applicazione dei parametri della funzione di formattazione</span><span class="sxs-lookup"><span data-stu-id="791cc-252">Formatting function parameter application</span></span>

<span data-ttu-id="791cc-253">In generale, la maggior parte dell'applicazione dei parametri di funzione viene eseguita sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="791cc-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="791cc-254">Se si desidera applicare parametri a una funzione in una nuova riga, applicare un rientro di un ambito.</span><span class="sxs-lookup"><span data-stu-id="791cc-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="791cc-255">Le stesse linee guida si applicano per le espressioni lambda come argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="791cc-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="791cc-256">Se il corpo di un'espressione lambda, il corpo può avere un'altra riga, rientrata da un ambito</span><span class="sxs-lookup"><span data-stu-id="791cc-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="791cc-257">Tuttavia, se il corpo di un'espressione lambda è più di una riga, è consigliabile eseguire il factoring in una funzione separata anziché applicare un costrutto su più righe come singolo argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="791cc-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="791cc-258">Formattazione degli operatori infissi</span><span class="sxs-lookup"><span data-stu-id="791cc-258">Formatting infix operators</span></span>

<span data-ttu-id="791cc-259">Separare gli operatori in base agli spazi.</span><span class="sxs-lookup"><span data-stu-id="791cc-259">Separate operators by spaces.</span></span> <span data-ttu-id="791cc-260">Eccezioni ovvie a `!` questa `.` regola sono gli operatori e .</span><span class="sxs-lookup"><span data-stu-id="791cc-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="791cc-261">Le espressioni infisse sono OK per allineare sulla stessa colonna:</span><span class="sxs-lookup"><span data-stu-id="791cc-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="791cc-262">Formattazione degli operatori della pipelineFormatting pipeline operators</span><span class="sxs-lookup"><span data-stu-id="791cc-262">Formatting pipeline operators</span></span>

<span data-ttu-id="791cc-263">Gli `|>` operatori di pipeline devono andare sotto le espressioni su cui operano.</span><span class="sxs-lookup"><span data-stu-id="791cc-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="791cc-264">Formattazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="791cc-264">Formatting modules</span></span>

<span data-ttu-id="791cc-265">Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non deve essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="791cc-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="791cc-266">Gli elementi dello spazio dei nomi non devono essere rientrati.</span><span class="sxs-lookup"><span data-stu-id="791cc-266">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="791cc-267">Formattazione di espressioni e interfacce di oggetti</span><span class="sxs-lookup"><span data-stu-id="791cc-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="791cc-268">Le espressioni oggetto e le interfacce devono `member` essere allineate nello stesso modo con il rientro dopo 4 spazi.</span><span class="sxs-lookup"><span data-stu-id="791cc-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="791cc-269">Formattazione degli spazi vuoti nelle espressioni</span><span class="sxs-lookup"><span data-stu-id="791cc-269">Formatting white space in expressions</span></span>

<span data-ttu-id="791cc-270">Evitare spazi vuoti estranei nelle espressioni F .</span><span class="sxs-lookup"><span data-stu-id="791cc-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="791cc-271">Gli argomenti denominati non `=`devono inoltre avere spazio che circonda il :</span><span class="sxs-lookup"><span data-stu-id="791cc-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="791cc-272">Attributi di formattazione</span><span class="sxs-lookup"><span data-stu-id="791cc-272">Formatting attributes</span></span>

<span data-ttu-id="791cc-273">[Gli attributi](../language-reference/attributes.md) vengono posizionati sopra un costrutto:Attributes are placed above a construct:</span><span class="sxs-lookup"><span data-stu-id="791cc-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="791cc-274">Formattazione degli attributi sui parametri</span><span class="sxs-lookup"><span data-stu-id="791cc-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="791cc-275">Gli attributi possono anche essere posti sui parametri.</span><span class="sxs-lookup"><span data-stu-id="791cc-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="791cc-276">In questo caso, posizionare quindi sulla stessa riga del parametro e prima del nome:</span><span class="sxs-lookup"><span data-stu-id="791cc-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="791cc-277">Formattazione di più attributi</span><span class="sxs-lookup"><span data-stu-id="791cc-277">Formatting multiple attributes</span></span>

<span data-ttu-id="791cc-278">Quando più attributi vengono applicati a un costrutto che non è un parametro, devono essere posizionati in modo che sia presente un attributo per riga:When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span><span class="sxs-lookup"><span data-stu-id="791cc-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="791cc-279">Quando vengono applicati a un parametro, devono trovarsi `;` sulla stessa riga e separati da un separatore.</span><span class="sxs-lookup"><span data-stu-id="791cc-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="791cc-280">Formattazione di valori letterali</span><span class="sxs-lookup"><span data-stu-id="791cc-280">Formatting literals</span></span>

<span data-ttu-id="791cc-281">[I valori letterali F ,](../language-reference/literals.md) usando l'attributo, `Literal` devono inserire l'attributo nella propria riga e usare la denominazione PascalCase:</span><span class="sxs-lookup"><span data-stu-id="791cc-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="791cc-282">Evitare di posizionare l'attributo sulla stessa riga del valore.</span><span class="sxs-lookup"><span data-stu-id="791cc-282">Avoid placing the attribute on the same line as the value.</span></span>
