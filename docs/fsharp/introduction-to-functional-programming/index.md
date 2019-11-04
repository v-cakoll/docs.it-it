---
title: Introduzione alla programmazione funzionale in F#
description: Informazioni sulle nozioni di base della programmazione F#funzionale in.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424706"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="aa5a1-103">Introduzione alla programmazione funzionale in F\#</span><span class="sxs-lookup"><span data-stu-id="aa5a1-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="aa5a1-104">La programmazione funzionale è uno stile di programmazione che enfatizza l'uso di funzioni e dati non modificabili.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="aa5a1-105">La programmazione funzionale tipizzata si verifica quando la programmazione funzionale è combinata con tipi statici F#, ad esempio con.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="aa5a1-106">In generale, i concetti seguenti sono evidenziati nella programmazione funzionale:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="aa5a1-107">Funzioni come costrutti primari usati</span><span class="sxs-lookup"><span data-stu-id="aa5a1-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="aa5a1-108">Espressioni anziché istruzioni</span><span class="sxs-lookup"><span data-stu-id="aa5a1-108">Expressions instead of statements</span></span>
* <span data-ttu-id="aa5a1-109">Valori non modificabili sulle variabili</span><span class="sxs-lookup"><span data-stu-id="aa5a1-109">Immutable values over variables</span></span>
* <span data-ttu-id="aa5a1-110">Programmazione dichiarativa sulla programmazione imperativa</span><span class="sxs-lookup"><span data-stu-id="aa5a1-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="aa5a1-111">In questa serie verranno illustrati concetti e modelli nella programmazione funzionale tramite F#.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="aa5a1-112">Si apprenderà anche un F# altro aspetto.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="aa5a1-113">Terminologia</span><span class="sxs-lookup"><span data-stu-id="aa5a1-113">Terminology</span></span>

<span data-ttu-id="aa5a1-114">La programmazione funzionale, come altri paradigmi di programmazione, viene fornita con un vocabolario che dovrà essere apprese in futuro.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="aa5a1-115">Di seguito sono riportati alcuni termini comuni:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="aa5a1-116">**Function** : una funzione è un costrutto che produce un output quando viene specificato un input.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="aa5a1-117">Più formalmente, viene eseguito il _mapping_ di un elemento da un set a un altro set.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="aa5a1-118">Questo formalismo viene sollevato nel concreto in molti modi, soprattutto quando si usano funzioni che operano su raccolte di dati.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="aa5a1-119">Si tratta del concetto più semplice e importante nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="aa5a1-120">**Espressione** : un'espressione è un costrutto nel codice che produce un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="aa5a1-121">In F#, questo valore deve essere associato o ignorato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="aa5a1-122">Un'espressione può essere sostituita in modo banale da una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="aa5a1-123">**Purezza** -purezza è una proprietà di una funzione in modo che il valore restituito sia sempre lo stesso per gli stessi argomenti e che la relativa valutazione non abbia effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="aa5a1-124">Una funzione pura dipende interamente dagli argomenti.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="aa5a1-125">**Trasparenza referenziale** : la trasparenza referenziale è una proprietà di espressioni in modo che possano essere sostituite con il relativo output senza influire sul comportamento di un programma.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="aa5a1-126">**Immutabilità-** immutabilità indica che un valore non può essere modificato sul posto.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="aa5a1-127">Questo si differenzia dalle variabili, che possono cambiare sul posto.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="aa5a1-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="aa5a1-128">Examples</span></span>

<span data-ttu-id="aa5a1-129">Gli esempi seguenti illustrano questi concetti di base.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="aa5a1-130">Funzioni</span><span class="sxs-lookup"><span data-stu-id="aa5a1-130">Functions</span></span>

<span data-ttu-id="aa5a1-131">Il costrutto più comune e fondamentale nella programmazione funzionale è la funzione.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="aa5a1-132">Ecco una funzione semplice che aggiunge 1 a un numero intero:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="aa5a1-133">La firma del tipo è la seguente:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="aa5a1-134">La firma può essere letta come "`addOne` accetta una `int` denominata `x` e produrrà un `int`".</span><span class="sxs-lookup"><span data-stu-id="aa5a1-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="aa5a1-135">Più formalmente, `addOne` sta _eseguendo il mapping_ di un valore dal set di numeri interi al set di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="aa5a1-136">Il token `->` significa questo mapping.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="aa5a1-137">In F#è in genere possibile esaminare la firma della funzione per ottenere un'idea di come funziona.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="aa5a1-138">Perché la firma è importante?</span><span class="sxs-lookup"><span data-stu-id="aa5a1-138">So, why is the signature important?</span></span> <span data-ttu-id="aa5a1-139">Nella programmazione funzionale tipizzata, l'implementazione di una funzione è spesso meno importante della firma del tipo effettivo.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="aa5a1-140">Il fatto che `addOne` aggiunge il valore 1 a un intero è interessante in fase di esecuzione, ma quando si costruisce un programma, il fatto che accetta e restituisce un `int` è ciò che informa come si userà effettivamente questa funzione.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="aa5a1-141">Inoltre, una volta utilizzata correttamente questa funzione (rispetto alla firma del tipo), la diagnosi di eventuali problemi può essere eseguita solo all'interno del corpo della funzione `addOne`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="aa5a1-142">Si tratta dell'impeto dietro la programmazione funzionale tipizzata.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="aa5a1-143">Espressioni</span><span class="sxs-lookup"><span data-stu-id="aa5a1-143">Expressions</span></span>

<span data-ttu-id="aa5a1-144">Le espressioni sono costrutti che restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="aa5a1-145">Diversamente dalle istruzioni che eseguono un'azione, le espressioni possono essere considerate l'esecuzione di un'azione che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="aa5a1-146">Le espressioni vengono quasi sempre utilizzate a favore delle istruzioni nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="aa5a1-147">Si consideri la funzione precedente `addOne`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="aa5a1-148">Il corpo di `addOne` è un'espressione:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="aa5a1-149">È il risultato di questa espressione che definisce il tipo di risultato della funzione `addOne`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="aa5a1-150">Ad esempio, l'espressione che costituisce questa funzione può essere modificata in modo che sia un tipo diverso, ad esempio un `string`:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="aa5a1-151">La firma della funzione è ora:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="aa5a1-152">Poiché qualsiasi tipo in F# può avere `ToString()` chiamato su di esso, il tipo di `x` è stato reso generico (chiamato [generalizzazione automatica](../language-reference/generics/automatic-generalization.md)) e il tipo risultante è un `string`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="aa5a1-153">Le espressioni non sono solo i corpi di funzioni.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="aa5a1-154">È possibile avere espressioni che producono un valore usato altrove.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="aa5a1-155">Uno più comune è `if`:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-155">A common one is `if`:</span></span>

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

<span data-ttu-id="aa5a1-156">L'espressione `if` produce un valore denominato `result`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="aa5a1-157">Si noti che è possibile omettere `result` completamente, rendendo l'espressione `if` il corpo della funzione `addOneIfOdd`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="aa5a1-158">La cosa principale da ricordare sulle espressioni è che producono un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="aa5a1-159">È disponibile un tipo speciale, `unit`, che viene usato quando non è necessario restituire alcun valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="aa5a1-160">Si consideri, ad esempio, questa semplice funzione:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="aa5a1-161">La firma ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="aa5a1-162">Il tipo di `unit` indica che non viene restituito alcun valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="aa5a1-163">Questa operazione è utile quando si dispone di una routine che deve "lavorare", anche se non è disponibile alcun valore da restituire come risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="aa5a1-164">Si tratta di un contrasto acuto rispetto alla programmazione imperativa, in cui il costrutto `if` equivalente è un'istruzione e la produzione di valori viene spesso eseguita con le variabili mutanti.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="aa5a1-165">Ad esempio, in C#il codice potrebbe essere scritto come segue:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="aa5a1-166">Vale la pena notare che C# e altri linguaggi di tipo C supportano l' [espressione ternaria](../../csharp/language-reference/operators/conditional-operator.md), che consente la programmazione condizionale basata su espressioni.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="aa5a1-167">Nella programmazione funzionale è raro mutare i valori con le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="aa5a1-168">Sebbene alcuni linguaggi funzionali supportino istruzioni e mutazioni, non è comune usare questi concetti nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="aa5a1-169">Funzioni pure</span><span class="sxs-lookup"><span data-stu-id="aa5a1-169">Pure functions</span></span>

<span data-ttu-id="aa5a1-170">Come indicato in precedenza, le funzioni pure sono funzioni che:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="aa5a1-171">Restituisce sempre lo stesso valore per lo stesso input.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="aa5a1-172">Non hanno effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-172">Have no side effects.</span></span>

<span data-ttu-id="aa5a1-173">È utile considerare le funzioni matematiche in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="aa5a1-174">In matematica le funzioni dipendono solo dai rispettivi argomenti e non hanno effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="aa5a1-175">Nella funzione matematica `f(x) = x + 1`il valore di `f(x)` dipende solo dal valore di `x`.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="aa5a1-176">Le funzioni pure nella programmazione funzionale hanno lo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="aa5a1-177">Quando si scrive una funzione pura, la funzione deve dipendere solo dai relativi argomenti e non eseguire alcuna azione che abbia come risultato un effetto collaterale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="aa5a1-178">Di seguito è riportato un esempio di una funzione non pura perché dipende da uno stato modificabile globale:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="aa5a1-179">La funzione `addOneToValue` è chiaramente impura, perché `value` può essere modificata in qualsiasi momento per avere un valore diverso da 1.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="aa5a1-180">Questo modello di a seconda di un valore globale deve essere evitato nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="aa5a1-181">Di seguito è riportato un altro esempio di una funzione non pura, perché esegue un effetto collaterale:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="aa5a1-182">Sebbene questa funzione non dipenda da un valore globale, scrive il valore di `x` nell'output del programma.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="aa5a1-183">Sebbene non vi sia alcun problema intrinseco, significa che la funzione non è pura.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="aa5a1-184">Se un'altra parte del programma dipende da un elemento esterno al programma, ad esempio il buffer di output, la chiamata a questa funzione può influire sull'altra parte del programma.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="aa5a1-185">La rimozione dell'istruzione `printfn` rende la funzione pure:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="aa5a1-186">Anche se questa funzione non è intrinsecamente _migliore_ della versione precedente con l'istruzione `printfn`, garantisce che la funzione restituisca un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="aa5a1-187">La chiamata di questa funzione un numero qualsiasi di volte produce lo stesso risultato: produce solo un valore.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="aa5a1-188">La prevedibilità fornita dalla purezza è un elemento che molti programmatori funzionali si impegnano.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="aa5a1-189">Immutabilità</span><span class="sxs-lookup"><span data-stu-id="aa5a1-189">Immutability</span></span>

<span data-ttu-id="aa5a1-190">Infine, uno dei concetti fondamentali della programmazione funzionale tipizzata è l'immutabilità.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="aa5a1-191">In F#tutti i valori non sono modificabili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="aa5a1-192">Ciò significa che non possono essere mutate sul posto a meno che non vengano contrassegnate in modo esplicito come modificabile.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="aa5a1-193">In pratica, l'utilizzo di valori non modificabili significa che è possibile modificare l'approccio alla programmazione da, "devo modificare qualcosa", a "è necessario produrre un nuovo valore".</span><span class="sxs-lookup"><span data-stu-id="aa5a1-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="aa5a1-194">Se ad esempio si aggiunge 1 a un valore, viene generato un nuovo valore, senza mutare quello esistente:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="aa5a1-195">In F#il codice seguente **non** modifica la funzione `value`. viene invece eseguito un controllo di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="aa5a1-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="aa5a1-196">Alcuni linguaggi di programmazione funzionale non supportano alcuna mutazione.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="aa5a1-197">In F#è supportato, ma non è il comportamento predefinito per i valori.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="aa5a1-198">Questo concetto si estende anche ulteriormente alle strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="aa5a1-199">Nella programmazione funzionale, le strutture di dati non modificabili, ad esempio set (e molti altri), hanno un'implementazione diversa da quella prevista inizialmente.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="aa5a1-200">Concettualmente, qualcosa come l'aggiunta di un elemento a un set non modifica il set, produce un _nuovo_ set con il valore aggiunto.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="aa5a1-201">Dietro le quinte, questa operazione viene spesso eseguita da una struttura di dati diversa che consente di tenere traccia di un valore in modo efficiente, in modo che sia possibile assegnare la rappresentazione appropriata dei dati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="aa5a1-202">Questo stile di utilizzo di valori e strutture di dati è fondamentale, in quanto impone di trattare qualsiasi operazione che modifica un elemento come se creasse una nuova versione di tale elemento.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="aa5a1-203">Ciò consente di verificare la coerenza tra uguaglianza e comparabilità nei programmi.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa5a1-204">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="aa5a1-204">Next steps</span></span>

<span data-ttu-id="aa5a1-205">Nella sezione successiva vengono illustrate in modo approfondito le funzioni, esplorando i diversi modi in cui è possibile usarle nella programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="aa5a1-206">[Funzioni di prima classe](first-class-functions.md) Esplora le funzioni in modo approfondito, mostrando come è possibile usarle in diversi contesti.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="aa5a1-207">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="aa5a1-207">Further reading</span></span>

<span data-ttu-id="aa5a1-208">La serie [funzionale Thinking](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) è un'altra risorsa ideale per apprendere la programmazione F#funzionale con.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="aa5a1-209">Vengono illustrati i concetti fondamentali della programmazione funzionale in modo pragmatico e di facile lettura, usando F# le funzionalità per illustrare i concetti.</span><span class="sxs-lookup"><span data-stu-id="aa5a1-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
