---
title: Funzioni come valori di prima classe (F#)
description: Informazioni su come le funzioni vengono elevate per stato di prima classe nel linguaggio di programmazione c#.
ms.date: 05/16/2016
ms.openlocfilehash: cccff5fcf9de150da26422f80cae032ddf21014c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566665"
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="81747-103">Funzioni come valori di prima classe</span><span class="sxs-lookup"><span data-stu-id="81747-103">Functions as First-Class Values</span></span>

<span data-ttu-id="81747-104">Una caratteristica di definizione dei linguaggi di programmazione funzionale è l'elevazione delle funzioni di stato di prima classe.</span><span class="sxs-lookup"><span data-stu-id="81747-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="81747-105">Dovrebbe essere possibile eseguire con una funzione qualsiasi è possibile eseguire con i valori degli altri tipi predefiniti e in grado di farlo con un livello di impegno confrontabile.</span><span class="sxs-lookup"><span data-stu-id="81747-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="81747-106">Di seguito sono elencate le misure tipiche dello stato di prima classe:</span><span class="sxs-lookup"><span data-stu-id="81747-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="81747-107">È possibile associare funzioni di identificatori</span><span class="sxs-lookup"><span data-stu-id="81747-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="81747-108">Vale a dire può garantirvi nomi?</span><span class="sxs-lookup"><span data-stu-id="81747-108">That is, can you give them names?</span></span>

- <span data-ttu-id="81747-109">È possibile archiviare funzioni nelle strutture dei dati, ad esempio in un elenco?</span><span class="sxs-lookup"><span data-stu-id="81747-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="81747-110">È possibile passare una funzione come argomento in una chiamata di funzione?</span><span class="sxs-lookup"><span data-stu-id="81747-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="81747-111">È possibile restituire una funzione da una chiamata di funzione</span><span class="sxs-lookup"><span data-stu-id="81747-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="81747-112">Le ultime due misure definiscono i cosiddetti *operazioni di ordine superiore* o *funzioni di ordine superiore*.</span><span class="sxs-lookup"><span data-stu-id="81747-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="81747-113">Funzioni di ordine superiore accettano funzioni come argomenti e restituiscono funzioni come il valore delle chiamate di funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="81747-114">Queste operazioni supportano fondamenti della programmazione funzionale come mapping di funzioni e composizione di funzioni.</span><span class="sxs-lookup"><span data-stu-id="81747-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>


## <a name="give-the-value-a-name"></a><span data-ttu-id="81747-115">Assegnare il valore di un nome</span><span class="sxs-lookup"><span data-stu-id="81747-115">Give the Value a Name</span></span>

<span data-ttu-id="81747-116">Se una funzione è un valore di prima classe, è necessario essere in grado di assegnare un nome, così come è possibile assegnare valori integer, stringhe e altri tipi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="81747-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="81747-117">Si parla nella documentazione di programmazione funzionale come associazione di un identificatore a un valore.</span><span class="sxs-lookup"><span data-stu-id="81747-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="81747-118">F # utilizza [ `let` associazioni](../language-reference/functions/let-bindings.md) per associare i nomi ai valori: `let <identifier> = <value>`.</span><span class="sxs-lookup"><span data-stu-id="81747-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="81747-119">Il codice riportato di seguito sono illustrati due esempi.</span><span class="sxs-lookup"><span data-stu-id="81747-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="81747-120">È possibile denominare una funzione altrettanto facilmente.</span><span class="sxs-lookup"><span data-stu-id="81747-120">You can name a function just as easily.</span></span> <span data-ttu-id="81747-121">Nell'esempio seguente viene definita una funzione denominata `squareIt` associando l'identificatore `squareIt` per il [espressione lambda](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="81747-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="81747-122">Funzione `squareIt` dispone di un parametro `n`, e restituisce il quadrato di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="81747-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="81747-123">F # offre quanto segue sintassi più concisa per ottenere lo stesso risultato con meno digitazione.</span><span class="sxs-lookup"><span data-stu-id="81747-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="81747-124">Gli esempi che seguono per lo più utilizzano il primo stile, `let <function-name> = <lambda-expression>`, per evidenziare le analogie tra la dichiarazione di funzioni e la dichiarazione di altri tipi di valori.</span><span class="sxs-lookup"><span data-stu-id="81747-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="81747-125">Tuttavia, tutte le funzioni denominate possono essere scritti con la sintassi concisa.</span><span class="sxs-lookup"><span data-stu-id="81747-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="81747-126">Alcuni degli esempi sono scritti in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="81747-126">Some of the examples are written in both ways.</span></span>


## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="81747-127">Archiviare il valore in una struttura di dati</span><span class="sxs-lookup"><span data-stu-id="81747-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="81747-128">Un valore di prima classe può essere archiviato in una struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="81747-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="81747-129">Il codice seguente mostra esempi in cui archiviano i valori negli elenchi e Tuple.</span><span class="sxs-lookup"><span data-stu-id="81747-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="81747-130">Per verificare che il nome di una funzione archiviato in una tupla in realtà restituisce una funzione, l'esempio seguente usa il `fst` e `snd` operatori per estrarre il primo e secondo elemento da tupla `funAndArgTuple`.</span><span class="sxs-lookup"><span data-stu-id="81747-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="81747-131">Il primo elemento nella tupla è `squareIt` e il secondo elemento è `num`.</span><span class="sxs-lookup"><span data-stu-id="81747-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="81747-132">Identificatore `num` è associato in un esempio precedente all'intero 10, un argomento valido per il `squareIt` (funzione).</span><span class="sxs-lookup"><span data-stu-id="81747-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="81747-133">La seconda espressione applica il primo elemento nella tupla al secondo elemento nella tupla: `squareIt num`.</span><span class="sxs-lookup"><span data-stu-id="81747-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="81747-134">Analogamente, come identificatore `num` e intero 10 può essere utilizzato in modo intercambiabile, in tal caso è possibile identificatore `squareIt` e l'espressione lambda `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="81747-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="81747-135">Passare il valore come argomento</span><span class="sxs-lookup"><span data-stu-id="81747-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="81747-136">Se un valore ha lo stato di prima classe in una lingua, è possibile passare come argomento a una funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="81747-137">Ad esempio, è pratica comune passare interi e stringhe come argomenti.</span><span class="sxs-lookup"><span data-stu-id="81747-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="81747-138">Il codice seguente mostra i numeri interi e stringhe passate come argomenti in F #.</span><span class="sxs-lookup"><span data-stu-id="81747-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="81747-139">Se lo stato di prima classe dispone di funzioni, è necessario essere in grado di passati come argomenti allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="81747-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="81747-140">Tenere presente che questa è la prima caratteristica delle funzioni di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="81747-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="81747-141">Nell'esempio seguente, la funzione `applyIt` presenta due parametri, `op` e `arg`.</span><span class="sxs-lookup"><span data-stu-id="81747-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="81747-142">Se si invia una funzione che dispone di un parametro per `op` e un argomento appropriato per la funzione `arg`, la funzione restituisce il risultato dell'applicazione `op` a `arg`.</span><span class="sxs-lookup"><span data-stu-id="81747-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="81747-143">Nell'esempio seguente, l'argomento della funzione sia l'argomento integer vengono inviati nello stesso modo, tramite i relativi nomi.</span><span class="sxs-lookup"><span data-stu-id="81747-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="81747-144">La possibilità di inviare una funzione come argomento a un'altra funzione sottostante astrazioni comuni nei linguaggi di programmazione funzionale, ad esempio operazioni mappa o un filtro.</span><span class="sxs-lookup"><span data-stu-id="81747-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="81747-145">Un'operazione di mapping, ad esempio, è una funzione di ordine superiore che acquisisce il calcolo condiviso dalle funzioni che scorrere un elenco, eseguono un'operazione su ogni elemento e quindi restituiscono un elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="81747-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="81747-146">È possibile incrementare ogni elemento in un elenco di numeri interi, o al quadrato di ogni elemento o per modificare ogni elemento in un elenco di stringhe in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="81747-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="81747-147">La parte soggetta a errori di calcolo è il processo ricorsivo che scorre l'elenco e compila un elenco di risultati da restituire.</span><span class="sxs-lookup"><span data-stu-id="81747-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="81747-148">Tale parte viene acquisita nella funzione di mapping.</span><span class="sxs-lookup"><span data-stu-id="81747-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="81747-149">È necessario scrivere per una particolare applicazione è la funzione che si desidera applicare singolarmente a ogni elemento di elenco (aggiunta, elevazione al quadrato, modificare maiuscole e minuscole).</span><span class="sxs-lookup"><span data-stu-id="81747-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="81747-150">Che funzione viene inviata come argomento alla funzione di mapping, proprio come `squareIt` viene inviato a `applyIt` nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="81747-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="81747-151">F # fornisce metodi di mapping per la maggior parte dei tipi di raccolta, tra cui [Elenca](../language-reference/lists.md), [matrici](../language-reference/arrays.md), e [sequenze](../language-reference/sequences.md).</span><span class="sxs-lookup"><span data-stu-id="81747-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="81747-152">L'esempio seguente usa gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="81747-152">The following examples use lists.</span></span> <span data-ttu-id="81747-153">La sintassi è `List.map <the function> <the list>`.</span><span class="sxs-lookup"><span data-stu-id="81747-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="81747-154">Per ulteriori informazioni, vedere [Elenca](../language-reference/lists.md).</span><span class="sxs-lookup"><span data-stu-id="81747-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="81747-155">Il valore restituito da una chiamata di funzione</span><span class="sxs-lookup"><span data-stu-id="81747-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="81747-156">Infine, se lo stato di prima classe dispone di una funzione in una lingua, è necessario essere in grado di restituire il valore di una chiamata di funzione, la esattamente come si restituiscono altri tipi, ad esempio numeri interi e stringhe.</span><span class="sxs-lookup"><span data-stu-id="81747-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="81747-157">Chiamate di funzione seguenti restituiscono valori integer e visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="81747-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="81747-158">La chiamata di funzione seguente restituisce una stringa.</span><span class="sxs-lookup"><span data-stu-id="81747-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="81747-159">La seguente chiamata di funzione, dichiarate inline, restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="81747-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="81747-160">Il valore visualizzato è `True`.</span><span class="sxs-lookup"><span data-stu-id="81747-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="81747-161">La possibilità di restituire una funzione come valore di una chiamata di funzione è la seconda caratteristica delle funzioni di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="81747-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="81747-162">Nell'esempio seguente, `checkFor` viene definito come una funzione che accetta un solo argomento, `item`e restituisce una nuova funzione come relativo valore.</span><span class="sxs-lookup"><span data-stu-id="81747-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="81747-163">La funzione restituita accetta un elenco come argomento, `lst`e Cerca `item` in `lst`.</span><span class="sxs-lookup"><span data-stu-id="81747-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="81747-164">Se `item` è presente, la funzione restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="81747-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="81747-165">Se `item` non è presente, la funzione restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="81747-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="81747-166">Come nella sezione precedente, il codice seguente utilizza una funzione di elenco fornito, [List. exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), la ricerca nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="81747-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="81747-167">Il codice seguente usa `checkFor` per creare una nuova funzione che accetta un argomento, un elenco e cerca 7 nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="81747-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="81747-168">Nell'esempio seguente viene utilizzato lo stato di prima classe delle funzioni in F # per dichiarare una funzione, `compose`, che restituisce una composizione di due argomenti di funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
<span data-ttu-id="81747-169">Per una versione ancora più breve, vedere la sezione seguente, "Funzioni sottoposte a currying."</span><span class="sxs-lookup"><span data-stu-id="81747-169">For an even shorter version, see the following section, "Curried Functions."</span></span>


<span data-ttu-id="81747-170">Il codice seguente invia due funzioni come argomenti `compose`, entrambi di che accettano un solo argomento dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="81747-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="81747-171">Il valore restituito è una nuova funzione che è una composizione di due argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
<span data-ttu-id="81747-172">F # fornisce due operatori, `<<` e `>>`, che consente di combinare funzioni.</span><span class="sxs-lookup"><span data-stu-id="81747-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="81747-173">Ad esempio, `let squareAndDouble2 = doubleIt << squareIt` equivale a `let squareAndDouble = compose doubleIt squareIt` nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="81747-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="81747-174">L'esempio seguente di restituzione di una funzione come valore di una chiamata di funzione crea un semplice gioco di individuazione.</span><span class="sxs-lookup"><span data-stu-id="81747-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="81747-175">Per creare un gioco, chiamare `makeGame` con il valore desiderato da individuare inviato per `target`.</span><span class="sxs-lookup"><span data-stu-id="81747-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="81747-176">Il valore restituito dalla funzione `makeGame` è una funzione che accetta un argomento, la proposta e segnala se il valore indicato è corretto.</span><span class="sxs-lookup"><span data-stu-id="81747-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="81747-177">Il codice seguente chiama `makeGame`, inviare il valore `7` per `target`.</span><span class="sxs-lookup"><span data-stu-id="81747-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="81747-178">Identificatore `playGame` è associata all'espressione lambda restituita.</span><span class="sxs-lookup"><span data-stu-id="81747-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="81747-179">Pertanto, `playGame` è una funzione che accetta come unico argomento un valore per `guess`.</span><span class="sxs-lookup"><span data-stu-id="81747-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a><span data-ttu-id="81747-180">Funzioni sottoposte a currying</span><span class="sxs-lookup"><span data-stu-id="81747-180">Curried Functions</span></span>

<span data-ttu-id="81747-181">Molti degli esempi nella sezione precedente possono essere scritti in modo più conciso sfruttando l'operatore implicito *currying* nelle dichiarazioni di funzione F #.</span><span class="sxs-lookup"><span data-stu-id="81747-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="81747-182">Currying è un processo di trasformazione di una funzione che ha più di un parametro in una serie di funzioni incorporate, ognuna delle quali presenta un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="81747-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="81747-183">In F #, le funzioni contenenti più di un parametro sono intrinsecamente sottoposte a currying.</span><span class="sxs-lookup"><span data-stu-id="81747-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="81747-184">Ad esempio, `compose` della sezione precedente può essere scritta come mostrato nella seguente stile conciso, con tre parametri.</span><span class="sxs-lookup"><span data-stu-id="81747-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="81747-185">Tuttavia, il risultato è una funzione di un parametro che restituisce una funzione di un parametro che a sua volta restituisce un'altra funzione di un parametro, come illustrato nella `compose4curried`.</span><span class="sxs-lookup"><span data-stu-id="81747-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="81747-186">È possibile accedere a questa funzione in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="81747-186">You can access this function in several ways.</span></span> <span data-ttu-id="81747-187">Ognuno degli esempi seguenti restituito di 18.</span><span class="sxs-lookup"><span data-stu-id="81747-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="81747-188">È possibile sostituire `compose4` con `compose4curried` in uno degli esempi.</span><span class="sxs-lookup"><span data-stu-id="81747-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="81747-189">Per verificare che la funzione continui a funzionare come in precedenza, provare di nuovo i test case originali.</span><span class="sxs-lookup"><span data-stu-id="81747-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
<span data-ttu-id="81747-190">È possibile limitare il currying racchiudendo le tuple parametri.</span><span class="sxs-lookup"><span data-stu-id="81747-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="81747-191">Per ulteriori informazioni, vedere "Parametro modelli" nella [parametri e argomenti](../language-reference/parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="81747-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="81747-192">Nell'esempio seguente viene utilizzato il currying implicito per scrivere una versione più breve di `makeGame`.</span><span class="sxs-lookup"><span data-stu-id="81747-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="81747-193">I dettagli di `makeGame` crea e restituisce il `game` funzione sono meno espliciti in questo formato, ma è possibile verificare tramite i test case originali che il risultato è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="81747-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="81747-194">Per ulteriori informazioni sul currying, vedere "Applicazione parziale di argomenti" in [funzioni](../language-reference/functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="81747-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>


## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="81747-195">Identificatore e definizione di funzione sono intercambiabili</span><span class="sxs-lookup"><span data-stu-id="81747-195">Identifier and Function Definition Are Interchangeable</span></span>
<span data-ttu-id="81747-196">Il nome della variabile `num` nella precedente esempi restituisce l'intero 10 e non sorprende quello in `num` è valido, 10 sia valido.</span><span class="sxs-lookup"><span data-stu-id="81747-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="81747-197">Lo stesso vale per gli identificatori di funzione e i relativi valori: ovunque può essere utilizzato il nome della funzione, l'espressione lambda a cui è associato è utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="81747-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="81747-198">L'esempio seguente definisce un `Boolean` funzione chiamata `isNegative`e quindi viene utilizzato il nome della funzione e la definizione della funzione in modo intercambiabile.</span><span class="sxs-lookup"><span data-stu-id="81747-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="81747-199">I tre esempi successivi viene sempre restituito e visualizzato `False`.</span><span class="sxs-lookup"><span data-stu-id="81747-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="81747-200">Per eseguire un'ulteriore è un unico passaggio, sostituire il valore che `applyIt` è associato a per `applyIt`.</span><span class="sxs-lookup"><span data-stu-id="81747-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="81747-201">Le funzioni sono valori di prima classe in F #</span><span class="sxs-lookup"><span data-stu-id="81747-201">Functions Are First-Class Values in F#</span></span> #

<span data-ttu-id="81747-202">Negli esempi nelle sezioni precedenti viene illustrato che funzioni in F # soddisfano i criteri per essere considerate valori in F #:</span><span class="sxs-lookup"><span data-stu-id="81747-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="81747-203">È possibile associare un identificatore per una definizione di funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="81747-204">È possibile archiviare una funzione in una struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="81747-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="81747-205">È possibile passare una funzione come argomento.</span><span class="sxs-lookup"><span data-stu-id="81747-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="81747-206">È possibile restituire una funzione come valore di una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="81747-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="81747-207">Per ulteriori informazioni su F #, vedere il [riferimenti al linguaggio F #](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="81747-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="81747-208">Esempio</span><span class="sxs-lookup"><span data-stu-id="81747-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="81747-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81747-209">Description</span></span>

<span data-ttu-id="81747-210">Il codice seguente contiene tutti gli esempi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="81747-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="81747-211">Codice</span><span class="sxs-lookup"><span data-stu-id="81747-211">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a><span data-ttu-id="81747-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81747-212">See Also</span></span>

[<span data-ttu-id="81747-213">Elenchi</span><span class="sxs-lookup"><span data-stu-id="81747-213">Lists</span></span>](../language-reference/lists.md)

[<span data-ttu-id="81747-214">Tuple</span><span class="sxs-lookup"><span data-stu-id="81747-214">Tuples</span></span>](../language-reference/tuples.md)

[<span data-ttu-id="81747-215">Funzioni</span><span class="sxs-lookup"><span data-stu-id="81747-215">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="81747-216">`let` Associazioni</span><span class="sxs-lookup"><span data-stu-id="81747-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)

[<span data-ttu-id="81747-217">Espressioni lambda: I `fun` (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="81747-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
