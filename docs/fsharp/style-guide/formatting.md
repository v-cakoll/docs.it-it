---
title: F#linee guida per la formattazione del codice
description: Per ulteriori linee guida per la formattazione, vedere F# codice.
ms.date: 02/08/2019
ms.openlocfilehash: ce07bd800984ec082a522bc62cb487f786fa0510
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063594"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="35b77-103">F#linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="35b77-103">F# code formatting guidelines</span></span>

<span data-ttu-id="35b77-104">Questo articolo offre linee guida per la modalità di formattazione del codice in modo che il F# codice è:</span><span class="sxs-lookup"><span data-stu-id="35b77-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="35b77-105">In genere visualizzati come più leggibili</span><span class="sxs-lookup"><span data-stu-id="35b77-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="35b77-106">È in base alle convenzioni applicate formattando altri editor e strumenti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35b77-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="35b77-107">Simile ad altro codice online</span><span class="sxs-lookup"><span data-stu-id="35b77-107">Similar to other code online</span></span>

<span data-ttu-id="35b77-108">Queste indicazioni si basano [una guida completa alla F# convenzioni di formattazione](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) dal [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="35b77-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="35b77-109">Regole generali per il rientro</span><span class="sxs-lookup"><span data-stu-id="35b77-109">General rules for indentation</span></span>

<span data-ttu-id="35b77-110">F#Per impostazione predefinita, utilizza gli spazi vuoti significativi.</span><span class="sxs-lookup"><span data-stu-id="35b77-110">F# uses significant white space by default.</span></span> <span data-ttu-id="35b77-111">Le linee guida seguenti sono utili per fornire istruzioni su come organizzare alcune problematiche di che ciò può essere imposti.</span><span class="sxs-lookup"><span data-stu-id="35b77-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="35b77-112">Uso di spazi</span><span class="sxs-lookup"><span data-stu-id="35b77-112">Using spaces</span></span>

<span data-ttu-id="35b77-113">Quando il rientro è necessario, è necessario utilizzare spazi, tabulazioni non.</span><span class="sxs-lookup"><span data-stu-id="35b77-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="35b77-114">È necessario almeno uno spazio.</span><span class="sxs-lookup"><span data-stu-id="35b77-114">At least one space is required.</span></span> <span data-ttu-id="35b77-115">L'organizzazione può creare gli standard di codifica per specificare il numero di spazi da utilizzare per il rientro. due, tre o quattro spazi del rientro a ogni livello in cui si verifica il rientro è tipico.</span><span class="sxs-lookup"><span data-stu-id="35b77-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="35b77-116">**Si consiglia di 4 spazi per il rientro.**</span><span class="sxs-lookup"><span data-stu-id="35b77-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="35b77-117">Ciò premesso, rientro dei programmi è una questione soggettiva.</span><span class="sxs-lookup"><span data-stu-id="35b77-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="35b77-118">Le variazioni sono OK, ma è la prima regola è necessario seguire *coerenza di rientro*.</span><span class="sxs-lookup"><span data-stu-id="35b77-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="35b77-119">Scegliere uno stile di rientro in genere accettato e usarlo in modo sistematico in tutta la codebase.</span><span class="sxs-lookup"><span data-stu-id="35b77-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="35b77-120">Formattazione di spazi vuoti</span><span class="sxs-lookup"><span data-stu-id="35b77-120">Formatting white space</span></span>

<span data-ttu-id="35b77-121">F#è sensibile gli spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="35b77-121">F# is white space sensitive.</span></span> <span data-ttu-id="35b77-122">Sebbene la maggior parte delle semantica da spazi vuoti viene analizzata rientro corretto, esistono alcuni altri aspetti da considerare.</span><span class="sxs-lookup"><span data-stu-id="35b77-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="35b77-123">Formattazione di operatori nelle espressioni aritmetiche</span><span class="sxs-lookup"><span data-stu-id="35b77-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="35b77-124">Usare sempre uno spazio bianco intorno binarie espressioni aritmetiche:</span><span class="sxs-lookup"><span data-stu-id="35b77-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="35b77-125">Unario `-` gli operatori devono avere sempre il valore che vengono ricompilati impedendo seguono immediatamente:</span><span class="sxs-lookup"><span data-stu-id="35b77-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="35b77-126">Aggiunta di un carattere di spazio vuoto dopo la `-` operatore può generare confusione per gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="35b77-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="35b77-127">In breve, è importante sempre:</span><span class="sxs-lookup"><span data-stu-id="35b77-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="35b77-128">Operatori binari snippet di inclusione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="35b77-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="35b77-129">Assenza di spazio vuoto finale dopo un operatore unario</span><span class="sxs-lookup"><span data-stu-id="35b77-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="35b77-130">La linea guida per l'operatore aritmetico binaria è particolarmente importante.</span><span class="sxs-lookup"><span data-stu-id="35b77-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="35b77-131">Esito negativo racchiudere un file binario `-` operatore, in combinazione con determinate opzioni di formattazione, potrebbe causare per interpretarlo come unario `-`.</span><span class="sxs-lookup"><span data-stu-id="35b77-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="35b77-132">Racchiudere una definizione di operatore personalizzato con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="35b77-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="35b77-133">Usare sempre gli spazi vuoti per racchiudere una definizione di operatore:</span><span class="sxs-lookup"><span data-stu-id="35b77-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="35b77-134">Per qualsiasi operatore personalizzato che inizia con `*` e che dispone di più di un carattere, è necessario aggiungere uno spazio vuoto all'inizio della definizione per evitare ambiguità un compilatore.</span><span class="sxs-lookup"><span data-stu-id="35b77-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="35b77-135">Per questo motivo, è consigliabile che è sufficiente racchiudere le definizioni di tutti gli operatori con un singolo carattere di spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="35b77-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="35b77-136">Racchiudere le frecce di parametro di funzione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="35b77-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="35b77-137">Quando si definisce la firma di una funzione, usare uno spazio bianco intorno di `->` simbolo:</span><span class="sxs-lookup"><span data-stu-id="35b77-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="35b77-138">Argomenti della funzione snippet di inclusione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="35b77-138">Surround function arguments with white space</span></span>

<span data-ttu-id="35b77-139">Quando si definisce una funzione, usare uno spazio bianco intorno a ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="35b77-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="type-annotations"></a><span data-ttu-id="35b77-140">Annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="35b77-140">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="35b77-141">Annotazioni del tipo di argomento di funzione di riempimento a destra</span><span class="sxs-lookup"><span data-stu-id="35b77-141">Right-pad function argument type annotations</span></span>

<span data-ttu-id="35b77-142">Quando si definiscono gli argomenti con annotazioni del tipo, usare lo spazio vuoto dopo la `:` simbolo:</span><span class="sxs-lookup"><span data-stu-id="35b77-142">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="35b77-143">Annotazioni di tipo restituito di snippet di inclusione con uno spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="35b77-143">Surround return type annotations with white space</span></span>

<span data-ttu-id="35b77-144">In un'associazione let funzione o un valore di annotazione di tipo (tipo restituito in caso di una funzione), usare gli spazi vuoti prima e dopo il `:` simbolo:</span><span class="sxs-lookup"><span data-stu-id="35b77-144">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="35b77-145">Formattazione di righe vuote</span><span class="sxs-lookup"><span data-stu-id="35b77-145">Formatting blank lines</span></span>

* <span data-ttu-id="35b77-146">Separati (funzione) e classe definizioni di primo livello con due righe vuote.</span><span class="sxs-lookup"><span data-stu-id="35b77-146">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="35b77-147">Le definizioni di metodo all'interno di una classe sono separate da una singola riga vuota.</span><span class="sxs-lookup"><span data-stu-id="35b77-147">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="35b77-148">Righe vuote aggiuntive possono essere usate (solo se necessario) per separare gruppi di funzioni correlate.</span><span class="sxs-lookup"><span data-stu-id="35b77-148">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="35b77-149">È possibile omettere le righe vuote tra una serie di istruzioni a riga singola correlati (ad esempio, un set di implementazioni fittizie).</span><span class="sxs-lookup"><span data-stu-id="35b77-149">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="35b77-150">Usare le righe vuote in funzioni, solo se necessario, per indicare sezioni logiche.</span><span class="sxs-lookup"><span data-stu-id="35b77-150">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="35b77-151">Formattazione di commenti</span><span class="sxs-lookup"><span data-stu-id="35b77-151">Formatting comments</span></span>

<span data-ttu-id="35b77-152">In genere preferire più commenti con barra doppia commenti del blocco di stile di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="35b77-152">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="35b77-153">Commenti inline devono convertire in maiuscolo la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="35b77-153">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="35b77-154">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="35b77-154">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="35b77-155">Usano la notazione camel per le funzioni e i valori associati a classe, espressione di associazione e con associazione a modello</span><span class="sxs-lookup"><span data-stu-id="35b77-155">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="35b77-156">È comune e accettati F# usano la notazione camel per tutti i nomi associati come variabili locali o nei criteri di corrispondenza e definizioni di funzioni di stile.</span><span class="sxs-lookup"><span data-stu-id="35b77-156">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="35b77-157">In locale con associazione a funzioni nelle classi devono inoltre usano la notazione camel.</span><span class="sxs-lookup"><span data-stu-id="35b77-157">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="35b77-158">Usano la notazione camel per le funzioni pubbliche associata al modulo</span><span class="sxs-lookup"><span data-stu-id="35b77-158">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="35b77-159">Quando una funzione associata al modulo fa parte di un'API pubblica, è necessario utilizzare camelCase:</span><span class="sxs-lookup"><span data-stu-id="35b77-159">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="35b77-160">Usano la notazione camel per le funzioni e i valori associati a modulo interni e privati</span><span class="sxs-lookup"><span data-stu-id="35b77-160">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="35b77-161">Usano la notazione camel per i valori privati associata al modulo, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="35b77-161">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="35b77-162">Funzioni ad hoc negli script</span><span class="sxs-lookup"><span data-stu-id="35b77-162">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="35b77-163">Valori che compongono l'implementazione interna di un tipo o un modulo</span><span class="sxs-lookup"><span data-stu-id="35b77-163">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="35b77-164">Usano la notazione camel per i parametri</span><span class="sxs-lookup"><span data-stu-id="35b77-164">Use camelCase for parameters</span></span>

<span data-ttu-id="35b77-165">Tutti i parametri devono usano la notazione camel in base alle convenzioni di denominazione .NET.</span><span class="sxs-lookup"><span data-stu-id="35b77-165">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="35b77-166">Per i moduli usano la notazione Pascal</span><span class="sxs-lookup"><span data-stu-id="35b77-166">Use PascalCase for modules</span></span>

<span data-ttu-id="35b77-167">Tutti i moduli (livello superiore, interni, privati, annidati) utilizzino PascalCase.</span><span class="sxs-lookup"><span data-stu-id="35b77-167">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="35b77-168">Usano la notazione Pascal per le dichiarazioni di tipi, membri e le etichette</span><span class="sxs-lookup"><span data-stu-id="35b77-168">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="35b77-169">Classi, interfacce, strutture, enumerazioni, delegati, record e unioni discriminate devono essere denominate con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="35b77-169">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="35b77-170">I membri all'interno di tipi e le etichette per i record e unioni discriminate devono inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="35b77-170">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="35b77-171">Usano la notazione Pascal per i costrutti intrinseci per .NET</span><span class="sxs-lookup"><span data-stu-id="35b77-171">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="35b77-172">Spazi dei nomi, le eccezioni, eventi e progetto /`.dll` nomi dovrebbero inoltre usano la notazione Pascal.</span><span class="sxs-lookup"><span data-stu-id="35b77-172">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="35b77-173">Non solo si rende il consumo da altri linguaggi .NET sembrano più naturali agli utenti, è anche coerenza con le convenzioni di denominazione .NET che probabile incontrare.</span><span class="sxs-lookup"><span data-stu-id="35b77-173">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="35b77-174">Evitare caratteri di sottolineatura nei nomi</span><span class="sxs-lookup"><span data-stu-id="35b77-174">Avoid underscores in names</span></span>

<span data-ttu-id="35b77-175">In passato, alcune F# librerie hanno utilizzati caratteri di sottolineatura nei nomi.</span><span class="sxs-lookup"><span data-stu-id="35b77-175">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="35b77-176">Tuttavia, questo è non è più diffuso, in parte perché è in conflitto con le convenzioni di denominazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="35b77-176">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="35b77-177">Ciò premesso, alcune F# programmatori di utilizzare caratteri di sottolineatura frequentemente, in parte per motivi storici e tolleranza d'errore e riguardo è importante.</span><span class="sxs-lookup"><span data-stu-id="35b77-177">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="35b77-178">Tuttavia, tenere presente che lo stile è spesso disliked da altri utenti che dispongono di una scelta sull'opportunità di usarlo.</span><span class="sxs-lookup"><span data-stu-id="35b77-178">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="35b77-179">Alcune eccezioni includono l'interoperabilità con i componenti nativi, in cui i caratteri di sottolineatura sono molto comuni.</span><span class="sxs-lookup"><span data-stu-id="35b77-179">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="35b77-180">Standard di utilizzo F# operatori</span><span class="sxs-lookup"><span data-stu-id="35b77-180">Use standard F# operators</span></span>

<span data-ttu-id="35b77-181">Gli operatori seguenti vengono definiti di F# libreria standard e deve essere usato invece di definire gli equivalenti.</span><span class="sxs-lookup"><span data-stu-id="35b77-181">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="35b77-182">Utilizzo di questi operatori è consigliata perché tende a rendere il codice più leggibile e idiomatico.</span><span class="sxs-lookup"><span data-stu-id="35b77-182">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="35b77-183">Gli sviluppatori con esperienza in OCaml o altri linguaggi di programmazione funzionale possono essere abituati a diversi linguaggi.</span><span class="sxs-lookup"><span data-stu-id="35b77-183">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="35b77-184">L'elenco seguente riepiloga l'elemento consigliato F# operatori.</span><span class="sxs-lookup"><span data-stu-id="35b77-184">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="35b77-185">Utilizzare la sintassi di prefisso per i generics (`Foo<T>`) anziché la sintassi in forma suffissa (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="35b77-185">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="35b77-186">F#eredita sia lo stile di Machine Learning suffisso di denominazione dei tipi generici (ad esempio, `int list`), nonché il prefisso stile .NET (ad esempio, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="35b77-186">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="35b77-187">Preferisce lo stile di .NET, ad eccezione di quattro tipi specifici:</span><span class="sxs-lookup"><span data-stu-id="35b77-187">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="35b77-188">Per F# gli elenchi, usare la forma suffissa: `int list` anziché da `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="35b77-188">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="35b77-189">Per F# opzioni, utilizzare la forma suffissa: `int option` anziché da `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="35b77-189">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="35b77-190">Per F# le matrici, usare il nome sintattico `int[]` anziché da `int array` oppure `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="35b77-190">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="35b77-191">Per le celle di riferimento, usare `int ref` invece `ref<int>` o `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="35b77-191">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="35b77-192">Per tutti gli altri tipi, usare la forma prefissa.</span><span class="sxs-lookup"><span data-stu-id="35b77-192">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="35b77-193">Formattazione di tuple</span><span class="sxs-lookup"><span data-stu-id="35b77-193">Formatting tuples</span></span>

<span data-ttu-id="35b77-194">Creazione di un'istanza di tupla devono essere racchiusi tra parentesi, e le virgole di delimitazione all'interno devono essere seguite da uno spazio singolo, ad esempio: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="35b77-194">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="35b77-195">Viene comunemente accettato per omettere le parentesi nei criteri di ricerca di tuple:</span><span class="sxs-lookup"><span data-stu-id="35b77-195">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="35b77-196">Viene anche comunemente accettato per omettere le parentesi, se la tupla è il valore restituito di una funzione:</span><span class="sxs-lookup"><span data-stu-id="35b77-196">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="35b77-197">In sintesi, preferisce le creazioni di istanze di racchiusi tra parentesi tuple, ma quando si usano le tuple per criteri di ricerca o un valore restituito, viene considerato corretto evitare le parentesi.</span><span class="sxs-lookup"><span data-stu-id="35b77-197">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="35b77-198">Formattazione di dichiarazioni di unione discriminata</span><span class="sxs-lookup"><span data-stu-id="35b77-198">Formatting discriminated union declarations</span></span>

<span data-ttu-id="35b77-199">Impostare un rientro `|` nella definizione del tipo da 4 spazi:</span><span class="sxs-lookup"><span data-stu-id="35b77-199">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="35b77-200">Formattazione di unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="35b77-200">Formatting discriminated unions</span></span>

<span data-ttu-id="35b77-201">Un'istanza le unioni discriminate suddivisi su più righe deve fornire dati in essi contenuti un nuovo ambito con rientro:</span><span class="sxs-lookup"><span data-stu-id="35b77-201">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="35b77-202">La parentesi di chiusura può essere anche in una nuova riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-202">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="35b77-203">Dichiarazioni di record di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-203">Formatting record declarations</span></span>

<span data-ttu-id="35b77-204">Impostare un rientro `{` nel tipo di definizione da 4 spazi e avviare l'elenco dei campi nella stessa riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-204">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="35b77-205">L'inserimento del token di apertura in una nuova riga e il token di chiusura in una nuova riga è preferibile se si sta dichiarando le implementazioni di interfaccia o i membri del record:</span><span class="sxs-lookup"><span data-stu-id="35b77-205">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

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

## <a name="formatting-records"></a><span data-ttu-id="35b77-206">Formattazione di record</span><span class="sxs-lookup"><span data-stu-id="35b77-206">Formatting records</span></span>

<span data-ttu-id="35b77-207">Record brevi possono essere scritti in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-207">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="35b77-208">Record più lunghe deve utilizzare le nuove righe per le etichette:</span><span class="sxs-lookup"><span data-stu-id="35b77-208">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="35b77-209">L'apertura di inserire il contenuto a schede ambito su un token in una nuova riga, e il token di chiusura in una nuova riga è preferibile se si è:</span><span class="sxs-lookup"><span data-stu-id="35b77-209">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="35b77-210">Spostamento record all'interno di codice con ambiti diversi rientro</span><span class="sxs-lookup"><span data-stu-id="35b77-210">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="35b77-211">Piping in una funzione</span><span class="sxs-lookup"><span data-stu-id="35b77-211">Piping them into a function</span></span>

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

<span data-ttu-id="35b77-212">Per gli elementi di elenco e la matrice si applicano le stesse regole.</span><span class="sxs-lookup"><span data-stu-id="35b77-212">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="35b77-213">La formattazione delle espressioni di copia e aggiorna record</span><span class="sxs-lookup"><span data-stu-id="35b77-213">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="35b77-214">Un'espressione di record di copia e aggiornamento è ancora un record, in modo simile linee guida sono valide.</span><span class="sxs-lookup"><span data-stu-id="35b77-214">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="35b77-215">Le espressioni breve possono contenere una sola riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-215">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="35b77-216">Espressioni più lunghe devono usare le nuove righe:</span><span class="sxs-lookup"><span data-stu-id="35b77-216">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="35b77-217">E come le indicazioni di record, è possibile dedicare righe separate per le parentesi graffe e impostare un rientro di un ambito a destra con l'espressione.</span><span class="sxs-lookup"><span data-stu-id="35b77-217">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="35b77-218">Si noti che in alcuni casi speciali, ad esempio il wrapping di un valore con facoltativo senza parentesi, potrebbe essere necessario mantenere una parentesi graffa in una sola riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-218">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="35b77-219">Formattazione di elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="35b77-219">Formatting lists and arrays</span></span>

<span data-ttu-id="35b77-220">Scrivere `x :: l` con spazi prima e dopo il `::` operator (`::` è un operatore di infissi, di conseguenza precedute e seguito da spazi).</span><span class="sxs-lookup"><span data-stu-id="35b77-220">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="35b77-221">Elenco e le matrici dichiarate in un'unica riga devono avere uno spazio dopo la parentesi di apertura e prima della parentesi di chiusura:</span><span class="sxs-lookup"><span data-stu-id="35b77-221">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="35b77-222">Usare sempre almeno uno spazio tra due operatori simile a parentesi graffa distinti.</span><span class="sxs-lookup"><span data-stu-id="35b77-222">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="35b77-223">Ad esempio, lasciare uno spazio tra un `[` e un `{`.</span><span class="sxs-lookup"><span data-stu-id="35b77-223">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="35b77-224">Si applica la stessa delle linee guida per gli elenchi o matrici di tuple.</span><span class="sxs-lookup"><span data-stu-id="35b77-224">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="35b77-225">Gli elenchi e matrici suddivisi su più righe seguono una regola simile dei record:</span><span class="sxs-lookup"><span data-stu-id="35b77-225">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="35b77-226">E come con i record, dichiarando l'apertura e la parentesi di chiusura in una riga separata facilitare lo spostamento di codice intorno e il piping nelle funzioni.</span><span class="sxs-lookup"><span data-stu-id="35b77-226">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="35b77-227">Formattazione se le espressioni</span><span class="sxs-lookup"><span data-stu-id="35b77-227">Formatting if expressions</span></span>

<span data-ttu-id="35b77-228">Rientro di istruzioni condizionali varia a seconda di dimensioni delle espressioni che li compongono.</span><span class="sxs-lookup"><span data-stu-id="35b77-228">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="35b77-229">Se `cond`, `e1` e `e2` sono brevi, è sufficiente scriverli su un'unica riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-229">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="35b77-230">Se uno dei due `cond`, `e1` o `e2` sono più lunghi, ma non su più righe:</span><span class="sxs-lookup"><span data-stu-id="35b77-230">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="35b77-231">Se le espressioni sono su più righe:</span><span class="sxs-lookup"><span data-stu-id="35b77-231">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="35b77-232">Più istruzioni condizionali, con `elif` e `else` vengono rientrate nello stesso ambito come il `if`:</span><span class="sxs-lookup"><span data-stu-id="35b77-232">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="35b77-233">Costrutti di modello corrispondenti</span><span class="sxs-lookup"><span data-stu-id="35b77-233">Pattern matching constructs</span></span>

<span data-ttu-id="35b77-234">Usare un `|` per ogni clausola di una corrispondenza con alcun rientro.</span><span class="sxs-lookup"><span data-stu-id="35b77-234">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="35b77-235">Se l'espressione è breve, è possibile utilizzare una singola riga se ogni sottoespressione anche è semplice.</span><span class="sxs-lookup"><span data-stu-id="35b77-235">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="35b77-236">Se l'espressione a destra del criterio corrispondente freccia è troppo grande, spostarlo alla riga seguente, con rientro un unico passaggio dai `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="35b77-236">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="35b77-237">Criteri di ricerca di funzioni anonime, a partire da `function`, devono in genere non impostare un rientro troppo lontano.</span><span class="sxs-lookup"><span data-stu-id="35b77-237">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="35b77-238">Ad esempio, è bene il rientro di un ambito come segue:</span><span class="sxs-lookup"><span data-stu-id="35b77-238">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="35b77-239">Criteri di ricerca nelle funzioni definite dal `let` oppure `let rec` deve essere rientrati 4 spazi dopo l'avvio di `let`, anche se `function` parola chiave viene usata:</span><span class="sxs-lookup"><span data-stu-id="35b77-239">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="35b77-240">Non è consigliabile allineare le frecce.</span><span class="sxs-lookup"><span data-stu-id="35b77-240">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="35b77-241">Formattazione try / with espressioni</span><span class="sxs-lookup"><span data-stu-id="35b77-241">Formatting try/with expressions</span></span>

<span data-ttu-id="35b77-242">Criteri di ricerca nel tipo di eccezione devono essere rientrato allo stesso livello `with`.</span><span class="sxs-lookup"><span data-stu-id="35b77-242">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="35b77-243">Formattazione dell'applicazione di parametro (funzione)</span><span class="sxs-lookup"><span data-stu-id="35b77-243">Formatting function parameter application</span></span>

<span data-ttu-id="35b77-244">In generale, la maggior parte delle applicazione di parametro di funzione viene eseguita nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="35b77-244">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="35b77-245">Se si vuole applicare parametri a una funzione in una nuova riga, impostare un rientro per un ambito.</span><span class="sxs-lookup"><span data-stu-id="35b77-245">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="35b77-246">Le stesse linee guida applicano per le espressioni lambda come argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="35b77-246">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="35b77-247">Se il corpo di un'espressione lambda, il corpo può contenere un'altra riga, rientrata in base a un ambito</span><span class="sxs-lookup"><span data-stu-id="35b77-247">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="35b77-248">Tuttavia, se il corpo di un'espressione lambda su più righe, è consigliabile estrarla factoring in funzioni separate piuttosto che dispone di un costrutto multilinea applicato come un singolo argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="35b77-248">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="35b77-249">Gli operatori infissi di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-249">Formatting infix operators</span></span>

<span data-ttu-id="35b77-250">Operatori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="35b77-250">Separate operators by spaces.</span></span> <span data-ttu-id="35b77-251">Sono evidenti eccezioni a questa regola il `!` e `.` operatori.</span><span class="sxs-lookup"><span data-stu-id="35b77-251">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="35b77-252">Le espressioni di infissi sono OK lineup nella stessa colonna:</span><span class="sxs-lookup"><span data-stu-id="35b77-252">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="35b77-253">Formattazione operatori pipeline</span><span class="sxs-lookup"><span data-stu-id="35b77-253">Formatting pipeline operators</span></span>

<span data-ttu-id="35b77-254">Pipeline `|>` operatori devono essere inserito sotto le espressioni operano in base a.</span><span class="sxs-lookup"><span data-stu-id="35b77-254">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="35b77-255">Formattazione di moduli</span><span class="sxs-lookup"><span data-stu-id="35b77-255">Formatting modules</span></span>

<span data-ttu-id="35b77-256">Il codice in un modulo locale deve essere rientrato rispetto al modulo, ma il codice in un modulo di primo livello non debba essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="35b77-256">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="35b77-257">Elementi Namespace non sono necessario impostare un rientro.</span><span class="sxs-lookup"><span data-stu-id="35b77-257">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="35b77-258">Formattazione di espressioni di oggetto e interfacce</span><span class="sxs-lookup"><span data-stu-id="35b77-258">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="35b77-259">Interfacce e le espressioni di oggetto devono essere allineate nello stesso modo con `member` viene applicato un rientro dopo 4 spazi.</span><span class="sxs-lookup"><span data-stu-id="35b77-259">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="35b77-260">Spazi vuoti nelle espressioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-260">Formatting white space in expressions</span></span>

<span data-ttu-id="35b77-261">Evitare gli spazi vuoti estranei nel F# le espressioni.</span><span class="sxs-lookup"><span data-stu-id="35b77-261">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="35b77-262">Gli argomenti denominati non necessario anche spazio che racchiudono il `=`:</span><span class="sxs-lookup"><span data-stu-id="35b77-262">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="35b77-263">Attributi di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-263">Formatting attributes</span></span>

<span data-ttu-id="35b77-264">[Gli attributi](../language-reference/attributes.md) vengono inseriti sopra un costrutto:</span><span class="sxs-lookup"><span data-stu-id="35b77-264">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="35b77-265">Gli attributi dei parametri di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-265">Formatting attributes on parameters</span></span>

<span data-ttu-id="35b77-266">Gli attributi possono essere anche punti di parametri.</span><span class="sxs-lookup"><span data-stu-id="35b77-266">Attributes can also be places on parameters.</span></span> <span data-ttu-id="35b77-267">In questo caso, inserire quindi sulla stessa riga come parametro e prima del nome:</span><span class="sxs-lookup"><span data-stu-id="35b77-267">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="35b77-268">Formattazione di più attributi</span><span class="sxs-lookup"><span data-stu-id="35b77-268">Formatting multiple attributes</span></span>

<span data-ttu-id="35b77-269">Quando vengono applicati più attributi a un costrutto che non è un parametro, devono essere posizionate in modo che sia presente un attributo per riga:</span><span class="sxs-lookup"><span data-stu-id="35b77-269">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="35b77-270">Quando applicato a un parametro, devono essere nella stessa riga e separati da un `;` separatore.</span><span class="sxs-lookup"><span data-stu-id="35b77-270">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="35b77-271">Valori letterali di formattazione</span><span class="sxs-lookup"><span data-stu-id="35b77-271">Formatting literals</span></span>

<span data-ttu-id="35b77-272">[F#valori letterali](../language-reference/literals.md) utilizzando il `Literal` attributo deve inserire l'attributo su una riga e usare camelCase di denominazione:</span><span class="sxs-lookup"><span data-stu-id="35b77-272">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="35b77-273">Evitare di inserire l'attributo sulla stessa riga come valore.</span><span class="sxs-lookup"><span data-stu-id="35b77-273">Avoid placing the attribute on the same line as the value.</span></span>
