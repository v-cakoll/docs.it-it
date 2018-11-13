---
title: Introduzione alla programmazione funzionale in F#
description: Scopri i concetti fondamentali della programmazione funzionale in F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724478"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="8a71a-103">Introduzione alla programmazione funzionale in F#</span><span class="sxs-lookup"><span data-stu-id="8a71a-103">Introduction to Functional Programming in F#</span></span> #

<span data-ttu-id="8a71a-104">Programmazione funzionale è uno stile di programmazione che mette in evidenza l'utilizzo di funzioni e dati non modificabili.</span><span class="sxs-lookup"><span data-stu-id="8a71a-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="8a71a-105">Programmazione funzionale tipizzata è quando la programmazione funzionale è combinata con i tipi statici, ad esempio con F#.</span><span class="sxs-lookup"><span data-stu-id="8a71a-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="8a71a-106">In generale, i concetti seguenti sono evidenziati nella programmazione funzionale:</span><span class="sxs-lookup"><span data-stu-id="8a71a-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="8a71a-107">Funzioni come i costrutti primari che è usare</span><span class="sxs-lookup"><span data-stu-id="8a71a-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="8a71a-108">Espressioni anziché le istruzioni</span><span class="sxs-lookup"><span data-stu-id="8a71a-108">Expressions instead of statements</span></span>
* <span data-ttu-id="8a71a-109">Valori non modificabili sulle variabili</span><span class="sxs-lookup"><span data-stu-id="8a71a-109">Immutable values over variables</span></span>
* <span data-ttu-id="8a71a-110">Programmazione dichiarativa tramite programmazione imperativa</span><span class="sxs-lookup"><span data-stu-id="8a71a-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="8a71a-111">In questa serie, si esamineranno concetti e modelli di programmazione funzionale con F#.</span><span class="sxs-lookup"><span data-stu-id="8a71a-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="8a71a-112">Corso della trattazione, scoprirai alcune F# troppo.</span><span class="sxs-lookup"><span data-stu-id="8a71a-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="8a71a-113">Terminologia</span><span class="sxs-lookup"><span data-stu-id="8a71a-113">Terminology</span></span>

<span data-ttu-id="8a71a-114">Programmazione funzionale, ad esempio altri paradigmi di programmazione, viene fornito con un vocabolario che si sarà necessario conoscere.</span><span class="sxs-lookup"><span data-stu-id="8a71a-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="8a71a-115">Ecco alcuni termini comuni si vedrà tutto il tempo:</span><span class="sxs-lookup"><span data-stu-id="8a71a-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="8a71a-116">**Funzione** -una funzione è un costrutto che produrrà un output quando viene specificato un input.</span><span class="sxs-lookup"><span data-stu-id="8a71a-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="8a71a-117">In termini più formali, si _viene eseguito il mapping_ imposta un elemento da uno a un altro set.</span><span class="sxs-lookup"><span data-stu-id="8a71a-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="8a71a-118">Questo formato viene eseguito il lift nella concreti molti aspetti, soprattutto quando si usa funzioni che operano su raccolte di dati.</span><span class="sxs-lookup"><span data-stu-id="8a71a-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="8a71a-119">Si tratta di concetto nella programmazione funzionale più base (e importante).</span><span class="sxs-lookup"><span data-stu-id="8a71a-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="8a71a-120">**Espressione** -un'espressione è un costrutto di codice che produce un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="8a71a-121">In F#, questo valore deve essere associato o ignorato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="8a71a-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="8a71a-122">Un'espressione può essere facilmente sostituita da una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="8a71a-123">**Purezza** -purezza è una proprietà di una funzione di modo che il relativo valore restituito è sempre uguale per gli stessi argomenti e che la sua valutazione ha effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="8a71a-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="8a71a-124">Una funzione pura dipende interamente relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="8a71a-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="8a71a-125">**Trasparenza referenziale** -trasparenza referenziale è una proprietà di espressioni tale che può essere sostituiti con il relativo output senza influire sul comportamento di un programma.</span><span class="sxs-lookup"><span data-stu-id="8a71a-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="8a71a-126">**Immutabilità** -significa immutabilità che un valore non può essere modificato sul posto.</span><span class="sxs-lookup"><span data-stu-id="8a71a-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="8a71a-127">Si tratta a differenza delle variabili, che può essere modificato in posizione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="8a71a-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="8a71a-128">Examples</span></span>

<span data-ttu-id="8a71a-129">Gli esempi seguenti illustrano questi concetti di base.</span><span class="sxs-lookup"><span data-stu-id="8a71a-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="8a71a-130">Funzioni</span><span class="sxs-lookup"><span data-stu-id="8a71a-130">Functions</span></span>

<span data-ttu-id="8a71a-131">Costrutto più fondamentale e comune nella programmazione funzionale sono la funzione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="8a71a-132">Di seguito è una funzione semplice che aggiunge 1 a un integer:</span><span class="sxs-lookup"><span data-stu-id="8a71a-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="8a71a-133">La firma di tipo è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8a71a-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="8a71a-134">La firma può essere letto come, "`addOne` accetta un `int` denominate `x` e produrrà un `int`".</span><span class="sxs-lookup"><span data-stu-id="8a71a-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="8a71a-135">Più formalmente `addOne` viene _mapping_ un valore dal set di numeri interi al set di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="8a71a-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="8a71a-136">Il `->` token indica questo mapping.</span><span class="sxs-lookup"><span data-stu-id="8a71a-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="8a71a-137">In F#, in genere è possibile esaminare la firma della funzione e farsi un'idea di cosa.</span><span class="sxs-lookup"><span data-stu-id="8a71a-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="8a71a-138">Quindi, perché è la firma importante?</span><span class="sxs-lookup"><span data-stu-id="8a71a-138">So, why is the signature important?</span></span> <span data-ttu-id="8a71a-139">Nella programmazione funzionale tipizzata, l'implementazione di una funzione è spesso meno importante della firma del tipo effettivo.</span><span class="sxs-lookup"><span data-stu-id="8a71a-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="8a71a-140">Il fatto che `addOne` aggiunge il valore 1 per un numero intero è interessante in fase di esecuzione, ma quando si costruisce un programma, il fatto che accetta e restituisce un `int` è ciò che indica come verrà effettivamente usata questa funzione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="8a71a-141">Inoltre, quando si utilizza questa funzione in modo corretto (in relazione la firma di tipo), la diagnosi dei problemi è possibile solo all'interno del corpo del `addOne` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8a71a-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="8a71a-142">Questo è l'impulso di programmazione funzionale tipizzata.</span><span class="sxs-lookup"><span data-stu-id="8a71a-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="8a71a-143">Espressioni</span><span class="sxs-lookup"><span data-stu-id="8a71a-143">Expressions</span></span>

<span data-ttu-id="8a71a-144">Le espressioni sono costrutti che restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="8a71a-145">A differenza delle istruzioni che eseguono un'azione, espressioni possono essere considerate eseguendo un'azione che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="8a71a-146">Le espressioni vengono usate quasi sempre a favore di istruzioni nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="8a71a-147">Si consideri la funzione precedente, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="8a71a-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="8a71a-148">Il corpo di `addOne` è un'espressione:</span><span class="sxs-lookup"><span data-stu-id="8a71a-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="8a71a-149">È il risultato dell'espressione che definisce il tipo di risultato di `addOne` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8a71a-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="8a71a-150">Ad esempio, l'espressione che costituisce questa funzione è stato possibile modificare per essere un tipo diverso, ad esempio un `string`:</span><span class="sxs-lookup"><span data-stu-id="8a71a-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="8a71a-151">È ora la firma della funzione:</span><span class="sxs-lookup"><span data-stu-id="8a71a-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="8a71a-152">Poiché qualsiasi tipo in F# può avere `ToString()` chiamati su di esso, il tipo di `x` apportata generico (chiamato [generalizzazione automatica](../language-reference/generics/automatic-generalization.md)), e il tipo risultante è un `string`.</span><span class="sxs-lookup"><span data-stu-id="8a71a-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="8a71a-153">Le espressioni non sono appena i corpi delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="8a71a-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="8a71a-154">È possibile disporre le espressioni che producono un valore utilizzato in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="8a71a-155">Un comune è `if`:</span><span class="sxs-lookup"><span data-stu-id="8a71a-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="8a71a-156">Il `if` espressione produce un valore chiamato `result`.</span><span class="sxs-lookup"><span data-stu-id="8a71a-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="8a71a-157">Si noti che è possibile omettere `result` interamente, rendendo il `if` il corpo di espressione del `addOneIfOdd` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8a71a-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="8a71a-158">L'aspetto principale da ricordare riguardo a espressioni è che producono un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="8a71a-159">È presente un tipo speciale, `unit`, che viene usato quando sono presenti elementi da restituire.</span><span class="sxs-lookup"><span data-stu-id="8a71a-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="8a71a-160">Ad esempio, prendere in considerazione questa semplice funzione:</span><span class="sxs-lookup"><span data-stu-id="8a71a-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

<span data-ttu-id="8a71a-161">La firma è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8a71a-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="8a71a-162">Il `unit` tipo non indica che è presente alcun valore effettivo restituito.</span><span class="sxs-lookup"><span data-stu-id="8a71a-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="8a71a-163">Ciò è utile quando si dispone di una routine che deve "aziendale", anche non se nessun valore da restituire in seguito a tale lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a71a-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="8a71a-164">Si tratta in netto contrasto con la programmazione imperativa, in cui l'equivalente `if` costrutto è un'istruzione e restituendo valori viene spesso eseguita con le variabili di mutazione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="8a71a-165">Ad esempio, in C#, il codice potrebbe essere scritto come segue:</span><span class="sxs-lookup"><span data-stu-id="8a71a-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="8a71a-166">Vale la pena notare che C# e altri linguaggi di tipo C supportano i [espressione ternaria](../../csharp/language-reference/operators/conditional-operator.md), che consentono una programmazione condizionale basata su espressione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="8a71a-167">Nella programmazione funzionale, è raro che venga modificato i valori con le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8a71a-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="8a71a-168">Sebbene alcuni linguaggi funzionali supportano le istruzioni e modifica, non è più comune per usare questi concetti in programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="8a71a-169">Funzioni pure</span><span class="sxs-lookup"><span data-stu-id="8a71a-169">Pure functions</span></span>

<span data-ttu-id="8a71a-170">Come accennato in precedenza le funzioni pure sono funzioni che:</span><span class="sxs-lookup"><span data-stu-id="8a71a-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="8a71a-171">Restituiscono sempre lo stesso valore per lo stesso input.</span><span class="sxs-lookup"><span data-stu-id="8a71a-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="8a71a-172">Non hanno effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="8a71a-172">Have no side effects.</span></span>

<span data-ttu-id="8a71a-173">È utile pensare a funzioni matematiche in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="8a71a-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="8a71a-174">In matematica, le funzioni dipendono unicamente i relativi argomenti e non dispongono di tutti gli effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="8a71a-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="8a71a-175">Alla funzione matematica `f(x) = x + 1`, il valore di `f(x)` dipende solo dal valore di `x`.</span><span class="sxs-lookup"><span data-stu-id="8a71a-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="8a71a-176">Nella programmazione funzionale le funzioni pure sono allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="8a71a-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="8a71a-177">Quando si scrive una funzione pura, la funzione deve dipendere dai relativi argomenti e non esegue alcuna azione che comporta un effetto collaterale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="8a71a-178">Ecco un esempio di una funzione non pura perché dipende da stato globale, o modificabile:</span><span class="sxs-lookup"><span data-stu-id="8a71a-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="8a71a-179">Il `addOneToValue` funzione è chiaramente non pure, poiché `value` è stato possibile modificare in qualsiasi momento per avere un valore diverso da 1.</span><span class="sxs-lookup"><span data-stu-id="8a71a-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="8a71a-180">Questo modello di base a un valore globale è di evitare nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="8a71a-181">Ecco un altro esempio di una funzione non pura, perché consente di eseguire un effetto collaterale:</span><span class="sxs-lookup"><span data-stu-id="8a71a-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="8a71a-182">Anche se questa funzione non dipende da un valore globale, scrive il valore di `x` all'output del programma.</span><span class="sxs-lookup"><span data-stu-id="8a71a-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="8a71a-183">Anche se non vi sono intrinsecamente problemi con questa operazione, significa che la funzione non pura.</span><span class="sxs-lookup"><span data-stu-id="8a71a-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span>

<span data-ttu-id="8a71a-184">Rimozione di `printfn` istruzione finally rende la funzione pure:</span><span class="sxs-lookup"><span data-stu-id="8a71a-184">Removing the `printfn` statement finally makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="8a71a-185">Anche se questa funzione non è intrinsecamente _migliori_ rispetto alla versione precedente con il `printfn` istruzione, ma questa soluzione garantisce che questa funzione non è di restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-185">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="8a71a-186">Chiamare questa funzione una sola volta o 1 miliardi di volte in cui verrà comunque comportare la stessa operazione: semplicemente che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="8a71a-186">Calling this function once or 1 billion times will still result in the same thing: just producing a value.</span></span> <span data-ttu-id="8a71a-187">Questo prevedibilità è importante nella programmazione funzionale, quanto significa che qualsiasi funzione pura è referenziali trasparente.</span><span class="sxs-lookup"><span data-stu-id="8a71a-187">This predictability is valuable in functional programming, as it means that any pure function is referentially transparent.</span></span>

### <a name="referential-transparency"></a><span data-ttu-id="8a71a-188">Trasparenza referenziale</span><span class="sxs-lookup"><span data-stu-id="8a71a-188">Referential Transparency</span></span>

<span data-ttu-id="8a71a-189">La trasparenza referenziale è una proprietà di espressioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="8a71a-189">Referential transparency is a property of expressions and functions.</span></span> <span data-ttu-id="8a71a-190">Per un'espressione referenziali Transparent, deve essere in grado di essere sostituito con il relativo valore risulta senza modificare il comportamento del programma.</span><span class="sxs-lookup"><span data-stu-id="8a71a-190">For an expression to be referentially transparent, it must be able to be replaced with its resulting value without changing the program's behavior.</span></span> <span data-ttu-id="8a71a-191">Tutte le funzioni pure sono trasparenti referenziali.</span><span class="sxs-lookup"><span data-stu-id="8a71a-191">All pure functions are referentially transparent.</span></span>

<span data-ttu-id="8a71a-192">Come con le funzioni pure, può essere utile pensare a trasparenza referenziale dal punto di vista matematico.</span><span class="sxs-lookup"><span data-stu-id="8a71a-192">As with pure functions, it can be helpful to think of referential transparency from a mathematical perspective.</span></span> <span data-ttu-id="8a71a-193">Nell'espressione matematica `y = f(x)`, `f(x)` può essere sostituito dal risultato della funzione e rimarrà comunque disponibile uguale a `y`.</span><span class="sxs-lookup"><span data-stu-id="8a71a-193">In the mathematical expression `y = f(x)`, `f(x)` can be replaced by the result of the function and it will still be equal to `y`.</span></span> <span data-ttu-id="8a71a-194">Questo vale anche per la trasparenza referenziale nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-194">This is equally true for referential transparency in functional programming.</span></span>

<span data-ttu-id="8a71a-195">Si consiglia di chiamare definita in precedenza `addOneIfOdd` funzione due volte:</span><span class="sxs-lookup"><span data-stu-id="8a71a-195">Consider calling the previously defined `addOneIfOdd` function twice:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

<span data-ttu-id="8a71a-196">Non è possibile sostituire ogni chiamata di funzione con il corpo della funzione, sostituendo l'argomento `input` con ogni valore:</span><span class="sxs-lookup"><span data-stu-id="8a71a-196">We can replace each function call with the function body, substituting the argument `input` with each value:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

<span data-ttu-id="8a71a-197">Entrambe `res1` e `res2` hanno lo stesso valore come se la funzione è stata chiamata, che indica che `addOneIfOdd` referenziali trasparente.</span><span class="sxs-lookup"><span data-stu-id="8a71a-197">Both `res1` and `res2` have the same value as if the function was called, indicating that `addOneIfOdd` is referentially transparent!</span></span>

<span data-ttu-id="8a71a-198">Inoltre, non ha una funzione pure in modo che sia anche referenziali trasparente.</span><span class="sxs-lookup"><span data-stu-id="8a71a-198">Additionally, a function doesn't have to be pure to also be referentially transparent.</span></span> <span data-ttu-id="8a71a-199">Prendere in considerazione una definizione precedente di `addOneTovalue`:</span><span class="sxs-lookup"><span data-stu-id="8a71a-199">Consider a previous definition of  `addOneTovalue`:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="8a71a-200">Qualsiasi chiamata a questa funzione può anche essere sostituita dal rispettivo corpo e gli stessi elementi si verificherà ogni volta che:</span><span class="sxs-lookup"><span data-stu-id="8a71a-200">Any call to this function can also be replaced by its body and the same things will happen each time:</span></span>

* <span data-ttu-id="8a71a-201">L'output viene stampato il valore, prima dell'aggiunta</span><span class="sxs-lookup"><span data-stu-id="8a71a-201">The value, prior to being added to, is printed to the output</span></span>
* <span data-ttu-id="8a71a-202">Il valore è 1 aggiunto</span><span class="sxs-lookup"><span data-stu-id="8a71a-202">The value has 1 added to it</span></span>

<span data-ttu-id="8a71a-203">Durante la programmazione in F#, è spesso trasparenza referenziale che è l'obiettivo, anziché di purezza.</span><span class="sxs-lookup"><span data-stu-id="8a71a-203">When programming in F#, it is often referential transparency that is the goal, rather than purity.</span></span> <span data-ttu-id="8a71a-204">Tuttavia, è comunque consigliabile scrivere funzioni pure quando possibile.</span><span class="sxs-lookup"><span data-stu-id="8a71a-204">However, it is still good practice to write pure functions when you can.</span></span>

### <a name="immutability"></a><span data-ttu-id="8a71a-205">Immutabilità</span><span class="sxs-lookup"><span data-stu-id="8a71a-205">Immutability</span></span>

<span data-ttu-id="8a71a-206">Infine, uno dei concetti più importanti della programmazione funzionale tipizzato è immutabilità.</span><span class="sxs-lookup"><span data-stu-id="8a71a-206">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="8a71a-207">In F#, tutti i valori non sono modificabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8a71a-207">In F#, all values are immutable by default.</span></span> <span data-ttu-id="8a71a-208">Pertanto, che non è possibile modificare sul posto a meno che non è esplicitamente contrassegnarli come modificabile.</span><span class="sxs-lookup"><span data-stu-id="8a71a-208">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="8a71a-209">In pratica, funzionante con i valori non modificabili significa che si modifica l'approccio alla programmazione da, "Devo modificare un elemento", per "è necessario produrre un nuovo valore".</span><span class="sxs-lookup"><span data-stu-id="8a71a-209">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="8a71a-210">Ad esempio, aggiungendo 1 al valore significa che produce un nuovo valore, non mutazione quello esistente:</span><span class="sxs-lookup"><span data-stu-id="8a71a-210">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="8a71a-211">In F#, il codice seguente esegue **non** modificare le `value` funzione; al contrario, esegue un controllo di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="8a71a-211">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="8a71a-212">Alcuni linguaggi di programmazione funzionale non supportano affatto mutation.</span><span class="sxs-lookup"><span data-stu-id="8a71a-212">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="8a71a-213">In F#, è supportato, ma non è il comportamento predefinito per i valori.</span><span class="sxs-lookup"><span data-stu-id="8a71a-213">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="8a71a-214">Questo concetto consente di estendere ulteriormente le strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="8a71a-214">This concept extends even further to data structures.</span></span> <span data-ttu-id="8a71a-215">Nella programmazione funzionale, le strutture di dati non modificabili, ad esempio set (e molto altro ancora) avere un'implementazione diversa rispetto a inizialmente potrebbe prevedono.</span><span class="sxs-lookup"><span data-stu-id="8a71a-215">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="8a71a-216">Concettualmente, un valore, ad esempio l'aggiunta di un elemento a un set non modifica il set, genera una _nuovo_ impostata con il valore aggiunto.</span><span class="sxs-lookup"><span data-stu-id="8a71a-216">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="8a71a-217">Dietro le quinte, questa operazione viene spesso eseguita da una struttura di dati diversi che consente di rilevamento in modo efficiente un valore in modo che la rappresentazione appropriata dei dati può essere fornita come risultato.</span><span class="sxs-lookup"><span data-stu-id="8a71a-217">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="8a71a-218">Questo stile di valori e le strutture di dati è fondamentale, poiché costringe a trattare qualsiasi operazione che modifica un elemento come se crea una nuova versione di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="8a71a-218">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="8a71a-219">In questo modo per elementi quali l'uguaglianza e la comparabilità coerenza nei programmi.</span><span class="sxs-lookup"><span data-stu-id="8a71a-219">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a71a-220">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8a71a-220">Next steps</span></span>

<span data-ttu-id="8a71a-221">Nella sezione successiva illustrerà accuratamente le funzioni, esplorazione di modi diversi, è possibile usarli nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8a71a-221">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="8a71a-222">[Funzioni di prima classe](first-class-functions.md) esamina le funzioni in profondità, che mostra come è possibile usarli in contesti diversi.</span><span class="sxs-lookup"><span data-stu-id="8a71a-222">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="8a71a-223">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8a71a-223">Further reading</span></span>

<span data-ttu-id="8a71a-224">Il [pensando a livello funzionale](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) serie è un'altra risorsa eccezionale per apprendere la programmazione funzionale con F#.</span><span class="sxs-lookup"><span data-stu-id="8a71a-224">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="8a71a-225">Vengono descritti i concetti fondamentali della programmazione funzionale in modo pragmatico e facile da leggere, tramite F# funzionalità per illustrare i concetti.</span><span class="sxs-lookup"><span data-stu-id="8a71a-225">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>