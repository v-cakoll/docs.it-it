---
title: Linee guida per la formattazione del codice F#
description: 'Informazioni sulle linee guida per la formattazione del codice F #.'
ms.date: 11/04/2019
ms.openlocfilehash: a65600a6c685929aef8582e49caded6340fb09e2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309703"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="efc1b-103">Linee guida per la formattazione del codice F#</span><span class="sxs-lookup"><span data-stu-id="efc1b-103">F# code formatting guidelines</span></span>

<span data-ttu-id="efc1b-104">Questo articolo fornisce linee guida per la formattazione del codice in modo che il codice F # sia:</span><span class="sxs-lookup"><span data-stu-id="efc1b-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="efc1b-105">Più leggibili</span><span class="sxs-lookup"><span data-stu-id="efc1b-105">More legible</span></span>
* <span data-ttu-id="efc1b-106">In conformità alle convenzioni applicate dagli strumenti di formattazione in Visual Studio e altri editor</span><span class="sxs-lookup"><span data-stu-id="efc1b-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="efc1b-107">Simile ad altro codice online</span><span class="sxs-lookup"><span data-stu-id="efc1b-107">Similar to other code online</span></span>

<span data-ttu-id="efc1b-108">Queste linee guida sono basate su [una guida completa alle convenzioni di formattazione F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) di [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="efc1b-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="efc1b-109">Regole generali per il rientro</span><span class="sxs-lookup"><span data-stu-id="efc1b-109">General rules for indentation</span></span>

<span data-ttu-id="efc1b-110">Per impostazione predefinita, F # utilizza spazi vuoti significativi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-110">F# uses significant white space by default.</span></span> <span data-ttu-id="efc1b-111">Le linee guida riportate di seguito hanno lo scopo di fornire indicazioni su come manipolare alcune delle problemi che possono essere imposte.</span><span class="sxs-lookup"><span data-stu-id="efc1b-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="efc1b-112">Uso di spazi</span><span class="sxs-lookup"><span data-stu-id="efc1b-112">Using spaces</span></span>

<span data-ttu-id="efc1b-113">Quando il rientro è obbligatorio, è necessario utilizzare spazi, non tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="efc1b-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="efc1b-114">È necessario almeno uno spazio.</span><span class="sxs-lookup"><span data-stu-id="efc1b-114">At least one space is required.</span></span> <span data-ttu-id="efc1b-115">L'organizzazione può creare standard di codifica per specificare il numero di spazi da utilizzare per il rientro; sono tipiche due, tre o quattro spazi di rientro a ogni livello in cui si verifica il rientro.</span><span class="sxs-lookup"><span data-stu-id="efc1b-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="efc1b-116">**Si consiglia di usare quattro spazi per rientri.**</span><span class="sxs-lookup"><span data-stu-id="efc1b-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="efc1b-117">Detto questo, il rientro dei programmi è una questione soggettiva.</span><span class="sxs-lookup"><span data-stu-id="efc1b-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="efc1b-118">Le variazioni sono OK, ma la prima regola da seguire è la *coerenza dei rientri*.</span><span class="sxs-lookup"><span data-stu-id="efc1b-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="efc1b-119">Scegliere uno stile di rientro generalmente accettato e usarlo sistematicamente nell'intero codebase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="efc1b-120">Formattazione dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="efc1b-120">Formatting white space</span></span>

<span data-ttu-id="efc1b-121">F # è sensibile agli spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="efc1b-121">F# is white space sensitive.</span></span> <span data-ttu-id="efc1b-122">Sebbene la maggior parte della semantica degli spazi vuoti venga analizzata in base al rientro appropriato, è necessario prendere in considerazione altri aspetti.</span><span class="sxs-lookup"><span data-stu-id="efc1b-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="efc1b-123">Formattazione degli operatori nelle espressioni aritmetiche</span><span class="sxs-lookup"><span data-stu-id="efc1b-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="efc1b-124">Usare sempre lo spazio vuoto nelle espressioni aritmetiche binarie:</span><span class="sxs-lookup"><span data-stu-id="efc1b-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="efc1b-125">`-`Gli operatori unari devono essere sempre seguiti immediatamente dal valore che stanno negando:</span><span class="sxs-lookup"><span data-stu-id="efc1b-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="efc1b-126">L'aggiunta di uno spazio vuoto dopo l' `-` operatore può causare confusione per altri utenti.</span><span class="sxs-lookup"><span data-stu-id="efc1b-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="efc1b-127">In breve, è sempre importante:</span><span class="sxs-lookup"><span data-stu-id="efc1b-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="efc1b-128">Racchiudere gli operatori binari con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="efc1b-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="efc1b-129">Non avere mai spazi vuoti finali dopo un operatore unario</span><span class="sxs-lookup"><span data-stu-id="efc1b-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="efc1b-130">La linea guida dell'operatore aritmetico binario è particolarmente importante.</span><span class="sxs-lookup"><span data-stu-id="efc1b-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="efc1b-131">Se non si riesce a racchiudere un `-` operatore binario, in combinazione con determinate scelte di formattazione, può comportare l'interpretazione come unaria `-` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="efc1b-132">Racchiudere una definizione di operatore personalizzato con spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="efc1b-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="efc1b-133">Usare sempre gli spazi vuoti per racchiudere la definizione di un operatore:</span><span class="sxs-lookup"><span data-stu-id="efc1b-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="efc1b-134">Per qualsiasi operatore personalizzato che inizia con `*` e con più di un carattere, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare ambiguità del compilatore.</span><span class="sxs-lookup"><span data-stu-id="efc1b-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="efc1b-135">Per questo motivo, è consigliabile racchiudere semplicemente le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="efc1b-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="efc1b-136">Racchiudere le frecce dei parametri della funzione con spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="efc1b-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="efc1b-137">Quando si definisce la firma di una funzione, usare uno spazio vuoto intorno al `->` simbolo:</span><span class="sxs-lookup"><span data-stu-id="efc1b-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="efc1b-138">Racchiudere gli argomenti della funzione con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="efc1b-138">Surround function arguments with white space</span></span>

<span data-ttu-id="efc1b-139">Quando si definisce una funzione, usare uno spazio vuoto intorno a ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="efc1b-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a><span data-ttu-id="efc1b-140">Inserire i parametri in una nuova riga per le definizioni dei membri lunghi</span><span class="sxs-lookup"><span data-stu-id="efc1b-140">Place parameters on a new line for long member definitions</span></span>

<span data-ttu-id="efc1b-141">Se si dispone di una definizione di membro molto lungo, inserire i parametri su nuove righe e rientrare in base al livello di rientro del parametro successivo.</span><span class="sxs-lookup"><span data-stu-id="efc1b-141">If you have a very long member definition, place the parameters on new lines and indent them to match the indentation level of the subsequent parameter.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="efc1b-142">Questo vale anche per i costruttori:</span><span class="sxs-lookup"><span data-stu-id="efc1b-142">This also applies to constructors:</span></span>

```fsharp
type C(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

<span data-ttu-id="efc1b-143">Se è presente un'annotazione di tipo restituito esplicita, può trovarsi alla fine di `)` e prima di `=` o su una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="efc1b-143">If there is an explicit return type annotation, it can either be at the end of the `)` and before the `=`, or on a new line.</span></span> <span data-ttu-id="efc1b-144">Se anche il tipo restituito ha un nome lungo, quest'ultimo potrebbe essere preferibile:</span><span class="sxs-lookup"><span data-stu-id="efc1b-144">If the return type also has a long name, the latter might be preferable:</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse)
                                            : AVeryLongReturnType =
        // ... the body of the method follows
```

### <a name="type-annotations"></a><span data-ttu-id="efc1b-145">Annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="efc1b-145">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="efc1b-146">Annotazioni del tipo di argomento della funzione Right-Pad</span><span class="sxs-lookup"><span data-stu-id="efc1b-146">Right-pad function argument type annotations</span></span>

<span data-ttu-id="efc1b-147">Quando si definiscono gli argomenti con annotazioni di tipo, usare uno spazio vuoto dopo il `:` simbolo:</span><span class="sxs-lookup"><span data-stu-id="efc1b-147">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="efc1b-148">Annotazioni di tipo restituito Racchiudi con spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="efc1b-148">Surround return type annotations with white space</span></span>

<span data-ttu-id="efc1b-149">In un'annotazione di tipo valore o funzione associata (tipo restituito nel caso di una funzione), usare uno spazio vuoto prima e dopo il `:` simbolo:</span><span class="sxs-lookup"><span data-stu-id="efc1b-149">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="efc1b-150">Formattazione di righe vuote</span><span class="sxs-lookup"><span data-stu-id="efc1b-150">Formatting blank lines</span></span>

* <span data-ttu-id="efc1b-151">Separare le definizioni di classi e funzioni di primo livello con due righe vuote.</span><span class="sxs-lookup"><span data-stu-id="efc1b-151">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="efc1b-152">Le definizioni di metodo all'interno di una classe sono separate da un'unica riga vuota.</span><span class="sxs-lookup"><span data-stu-id="efc1b-152">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="efc1b-153">Per separare i gruppi di funzioni correlate, è possibile utilizzare le righe vuote aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="efc1b-153">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="efc1b-154">Le righe vuote possono essere omesse tra un gruppo di un set di righe correlato, ad esempio un set di implementazioni fittizie.</span><span class="sxs-lookup"><span data-stu-id="efc1b-154">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="efc1b-155">Utilizzare righe vuote nelle funzioni, per indicare le sezioni logiche.</span><span class="sxs-lookup"><span data-stu-id="efc1b-155">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="efc1b-156">Formattazione di commenti</span><span class="sxs-lookup"><span data-stu-id="efc1b-156">Formatting comments</span></span>

<span data-ttu-id="efc1b-157">Preferiscono in genere più commenti a doppia barra rispetto ai commenti di blocco di tipo ML.</span><span class="sxs-lookup"><span data-stu-id="efc1b-157">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="efc1b-158">I commenti inline devono sfruttare la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="efc1b-158">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="efc1b-159">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="efc1b-159">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="efc1b-160">Usare camelCase per le funzioni e i valori associati a classi, associati a espressioni e modelli</span><span class="sxs-lookup"><span data-stu-id="efc1b-160">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="efc1b-161">Lo stile F # è comune e accettato per usare camelCase per tutti i nomi associati come variabili locali o in corrispondenze di modelli e definizioni di funzione.</span><span class="sxs-lookup"><span data-stu-id="efc1b-161">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="efc1b-162">Anche le funzioni con binding localmente nelle classi devono usare camelCase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-162">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="efc1b-163">Usare camelCase per le funzioni pubbliche con associazione al modulo</span><span class="sxs-lookup"><span data-stu-id="efc1b-163">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="efc1b-164">Quando una funzione associata a un modulo fa parte di un'API pubblica, deve usare camelCase:</span><span class="sxs-lookup"><span data-stu-id="efc1b-164">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="efc1b-165">Usare camelCase per le funzioni e i valori associati a moduli interni e privati</span><span class="sxs-lookup"><span data-stu-id="efc1b-165">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="efc1b-166">Usare camelCase per i valori associati al modulo privato, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="efc1b-166">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="efc1b-167">Funzioni ad hoc negli script</span><span class="sxs-lookup"><span data-stu-id="efc1b-167">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="efc1b-168">Valori che costituiscono l'implementazione interna di un modulo o di un tipo</span><span class="sxs-lookup"><span data-stu-id="efc1b-168">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="efc1b-169">Usare camelCase per i parametri</span><span class="sxs-lookup"><span data-stu-id="efc1b-169">Use camelCase for parameters</span></span>

<span data-ttu-id="efc1b-170">Tutti i parametri devono usare camelCase in conformità alle convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="efc1b-170">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="efc1b-171">Usare PascalCase per i moduli</span><span class="sxs-lookup"><span data-stu-id="efc1b-171">Use PascalCase for modules</span></span>

<span data-ttu-id="efc1b-172">Tutti i moduli (di livello superiore, interno, privato, nidificato) devono usare PascalCase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-172">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="efc1b-173">Usare PascalCase per dichiarazioni di tipo, membri ed etichette</span><span class="sxs-lookup"><span data-stu-id="efc1b-173">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="efc1b-174">Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-174">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="efc1b-175">Anche i membri all'interno dei tipi e delle etichette per i record e le unioni discriminate devono usare PascalCase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-175">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="efc1b-176">Usare PascalCase per costrutti intrinseci a .NET</span><span class="sxs-lookup"><span data-stu-id="efc1b-176">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="efc1b-177">Gli spazi dei nomi, le eccezioni, gli eventi e `.dll` i nomi e i progetti devono anche usare PascalCase.</span><span class="sxs-lookup"><span data-stu-id="efc1b-177">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="efc1b-178">In questo modo, l'utilizzo da parte di altri linguaggi .NET risulta più naturale per gli utenti, ma è anche coerente con le convenzioni di denominazione .NET che è probabile che si verifichino.</span><span class="sxs-lookup"><span data-stu-id="efc1b-178">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="efc1b-179">Evitare i caratteri di sottolineatura nei nomi</span><span class="sxs-lookup"><span data-stu-id="efc1b-179">Avoid underscores in names</span></span>

<span data-ttu-id="efc1b-180">In passato, alcune librerie F # hanno usato caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-180">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="efc1b-181">Tuttavia, questo non è più ampiamente accettato, in parte perché si scontra con le convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="efc1b-181">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="efc1b-182">Detto questo, alcuni programmatori F # utilizzano molto spesso i caratteri di sottolineatura, in parte per motivi cronologici, e la tolleranza e il rispetto sono importanti.</span><span class="sxs-lookup"><span data-stu-id="efc1b-182">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="efc1b-183">Tuttavia, tenere presente che lo stile è spesso diverso da altri utenti che hanno la possibilità di scegliere se utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="efc1b-183">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="efc1b-184">Un'eccezione include l'interoperabilità con i componenti nativi, dove i caratteri di sottolineatura sono comuni.</span><span class="sxs-lookup"><span data-stu-id="efc1b-184">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="efc1b-185">Usare gli operatori F # standard</span><span class="sxs-lookup"><span data-stu-id="efc1b-185">Use standard F# operators</span></span>

<span data-ttu-id="efc1b-186">Gli operatori seguenti sono definiti nella libreria standard F # e devono essere usati anziché definire equivalenti.</span><span class="sxs-lookup"><span data-stu-id="efc1b-186">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="efc1b-187">L'uso di questi operatori è consigliato perché tende a rendere il codice più leggibile e idiomatiche.</span><span class="sxs-lookup"><span data-stu-id="efc1b-187">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="efc1b-188">Gli sviluppatori con background in OCaml o altro linguaggio di programmazione funzionale possono essere abituati a idiomi diversi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-188">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="efc1b-189">Nell'elenco seguente sono riepilogati gli operatori F # consigliati.</span><span class="sxs-lookup"><span data-stu-id="efc1b-189">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="efc1b-190">Usare la sintassi di prefisso per generics ( `Foo<T>` ) in preferenza alla sintassi suffissa ( `T Foo` )</span><span class="sxs-lookup"><span data-stu-id="efc1b-190">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="efc1b-191">F # eredita sia lo stile di suffisso ML dei tipi generici di denominazione (ad esempio, `int list` ) sia lo stile .NET del prefisso (ad esempio, `list<int>` ).</span><span class="sxs-lookup"><span data-stu-id="efc1b-191">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="efc1b-192">Preferisce lo stile .NET, ad eccezione di cinque tipi specifici:</span><span class="sxs-lookup"><span data-stu-id="efc1b-192">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="efc1b-193">Per gli elenchi F # usare il formato suffisso: `int list` anziché `list<int>` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-193">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="efc1b-194">Per le opzioni F # usare il formato suffisso: `int option` anziché `option<int>` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-194">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="efc1b-195">Per le opzioni di valore F # usare il formato suffisso: `int voption` anziché `voption<int>` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-195">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="efc1b-196">Per le matrici F # usare il nome sintattico `int[]` anziché `int array` o `array<int>` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-196">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="efc1b-197">Per le celle di riferimento, usare `int ref` anziché `ref<int>` o `Ref<int>` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-197">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="efc1b-198">Per tutti gli altri tipi, usare il formato prefisso.</span><span class="sxs-lookup"><span data-stu-id="efc1b-198">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="efc1b-199">Formattazione di Tuple</span><span class="sxs-lookup"><span data-stu-id="efc1b-199">Formatting tuples</span></span>

<span data-ttu-id="efc1b-200">La creazione di un'istanza di tupla deve essere racchiusa tra parentesi e le virgole di delimitazione al suo interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)` , `(x, y, z)` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-200">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="efc1b-201">Viene in genere accettato per omettere le parentesi nei criteri di ricerca delle tuple:</span><span class="sxs-lookup"><span data-stu-id="efc1b-201">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="efc1b-202">Viene inoltre comunemente accettato di omettere le parentesi se la tupla è il valore restituito di una funzione:</span><span class="sxs-lookup"><span data-stu-id="efc1b-202">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="efc1b-203">In sintesi, predilige le creazioni di istanze di Tuple tra parentesi, ma quando si usano Tuple per la corrispondenza dei modelli o un valore restituito, è opportuno evitare le parentesi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-203">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="efc1b-204">Formattazione di dichiarazioni di Unione discriminate</span><span class="sxs-lookup"><span data-stu-id="efc1b-204">Formatting discriminated union declarations</span></span>

<span data-ttu-id="efc1b-205">Rientro di `|` quattro spazi nella definizione del tipo:</span><span class="sxs-lookup"><span data-stu-id="efc1b-205">Indent `|` in type definition by four spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="efc1b-206">Formattazione di unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="efc1b-206">Formatting discriminated unions</span></span>

<span data-ttu-id="efc1b-207">Le unioni discriminate di cui è stata creata la suddivisione in più righe devono fornire ai dati contenuti un nuovo ambito con rientro:</span><span class="sxs-lookup"><span data-stu-id="efc1b-207">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="efc1b-208">La parentesi di chiusura può inoltre trovarsi in una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-208">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="efc1b-209">Formattazione di dichiarazioni di record</span><span class="sxs-lookup"><span data-stu-id="efc1b-209">Formatting record declarations</span></span>

<span data-ttu-id="efc1b-210">Rientrare `{` nella definizione del tipo di quattro spazi e avviare l'elenco dei campi sulla stessa riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-210">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="efc1b-211">L'inserimento del token di apertura su una nuova riga e il token di chiusura in una nuova riga è preferibile se si dichiarano implementazioni o membri dell'interfaccia nel record:</span><span class="sxs-lookup"><span data-stu-id="efc1b-211">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

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

## <a name="formatting-records"></a><span data-ttu-id="efc1b-212">Formattazione di record</span><span class="sxs-lookup"><span data-stu-id="efc1b-212">Formatting records</span></span>

<span data-ttu-id="efc1b-213">È possibile scrivere record brevi in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-213">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="efc1b-214">I record che hanno più tempo devono usare le nuove righe per le etichette:</span><span class="sxs-lookup"><span data-stu-id="efc1b-214">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="efc1b-215">Inserire il token di apertura su una nuova riga, il contenuto a schede su un ambito e il token di chiusura in una nuova riga è preferibile se si è:</span><span class="sxs-lookup"><span data-stu-id="efc1b-215">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="efc1b-216">Trasferimento di record nel codice con ambiti di rientro diversi</span><span class="sxs-lookup"><span data-stu-id="efc1b-216">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="efc1b-217">Inviarli tramite pipe a una funzione</span><span class="sxs-lookup"><span data-stu-id="efc1b-217">Piping them into a function</span></span>

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

<span data-ttu-id="efc1b-218">Le stesse regole si applicano agli elementi list e Array.</span><span class="sxs-lookup"><span data-stu-id="efc1b-218">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="efc1b-219">Formattazione di espressioni di record di copia e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="efc1b-219">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="efc1b-220">Un'espressione di record di copia e aggiornamento è ancora un record, quindi si applicano linee guida simili.</span><span class="sxs-lookup"><span data-stu-id="efc1b-220">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="efc1b-221">Le espressioni brevi possono rientrare in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-221">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="efc1b-222">Le espressioni più lunghe devono usare le nuove righe:</span><span class="sxs-lookup"><span data-stu-id="efc1b-222">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

<span data-ttu-id="efc1b-223">Come per le linee guida per i record, è possibile dedicare linee separate per le parentesi graffe e rientrare un ambito a destra con l'espressione.</span><span class="sxs-lookup"><span data-stu-id="efc1b-223">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="efc1b-224">In alcuni casi speciali, ad esempio il wrapping di un valore con un facoltativo senza parentesi, potrebbe essere necessario utilizzare una parentesi graffa in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-224">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="efc1b-225">Formattazione di elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="efc1b-225">Formatting lists and arrays</span></span>

<span data-ttu-id="efc1b-226">Scrivere `x :: l` con spazi intorno all' `::` operatore ( `::` è un operatore infisso, quindi racchiuso tra gli spazi).</span><span class="sxs-lookup"><span data-stu-id="efc1b-226">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="efc1b-227">Gli elenchi e le matrici dichiarati in una singola riga devono avere uno spazio dopo la parentesi di apertura e prima della parentesi quadra di chiusura:</span><span class="sxs-lookup"><span data-stu-id="efc1b-227">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="efc1b-228">Usare sempre almeno uno spazio tra due operatori distinti di tipo parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="efc1b-228">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="efc1b-229">Ad esempio, lasciare uno spazio tra `[` e `{` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-229">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="efc1b-230">Si applicano le stesse linee guida per elenchi o matrici di Tuple.</span><span class="sxs-lookup"><span data-stu-id="efc1b-230">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="efc1b-231">Gli elenchi e le matrici suddivisi in più righe seguono una regola simile a quella di record:</span><span class="sxs-lookup"><span data-stu-id="efc1b-231">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="efc1b-232">E come per i record, dichiarando le parentesi quadre di apertura e chiusura sulla propria riga, si renderà più semplice lo spostamento del codice e il piping delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="efc1b-232">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="efc1b-233">Quando si generano matrici ed elenchi a livello di codice, è preferibile `->` `do ... yield` quando viene generato sempre un valore:</span><span class="sxs-lookup"><span data-stu-id="efc1b-233">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

<span data-ttu-id="efc1b-234">Nelle versioni precedenti del linguaggio F # è necessario specificare `yield` nelle situazioni in cui i dati possono essere generati in modo condizionale oppure è possibile che vengano valutate espressioni consecutive.</span><span class="sxs-lookup"><span data-stu-id="efc1b-234">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="efc1b-235">È preferibile omettere queste `yield` parole chiave a meno che non sia necessario compilare con una versione precedente del linguaggio F #:</span><span class="sxs-lookup"><span data-stu-id="efc1b-235">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="efc1b-236">In alcuni casi, `do...yield` può aiutare a migliorare la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="efc1b-236">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="efc1b-237">Questi casi, anche se soggettivi, devono essere presi in considerazione.</span><span class="sxs-lookup"><span data-stu-id="efc1b-237">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="efc1b-238">Formattazione di espressioni if</span><span class="sxs-lookup"><span data-stu-id="efc1b-238">Formatting if expressions</span></span>

<span data-ttu-id="efc1b-239">Il rientro delle condizioni dipende dalle dimensioni delle espressioni che li costituiscono.</span><span class="sxs-lookup"><span data-stu-id="efc1b-239">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="efc1b-240">Se `cond` `e1` e `e2` sono brevi, è sufficiente scriverli in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-240">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="efc1b-241">Se `cond` `e1` o `e2` sono più lunghi, ma non a più righe:</span><span class="sxs-lookup"><span data-stu-id="efc1b-241">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="efc1b-242">Se una delle espressioni è a più righe:</span><span class="sxs-lookup"><span data-stu-id="efc1b-242">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="efc1b-243">Più condizionali con `elif` e `else` vengono rientrati nello stesso ambito di `if` :</span><span class="sxs-lookup"><span data-stu-id="efc1b-243">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="efc1b-244">Costrutti di criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="efc1b-244">Pattern matching constructs</span></span>

<span data-ttu-id="efc1b-245">Utilizzare un oggetto `|` per ogni clausola di una corrispondenza senza rientro.</span><span class="sxs-lookup"><span data-stu-id="efc1b-245">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="efc1b-246">Se l'espressione è breve, è possibile prendere in considerazione l'uso di una singola riga se anche ogni sottoespressione è semplice.</span><span class="sxs-lookup"><span data-stu-id="efc1b-246">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="efc1b-247">Se l'espressione a destra della freccia che corrisponde al criterio di ricerca è troppo grande, spostarla nella riga seguente, rientrata di un passaggio da `match` / `|` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-247">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="efc1b-248">I criteri di ricerca delle funzioni anonime, a partire da `function` , non dovrebbero in genere rientrare troppo a lungo.</span><span class="sxs-lookup"><span data-stu-id="efc1b-248">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="efc1b-249">È ad esempio possibile rientrare in un ambito come segue:</span><span class="sxs-lookup"><span data-stu-id="efc1b-249">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="efc1b-250">I criteri di ricerca nelle funzioni definite da `let` o `let rec` devono essere rientrati in quattro spazi dopo l'avvio di `let` , anche se `function` viene usata la parola chiave:</span><span class="sxs-lookup"><span data-stu-id="efc1b-250">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="efc1b-251">Non è consigliabile allineare le frecce.</span><span class="sxs-lookup"><span data-stu-id="efc1b-251">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="efc1b-252">Formattazione di espressioni try/with</span><span class="sxs-lookup"><span data-stu-id="efc1b-252">Formatting try/with expressions</span></span>

<span data-ttu-id="efc1b-253">I criteri di ricerca nel tipo di eccezione devono essere rientrati allo stesso livello di `with` .</span><span class="sxs-lookup"><span data-stu-id="efc1b-253">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="efc1b-254">Formattazione applicazione parametri funzione</span><span class="sxs-lookup"><span data-stu-id="efc1b-254">Formatting function parameter application</span></span>

<span data-ttu-id="efc1b-255">In generale, la maggior parte delle applicazioni per i parametri di funzione viene eseguita sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="efc1b-255">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="efc1b-256">Se si desidera applicare parametri a una funzione su una nuova riga, rientrare in un solo ambito.</span><span class="sxs-lookup"><span data-stu-id="efc1b-256">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="efc1b-257">Le stesse linee guida si applicano alle espressioni lambda come argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="efc1b-257">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="efc1b-258">Se il corpo di un'espressione lambda, il corpo può avere un'altra riga, rientrato da un ambito</span><span class="sxs-lookup"><span data-stu-id="efc1b-258">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="efc1b-259">Tuttavia, se il corpo di un'espressione lambda è più di una riga, provare a fattorizzarlo in una funzione separata anziché avere un costrutto a più righe applicato come singolo argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="efc1b-259">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="efc1b-260">Formattazione di operatori infissi</span><span class="sxs-lookup"><span data-stu-id="efc1b-260">Formatting infix operators</span></span>

<span data-ttu-id="efc1b-261">Separare gli operatori per spazi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-261">Separate operators by spaces.</span></span> <span data-ttu-id="efc1b-262">Le eccezioni ovvie a questa regola sono gli `!` `.` operatori e.</span><span class="sxs-lookup"><span data-stu-id="efc1b-262">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="efc1b-263">Le espressioni infissi sono OK per la scaletta nella stessa colonna:</span><span class="sxs-lookup"><span data-stu-id="efc1b-263">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="efc1b-264">Formattazione degli operatori pipeline</span><span class="sxs-lookup"><span data-stu-id="efc1b-264">Formatting pipeline operators</span></span>

<span data-ttu-id="efc1b-265">`|>`Gli operatori pipeline dovrebbero andare sotto le espressioni su cui operano.</span><span class="sxs-lookup"><span data-stu-id="efc1b-265">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="efc1b-266">Formattazione di moduli</span><span class="sxs-lookup"><span data-stu-id="efc1b-266">Formatting modules</span></span>

<span data-ttu-id="efc1b-267">Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di livello principale non deve essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="efc1b-267">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="efc1b-268">Non è necessario rientrare gli elementi dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-268">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="efc1b-269">Formattazione di espressioni di oggetti e interfacce</span><span class="sxs-lookup"><span data-stu-id="efc1b-269">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="efc1b-270">Le interfacce e le espressioni di oggetto devono essere allineate nello stesso modo in cui `member` vengono rientrate dopo quattro spazi.</span><span class="sxs-lookup"><span data-stu-id="efc1b-270">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="efc1b-271">Formattazione di spazi vuoti nelle espressioni</span><span class="sxs-lookup"><span data-stu-id="efc1b-271">Formatting white space in expressions</span></span>

<span data-ttu-id="efc1b-272">Evitare spazi vuoti estranei nelle espressioni F #.</span><span class="sxs-lookup"><span data-stu-id="efc1b-272">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="efc1b-273">Gli argomenti denominati non devono inoltre contenere spazio per l'oggetto `=` :</span><span class="sxs-lookup"><span data-stu-id="efc1b-273">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="efc1b-274">Attributi di formattazione</span><span class="sxs-lookup"><span data-stu-id="efc1b-274">Formatting attributes</span></span>

<span data-ttu-id="efc1b-275">[Gli attributi](../language-reference/attributes.md) vengono posizionati sopra un costrutto:</span><span class="sxs-lookup"><span data-stu-id="efc1b-275">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="efc1b-276">Formattazione degli attributi nei parametri</span><span class="sxs-lookup"><span data-stu-id="efc1b-276">Formatting attributes on parameters</span></span>

<span data-ttu-id="efc1b-277">Gli attributi possono essere inseriti anche nei parametri.</span><span class="sxs-lookup"><span data-stu-id="efc1b-277">Attributes can also be placed on parameters.</span></span> <span data-ttu-id="efc1b-278">In questo caso, posizionare quindi nella stessa riga del parametro e prima del nome:</span><span class="sxs-lookup"><span data-stu-id="efc1b-278">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="efc1b-279">Formattazione di più attributi</span><span class="sxs-lookup"><span data-stu-id="efc1b-279">Formatting multiple attributes</span></span>

<span data-ttu-id="efc1b-280">Quando si applicano più attributi a un costrutto che non è un parametro, questi devono essere posizionati in modo che esista un attributo per riga:</span><span class="sxs-lookup"><span data-stu-id="efc1b-280">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="efc1b-281">Quando vengono applicati a un parametro, devono trovarsi sulla stessa riga e separati da un `;` separatore.</span><span class="sxs-lookup"><span data-stu-id="efc1b-281">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="efc1b-282">Formattazione di valori letterali</span><span class="sxs-lookup"><span data-stu-id="efc1b-282">Formatting literals</span></span>

<span data-ttu-id="efc1b-283">I [valori letterali F #](../language-reference/literals.md) che usano l' `Literal` attributo devono inserire l'attributo sulla propria riga e usare la denominazione PascalCase:</span><span class="sxs-lookup"><span data-stu-id="efc1b-283">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="efc1b-284">Evitare di posizionare l'attributo sulla stessa riga del valore.</span><span class="sxs-lookup"><span data-stu-id="efc1b-284">Avoid placing the attribute on the same line as the value.</span></span>
