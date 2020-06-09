---
title: Funzioni
description: 'Informazioni sulle funzioni in F # e su come F # supporta i costrutti di programmazione funzionale comuni.'
ms.date: 05/16/2016
ms.openlocfilehash: e49183e0634dee1750757abadbfe9e9c824f51a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596474"
---
# <a name="functions"></a><span data-ttu-id="35134-103">Funzioni</span><span class="sxs-lookup"><span data-stu-id="35134-103">Functions</span></span>

<span data-ttu-id="35134-104">Le funzioni sono l'unità fondamentale di esecuzione di un programma in qualsiasi linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="35134-104">Functions are the fundamental unit of program execution in any programming language.</span></span> <span data-ttu-id="35134-105">Come negli altri linguaggi, una funzione F# ha un nome, può avere parametri e accettare argomenti e ha un corpo.</span><span class="sxs-lookup"><span data-stu-id="35134-105">As in other languages, an F# function has a name, can have parameters and take arguments, and has a body.</span></span> <span data-ttu-id="35134-106">F# supporta anche i costrutti di programmazione funzionale, ad esempio l'uso di funzioni come valori, l'uso di funzioni senza nome nelle espressioni, composizione di funzioni per creare nuove funzioni, funzioni sottoposte a currying e la definizione implicita di funzioni attraverso l'applicazione parziale di argomenti di funzioni.</span><span class="sxs-lookup"><span data-stu-id="35134-106">F# also supports functional programming constructs such as treating functions as values, using unnamed functions in expressions, composition of functions to form new functions, curried functions, and the implicit definition of functions by way of the partial application of function arguments.</span></span>

<span data-ttu-id="35134-107">Le funzioni vengono definite tramite la parole chiave `let` oppure, se la funzione è ricorsiva, tramite la combinazione di parole chiave `let rec`.</span><span class="sxs-lookup"><span data-stu-id="35134-107">You define functions by using the `let` keyword, or, if the function is recursive, the `let rec` keyword combination.</span></span>

## <a name="syntax"></a><span data-ttu-id="35134-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35134-108">Syntax</span></span>

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a><span data-ttu-id="35134-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35134-109">Remarks</span></span>

<span data-ttu-id="35134-110">*Function-name* (nome_funzione) è un identificatore che rappresenta la funzione.</span><span class="sxs-lookup"><span data-stu-id="35134-110">The *function-name* is an identifier that represents the function.</span></span> <span data-ttu-id="35134-111">*Parameter-list* (elenco_parametri) consiste di parametri successivi separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="35134-111">The *parameter-list* consists of successive parameters that are separated by spaces.</span></span> <span data-ttu-id="35134-112">È possibile specificare un tipo esplicito per ogni parametro, come illustrato nella sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="35134-112">You can specify an explicit type for each parameter, as described in the Parameters section.</span></span> <span data-ttu-id="35134-113">Se non si specifica un tipo di argomento specifico, il compilatore prova a dedurre il tipo dal corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="35134-113">If you do not specify a specific argument type, the compiler attempts to infer the type from the function body.</span></span> <span data-ttu-id="35134-114">*Function-body* (corpo_funzione) è costituito da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="35134-114">The *function-body* consists of an expression.</span></span> <span data-ttu-id="35134-115">L'espressione che costituisce il corpo della funzione è in genere un'espressione composta che consiste di un numero di espressioni che terminano con un'espressione finale, che è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="35134-115">The expression that makes up the function body is typically a compound expression consisting of a number of expressions that culminate in a final expression that is the return value.</span></span> <span data-ttu-id="35134-116">*Return-type* (tipo_restituito) è rappresentato dai due punti seguiti da un tipo ed è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="35134-116">The *return-type* is a colon followed by a type and is optional.</span></span> <span data-ttu-id="35134-117">Se non si specifica il tipo del valore restituito in modo esplicito, il compilatore determina il tipo restituito dall'espressione finale.</span><span class="sxs-lookup"><span data-stu-id="35134-117">If you do not specify the type of the return value explicitly, the compiler determines the return type from the final expression.</span></span>

<span data-ttu-id="35134-118">Una definizione di funzione semplice è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-118">A simple function definition resembles the following:</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="35134-119">Nell'esempio precedente, il nome della funzione è `f`, l'argomento è `x` ed è di tipo `int`, il corpo della funzione è `x + 1` e il valore restituito è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="35134-119">In the previous example, the function name is `f`, the argument is `x`, which has type `int`, the function body is `x + 1`, and the return value is of type `int`.</span></span>

<span data-ttu-id="35134-120">Le funzioni possono essere contrassegnate `inline`.</span><span class="sxs-lookup"><span data-stu-id="35134-120">Functions can be marked `inline`.</span></span> <span data-ttu-id="35134-121">Per informazioni su `inline`, vedere [Funzioni inline](inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="35134-121">For information about `inline`, see [Inline Functions](inline-functions.md).</span></span>

## <a name="scope"></a><span data-ttu-id="35134-122">Ambito</span><span class="sxs-lookup"><span data-stu-id="35134-122">Scope</span></span>

<span data-ttu-id="35134-123">A qualsiasi livello di ambito diverso dall'ambito del modulo, non è un errore riusare un nome di funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="35134-123">At any level of scope other than module scope, it is not an error to reuse a value or function name.</span></span> <span data-ttu-id="35134-124">Se si riusa un nome, il nome dichiarato successivamente sostituisce il nome dichiarato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="35134-124">If you reuse a name, the name declared later shadows the name declared earlier.</span></span> <span data-ttu-id="35134-125">Tuttavia, nell'ambito di livello superiore in un modulo, i nomi devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="35134-125">However, at the top level scope in a module, names must be unique.</span></span> <span data-ttu-id="35134-126">Ad esempio, il codice seguente genera un errore quando viene visualizzato nell'ambito del modulo, ma non quando viene visualizzato all'interno di una funzione:</span><span class="sxs-lookup"><span data-stu-id="35134-126">For example, the following code produces an error when it appears at module scope, but not when it appears inside a function:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

<span data-ttu-id="35134-127">Ma il codice seguente è accettabile a qualsiasi livello di ambito:</span><span class="sxs-lookup"><span data-stu-id="35134-127">But the following code is acceptable at any level of scope:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a><span data-ttu-id="35134-128">Parametri</span><span class="sxs-lookup"><span data-stu-id="35134-128">Parameters</span></span>

<span data-ttu-id="35134-129">I nomi dei parametri vengono elencati dopo il nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="35134-129">Names of parameters are listed after the function name.</span></span> <span data-ttu-id="35134-130">È possibile specificare un tipo per un parametro, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-130">You can specify a type for a parameter, as shown in the following example:</span></span>

```fsharp
let f (x : int) = x + 1
```

<span data-ttu-id="35134-131">Se si specifica un tipo, questo segue il nome del parametro ed è separato dal nome da due punti.</span><span class="sxs-lookup"><span data-stu-id="35134-131">If you specify a type, it follows the name of the parameter and is separated from the name by a colon.</span></span> <span data-ttu-id="35134-132">Se si omette il tipo per il parametro, questo viene dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="35134-132">If you omit the type for the parameter, the parameter type is inferred by the compiler.</span></span> <span data-ttu-id="35134-133">Ad esempio, nella definizione della funzione seguente, l'argomento `x` viene dedotto come tipo `int` perché 1 è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="35134-133">For example, in the following function definition, the argument `x` is inferred to be of type `int` because 1 is of type `int`.</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="35134-134">Tuttavia, il compilatore proverà a creare la funzione nel modo più generico possibile.</span><span class="sxs-lookup"><span data-stu-id="35134-134">However, the compiler will attempt to make the function as generic as possible.</span></span> <span data-ttu-id="35134-135">Ad esempio, si noti il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-135">For example, note the following code:</span></span>

```fsharp
let f x = (x, x)
```

<span data-ttu-id="35134-136">La funzione crea una tupla da un argomento di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="35134-136">The function creates a tuple from one argument of any type.</span></span> <span data-ttu-id="35134-137">Poiché il tipo non è specificato, la funzione può essere usata con qualsiasi tipo di argomento.</span><span class="sxs-lookup"><span data-stu-id="35134-137">Because the type is not specified, the function can be used with any argument type.</span></span> <span data-ttu-id="35134-138">Per altre informazioni, vedere [Generalizzazione automatica](../generics/automatic-generalization.md).</span><span class="sxs-lookup"><span data-stu-id="35134-138">For more information, see [Automatic Generalization](../generics/automatic-generalization.md).</span></span>

## <a name="function-bodies"></a><span data-ttu-id="35134-139">Corpi di funzioni</span><span class="sxs-lookup"><span data-stu-id="35134-139">Function Bodies</span></span>

<span data-ttu-id="35134-140">Un corpo di funzione può contenere definizioni di funzioni e variabili locali.</span><span class="sxs-lookup"><span data-stu-id="35134-140">A function body can contain definitions of local variables and functions.</span></span> <span data-ttu-id="35134-141">Tali funzioni e variabili rientrano nell'ambito del corpo della funzione corrente ma non al suo esterno.</span><span class="sxs-lookup"><span data-stu-id="35134-141">Such variables and functions are in scope in the body of the current function but not outside it.</span></span> <span data-ttu-id="35134-142">Dopo aver abilitato l'opzione di sintassi leggera, è necessario usare un rientro per indicare che una definizione è in un corpo della funzione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-142">When you have the lightweight syntax option enabled, you must use indentation to indicate that a definition is in a function body, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

<span data-ttu-id="35134-143">Per altre informazioni, vedere [Code Formatting Guidelines](../../style-guide/formatting.md) (Linee guida per la formattazione del codice) e [Verbose Syntax](../verbose-syntax.md) (Sintassi dettagliata).</span><span class="sxs-lookup"><span data-stu-id="35134-143">For more information, see [Code Formatting Guidelines](../../style-guide/formatting.md) and [Verbose Syntax](../verbose-syntax.md).</span></span>

## <a name="return-values"></a><span data-ttu-id="35134-144">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="35134-144">Return Values</span></span>

<span data-ttu-id="35134-145">Il compilatore usa l'espressione finale in un corpo di funzione per determinare il valore restituito e il tipo.</span><span class="sxs-lookup"><span data-stu-id="35134-145">The compiler uses the final expression in a function body to determine the return value and type.</span></span> <span data-ttu-id="35134-146">Il compilatore può dedurre il tipo dell'espressione finale dalle espressioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="35134-146">The compiler might infer the type of the final expression from previous expressions.</span></span> <span data-ttu-id="35134-147">Nella funzione `cylinderVolume`, come illustrato nella sezione precedente, il tipo di `pi` è determinato dal tipo di valore letterale `3.14159` come `float`.</span><span class="sxs-lookup"><span data-stu-id="35134-147">In the function `cylinderVolume`, shown in the previous section, the type of `pi` is determined from the type of the literal `3.14159` to be `float`.</span></span> <span data-ttu-id="35134-148">Per determinare il tipo dell'espressione `h * pi * r * r` come `float`, il compilatore usa il tipo di `pi`.</span><span class="sxs-lookup"><span data-stu-id="35134-148">The compiler uses the type of `pi` to determine the type of the expression `h * pi * r * r` to be `float`.</span></span> <span data-ttu-id="35134-149">Pertanto, il tipo restituito completo della funzione è `float`.</span><span class="sxs-lookup"><span data-stu-id="35134-149">Therefore, the overall return type of the function is `float`.</span></span>

<span data-ttu-id="35134-150">Per specificare in modo esplicito il valore restituito, scrivere il codice nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-150">To specify the return value explicitly, write the code as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

<span data-ttu-id="35134-151">Analogamente al codice scritto in precedenza, il compilatore applica **float** all'intera funzione; se si vuole applicarlo anche ai tipi di parametro, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-151">As the code is written above, the compiler applies **float** to the entire function; if you mean to apply it to the parameter types as well, use the following code:</span></span>

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a><span data-ttu-id="35134-152">Chiamata di una funzione</span><span class="sxs-lookup"><span data-stu-id="35134-152">Calling a Function</span></span>

<span data-ttu-id="35134-153">Le funzioni vengono chiamate specificando il nome della funzione seguito da uno spazio e quindi dagli argomenti separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="35134-153">You call functions by specifying the function name followed by a space and then any arguments separated by spaces.</span></span> <span data-ttu-id="35134-154">Ad esempio, per chiamare la funzione **cylinderVolume** e assegnare il risultato al valore **vol**, scrivere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-154">For example, to call the function **cylinderVolume** and assign the result to the value **vol**, you write the following code:</span></span>

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a><span data-ttu-id="35134-155">Applicazione parziale degli argomenti</span><span class="sxs-lookup"><span data-stu-id="35134-155">Partial Application of Arguments</span></span>

<span data-ttu-id="35134-156">Se si specifica un numero di argomenti inferiore al numero specificato, si crea una nuova funzione che prevedere gli argomenti rimanenti.</span><span class="sxs-lookup"><span data-stu-id="35134-156">If you supply fewer than the specified number of arguments, you create a new function that expects the remaining arguments.</span></span> <span data-ttu-id="35134-157">Questo metodo di gestione degli argomenti è detto *currying* ed è una caratteristica dei linguaggi di programmazione funzionale come F#.</span><span class="sxs-lookup"><span data-stu-id="35134-157">This method of handling arguments is referred to as *currying* and is a characteristic of functional programming languages like F#.</span></span> <span data-ttu-id="35134-158">Ad esempio, si supponga di usare due dimensioni per un tubo: una ha un raggio di **2** e l'altra ha un raggio di **3**.</span><span class="sxs-lookup"><span data-stu-id="35134-158">For example, suppose you are working with two sizes of pipe: one has a radius of **2.0** and the other has a radius of **3.0**.</span></span> <span data-ttu-id="35134-159">È possibile creare funzioni che determinano il volume del tubo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-159">You could create functions that determine the volume of pipe as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

<span data-ttu-id="35134-160">Verrà quindi specificato l'argomento aggiuntivo necessario per varie lunghezze del tubo delle due dimensioni diverse:</span><span class="sxs-lookup"><span data-stu-id="35134-160">You would then supply the additional argument as needed for various lengths of pipe of the two different sizes:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a><span data-ttu-id="35134-161">Funzioni ricorsive</span><span class="sxs-lookup"><span data-stu-id="35134-161">Recursive Functions</span></span>

<span data-ttu-id="35134-162">Le *funzioni ricorsive* sono funzioni che chiamano se stesse.</span><span class="sxs-lookup"><span data-stu-id="35134-162">*Recursive functions* are functions that call themselves.</span></span> <span data-ttu-id="35134-163">Richiedono di specificare la parola chiave **rec** seguita dalla parola chiave **let**.</span><span class="sxs-lookup"><span data-stu-id="35134-163">They require that you specify the **rec** keyword following the **let** keyword.</span></span> <span data-ttu-id="35134-164">È possibile richiamare la funzione ricorsiva dall'interno del corpo della funzione esattamente come si richiama qualsiasi chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="35134-164">Invoke the recursive function from within the body of the function just as you would invoke any function call.</span></span> <span data-ttu-id="35134-165">La funzione ricorsiva seguente calcola il numero *di Fibonacci*<sup>th</sup> .</span><span class="sxs-lookup"><span data-stu-id="35134-165">The following recursive function computes the *n*<sup>th</sup> Fibonacci number.</span></span> <span data-ttu-id="35134-166">La sequenza dei numeri di Fibonacci è nota dall'antichità ed è una sequenza in cui ogni numero successivo è la somma di due numeri precedenti nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="35134-166">The Fibonacci number sequence has been known since antiquity and is a sequence in which each successive number is the sum of the previous two numbers in the sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

<span data-ttu-id="35134-167">Alcune funzioni ricorsive potrebbero includere un overflow dello stack di programma o risultare inefficienti se non vengono scritte con cura e con tecniche speciali, come l'uso di accumulatori e continuazioni.</span><span class="sxs-lookup"><span data-stu-id="35134-167">Some recursive functions might overflow the program stack or perform inefficiently if you do not write them with care and with awareness of special techniques, such as the use of accumulators and continuations.</span></span>

## <a name="function-values"></a><span data-ttu-id="35134-168">Valori della funzione</span><span class="sxs-lookup"><span data-stu-id="35134-168">Function Values</span></span>

<span data-ttu-id="35134-169">In F#, tutte le funzioni sono considerate valori, e infatti sono note come *valori di funzione*.</span><span class="sxs-lookup"><span data-stu-id="35134-169">In F#, all functions are considered values; in fact, they are known as *function values*.</span></span> <span data-ttu-id="35134-170">Poiché le funzioni sono valori, possono essere usate come argomenti per altre funzioni o in altri contesti in cui vengono usati valori.</span><span class="sxs-lookup"><span data-stu-id="35134-170">Because functions are values, they can be used as arguments to other functions or in other contexts where values are used.</span></span> <span data-ttu-id="35134-171">Di seguito è incluso un esempio di una funzione che accetta un valore di funzione come argomento:</span><span class="sxs-lookup"><span data-stu-id="35134-171">Following is an example of a function that takes a function value as an argument:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

<span data-ttu-id="35134-172">Il tipo di valore di una funzione viene specificato usando il token `->`.</span><span class="sxs-lookup"><span data-stu-id="35134-172">You specify the type of a function value by using the `->` token.</span></span> <span data-ttu-id="35134-173">Sul lato sinistro di questo token si trova il tipo dell'argomento e sul lato destro si trova il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="35134-173">On the left side of this token is the type of the argument, and on the right side is the return value.</span></span> <span data-ttu-id="35134-174">Nell'esempio precedente, `apply1` è una funzione che accetta una funzione `transform` come argomento, in cui `transform` è una funzione che accetta un numero intero e restituisce un altro numero intero.</span><span class="sxs-lookup"><span data-stu-id="35134-174">In the previous example, `apply1` is a function that takes a function `transform` as an argument, where `transform` is a function that takes an integer and returns another integer.</span></span> <span data-ttu-id="35134-175">L'esempio di codice seguente illustra come usare `apply1`:</span><span class="sxs-lookup"><span data-stu-id="35134-175">The following code shows how to use `apply1`:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

<span data-ttu-id="35134-176">Il valore di `result` sarà 101 dopo l'esecuzione del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="35134-176">The value of `result` will be 101 after the previous code runs.</span></span>

<span data-ttu-id="35134-177">Più argomenti sono separati da token `->` successivi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-177">Multiple arguments are separated by successive `->` tokens, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

<span data-ttu-id="35134-178">Il risultato è 200.</span><span class="sxs-lookup"><span data-stu-id="35134-178">The result is 200.</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="35134-179">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="35134-179">Lambda Expressions</span></span>

<span data-ttu-id="35134-180">Un'*espressione lambda* è una funzione senza nome.</span><span class="sxs-lookup"><span data-stu-id="35134-180">A *lambda expression* is an unnamed function.</span></span> <span data-ttu-id="35134-181">Negli esempi precedenti, invece di definire le funzioni denominate **increment** e **mul**, è possibile usare espressioni lambda nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-181">In the previous examples, instead of defining named functions **increment** and **mul**, you could use lambda expressions as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

<span data-ttu-id="35134-182">Le espressioni lambda vengono definite usando la parola chiave `fun`.</span><span class="sxs-lookup"><span data-stu-id="35134-182">You define lambda expressions by using the `fun` keyword.</span></span> <span data-ttu-id="35134-183">Un'espressione lambda è simile a una definizione di funzione, con la differenza che al posto del token `=`, viene usato il token `->` per separare l'elenco di argomenti dal corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="35134-183">A lambda expression resembles a function definition, except that instead of the `=` token, the `->` token is used to separate the argument list from the function body.</span></span> <span data-ttu-id="35134-184">Analogamente a una definizione di funzione regolare, i tipi di argomenti possono essere dedotti o specificati in modo esplicito e il tipo restituito dell'espressione lambda viene dedotto dal tipo dell'ultima espressione nel corpo.</span><span class="sxs-lookup"><span data-stu-id="35134-184">As in a regular function definition, the argument types can be inferred or specified explicitly, and the return type of the lambda expression is inferred from the type of the last expression in the body.</span></span> <span data-ttu-id="35134-185">Per altre informazioni, vedere [Espressioni lambda: parola chiave `fun`](lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="35134-185">For more information, see [Lambda Expressions: The `fun` Keyword](lambda-expressions-the-fun-keyword.md).</span></span>

## <a name="function-composition-and-pipelining"></a><span data-ttu-id="35134-186">Composizione di funzioni e pipelining</span><span class="sxs-lookup"><span data-stu-id="35134-186">Function Composition and Pipelining</span></span>

<span data-ttu-id="35134-187">Le funzioni in F# possono essere composte da altre funzioni.</span><span class="sxs-lookup"><span data-stu-id="35134-187">Functions in F# can be composed from other functions.</span></span> <span data-ttu-id="35134-188">La composizione di due funzioni, **funzione1** e **funzione2**, è un'altra funzione che rappresenta l'applicazione di **funzione1** seguita dall'applicazione di **funzione2**:</span><span class="sxs-lookup"><span data-stu-id="35134-188">The composition of two functions **function1** and **function2** is another function that represents the application of **function1** followed the application of **function2**:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

<span data-ttu-id="35134-189">Il risultato è 202.</span><span class="sxs-lookup"><span data-stu-id="35134-189">The result is 202.</span></span>

<span data-ttu-id="35134-190">Il pipelining consente alle chiamate di funzioni di essere concatenate come operazioni successive.</span><span class="sxs-lookup"><span data-stu-id="35134-190">Pipelining enables function calls to be chained together as successive operations.</span></span> <span data-ttu-id="35134-191">Il pipelining funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="35134-191">Pipelining works as follows:</span></span>

```fsharp
let result = 100 |> function1 |> function2
```

<span data-ttu-id="35134-192">Il risultato è di nuovo 202.</span><span class="sxs-lookup"><span data-stu-id="35134-192">The result is again 202.</span></span>

<span data-ttu-id="35134-193">Gli operatori di composizione accettano due funzioni e restituiscono una funzione; al contrario, gli operatori pipeline accettano una funzione e un argomento e restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="35134-193">The composition operators take two functions and return a function; by contrast, the pipeline operators take a function and an argument and return a value.</span></span> <span data-ttu-id="35134-194">L'esempio di codice seguente illustra la differenza tra gli operatori di pipeline e di composizione visualizzando le differenze nelle firme di funzione e nell'uso.</span><span class="sxs-lookup"><span data-stu-id="35134-194">The following code example shows the difference between the pipeline and composition operators by showing the differences in the function signatures and usage.</span></span>

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a><span data-ttu-id="35134-195">Overload delle funzioni</span><span class="sxs-lookup"><span data-stu-id="35134-195">Overloading Functions</span></span>

<span data-ttu-id="35134-196">È possibile eseguire l'overload di metodi di un tipo, ma non di funzioni.</span><span class="sxs-lookup"><span data-stu-id="35134-196">You can overload methods of a type but not functions.</span></span> <span data-ttu-id="35134-197">Per altre informazioni, vedere [Metodi](../members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="35134-197">For more information, see [Methods](../members/methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35134-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35134-198">See also</span></span>

- [<span data-ttu-id="35134-199">Valori</span><span class="sxs-lookup"><span data-stu-id="35134-199">Values</span></span>](../values/index.md)
- [<span data-ttu-id="35134-200">Riferimenti per il linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="35134-200">F# Language Reference</span></span>](../index.md)
