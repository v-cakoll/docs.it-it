---
title: Parametri e argomenti (F#)
description: 'Informazioni sul supporto del linguaggio F # per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e146ec4e877bb89f10e2f3daad2d8356c29fa81f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="247fa-103">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="247fa-103">Parameters and Arguments</span></span>

<span data-ttu-id="247fa-104">In questo argomento viene descritto il supporto lingua per la definizione dei parametri e il passaggio di argomenti a funzioni, metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="247fa-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="247fa-105">Sono incluse informazioni su come passare per riferimento e come definire e utilizzare i metodi che possono accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="247fa-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="247fa-106">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="247fa-106">Parameters and Arguments</span></span>
<span data-ttu-id="247fa-107">Il termine *parametro* viene utilizzato per descrivere i nomi per i valori che devono essere forniti.</span><span class="sxs-lookup"><span data-stu-id="247fa-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="247fa-108">Il termine *argomento* viene utilizzato per i valori forniti per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="247fa-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="247fa-109">Parametri possono essere specificati in tupla o a currying, o in una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="247fa-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="247fa-110">È possibile passare argomenti tramite un nome di parametro espliciti.</span><span class="sxs-lookup"><span data-stu-id="247fa-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="247fa-111">I parametri dei metodi possono essere specificati come facoltativi e assegnati un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="247fa-111">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="247fa-112">Modelli di parametri</span><span class="sxs-lookup"><span data-stu-id="247fa-112">Parameter Patterns</span></span>
<span data-ttu-id="247fa-113">I parametri specificati per le funzioni e metodi sono in genere, separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="247fa-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="247fa-114">Ciò significa che, in sostanza, uno dei modelli descritti in [espressioni Match](match-expressions.md) può essere utilizzato in un elenco di parametri per una funzione o membro.</span><span class="sxs-lookup"><span data-stu-id="247fa-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="247fa-115">I metodi usano in genere la forma di tupla di passaggio di argomenti.</span><span class="sxs-lookup"><span data-stu-id="247fa-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="247fa-116">Questo consente di ottenere un risultato più chiaro dalla prospettiva di altri linguaggi .NET perché il formato tupla corrisponde il modo in cui gli argomenti vengono passati nei metodi .NET.</span><span class="sxs-lookup"><span data-stu-id="247fa-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="247fa-117">Il modulo sottoposte a currying viene generalmente utilizzato con funzioni create tramite `let` associazioni.</span><span class="sxs-lookup"><span data-stu-id="247fa-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="247fa-118">Nello pseudocodice seguente vengono illustrati esempi di tupla e argomenti sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="247fa-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="247fa-119">Form combinato sono possibili quando alcuni argomenti sono tuple e altri non lo sono.</span><span class="sxs-lookup"><span data-stu-id="247fa-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="247fa-120">Altri modelli possono essere utilizzati anche negli elenchi di parametri, ma se il modello di parametri non corrisponde a tutti i possibili input, potrebbe esserci una corrispondenza incompleta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="247fa-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="247fa-121">L'eccezione `MatchFailureException` viene generato quando il valore di un argomento non corrisponde ai modelli specificati nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="247fa-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="247fa-122">Il compilatore genera un avviso quando un modello di parametri consente corrispondenze incomplete.</span><span class="sxs-lookup"><span data-stu-id="247fa-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="247fa-123">Almeno un altro modello è in genere utile per gli elenchi di parametri, ovvero il carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="247fa-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="247fa-124">Utilizzare il carattere jolly in un elenco di parametri quando si desidera semplicemente ignorare tutti gli argomenti forniti.</span><span class="sxs-lookup"><span data-stu-id="247fa-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="247fa-125">Il codice seguente viene illustrato l'utilizzo del modello in un elenco di argomenti con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="247fa-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="247fa-126">Il carattere jolly può essere utile quando gli argomenti passati non è necessario, ad esempio il punto di ingresso principale per un programma, quando non si è interessati negli argomenti della riga di comando che vengono generalmente forniti come matrice di stringhe, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="247fa-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="247fa-127">Altri modelli talvolta utilizzati negli argomenti sono di `as` modello e i modelli di identificatori associati unioni discriminate e i criteri attivi.</span><span class="sxs-lookup"><span data-stu-id="247fa-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="247fa-128">È possibile utilizzare il modello di unione discriminata singolo case, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="247fa-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="247fa-129">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="247fa-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="247fa-130">Criteri attivi possono risultare utili come parametri, ad esempio, durante la trasformazione di un argomento in un formato desiderato, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="247fa-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="247fa-131">È possibile utilizzare il `as` modello per archiviare un valore corrispondente come un valore locale, come illustrato nella seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="247fa-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="247fa-132">Un altro modello utilizzato in alcuni casi è una funzione che lascia l'ultimo argomento senza nome fornendo, come il corpo della funzione, un'espressione lambda che esegue immediatamente i criteri di ricerca per l'argomento implicito.</span><span class="sxs-lookup"><span data-stu-id="247fa-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="247fa-133">Un esempio di questa è la seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="247fa-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="247fa-134">Questo codice definisce una funzione che accetta un elenco generico e restituisce `true` se l'elenco è vuoto, e `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="247fa-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="247fa-135">L'utilizzo di tali tecniche può rendere più difficile da leggere codice.</span><span class="sxs-lookup"><span data-stu-id="247fa-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="247fa-136">In alcuni casi, i modelli che comportano corrispondenze incomplete sono utili, ad esempio, se si sa che gli elenchi nel programma dispongono solo di tre elementi, è possibile utilizzare un modello simile al seguente in un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="247fa-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="247fa-137">Uso di criteri di corrispondenza incompleti è ideale per la creazione rapida di prototipi e altri utilizzi temporanei.</span><span class="sxs-lookup"><span data-stu-id="247fa-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="247fa-138">Il compilatore emetterà un avviso per tale codice.</span><span class="sxs-lookup"><span data-stu-id="247fa-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="247fa-139">Tali modelli non possono coprire nel caso generale di tutti i possibili input e pertanto non sono adatti per le API dei componenti.</span><span class="sxs-lookup"><span data-stu-id="247fa-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="247fa-140">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="247fa-140">Named Arguments</span></span>
<span data-ttu-id="247fa-141">Argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitato da virgole, o può essere passati in modo esplicito a un metodo, fornendo il nome, seguito da un segno di uguale e il valore deve essere passato.</span><span class="sxs-lookup"><span data-stu-id="247fa-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="247fa-142">Se specificato, fornendo il nome, possono essere visualizzati in un ordine diverso da quello utilizzato nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="247fa-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="247fa-143">Argomenti denominati possono rendere il codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="247fa-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="247fa-144">Argomenti denominati sono consentiti solo per metodi, non per `let`-associati valori di funzione, funzioni o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="247fa-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="247fa-145">Esempio di codice seguente viene illustrato l'utilizzo di argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="247fa-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="247fa-146">In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe utilizzando una sintassi simile a quella degli argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="247fa-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="247fa-147">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="247fa-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="247fa-148">Per ulteriori informazioni, vedere [costruttori (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="247fa-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="247fa-149">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="247fa-149">Optional Parameters</span></span>
<span data-ttu-id="247fa-150">È possibile specificare un parametro facoltativo per un metodo con un punto interrogativo davanti al nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="247fa-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="247fa-151">Parametri facoltativi vengono interpretati come il tipo di opzione F #, pertanto è possibile eseguire le query in modo regolare che i tipi di opzioni vengono eseguite query sulle, utilizzando un `match` espressione con `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="247fa-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="247fa-152">Parametri facoltativi sono consentiti solo per i membri, non nelle funzioni create tramite `let` associazioni.</span><span class="sxs-lookup"><span data-stu-id="247fa-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="247fa-153">È inoltre possibile utilizzare una funzione `defaultArg`, che imposta un valore predefinito di un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="247fa-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="247fa-154">Il `defaultArg` funzione accetta il parametro facoltativo come primo argomento e il valore predefinito come il secondo.</span><span class="sxs-lookup"><span data-stu-id="247fa-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="247fa-155">Nell'esempio seguente viene illustrato l'utilizzo di parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="247fa-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="247fa-156">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="247fa-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="247fa-157">Il passaggio per riferimento</span><span class="sxs-lookup"><span data-stu-id="247fa-157">Passing by Reference</span></span>
<span data-ttu-id="247fa-158">F # supporta la `byref` (parola chiave), che specifica che un parametro viene passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="247fa-158">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="247fa-159">Questo significa che qualsiasi modifica del valore venga mantenute dopo l'esecuzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="247fa-159">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="247fa-160">I valori forniti per un `byref` parametro deve essere modificabile.</span><span class="sxs-lookup"><span data-stu-id="247fa-160">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="247fa-161">In alternativa, è possibile passare le celle di riferimento del tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="247fa-161">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="247fa-162">Il passaggio per riferimento nei linguaggi .NET che si è evoluto come un modo per restituire più valori da una funzione.</span><span class="sxs-lookup"><span data-stu-id="247fa-162">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="247fa-163">In F #, è possibile restituire una tupla a questo scopo, o utilizzare una cella di riferimento modificabile come parametro.</span><span class="sxs-lookup"><span data-stu-id="247fa-163">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="247fa-164">Il `byref` parametro viene fornito principalmente per l'interoperabilità con le librerie .NET.</span><span class="sxs-lookup"><span data-stu-id="247fa-164">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="247fa-165">Nell'esempio seguente viene illustrato l'utilizzo del `byref` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="247fa-165">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="247fa-166">Si noti che quando si utilizza una cella di riferimento come parametro, è necessario creare una cella di riferimento come un valore denominato e utilizzarlo come parametro, non è sufficiente aggiungere il `ref` operatore, come illustrato nella prima chiamata a `Increment` nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="247fa-166">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="247fa-167">Poiché la creazione di una cella di riferimento, viene creata una copia del valore sottostante, la prima chiamata incrementa semplicemente un valore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="247fa-167">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="247fa-168">È possibile utilizzare una tupla come valore restituito per archiviare qualsiasi `out` parametri nei metodi della libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="247fa-168">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="247fa-169">In alternativa, è possibile trattare il `out` parametro come un `byref` parametro.</span><span class="sxs-lookup"><span data-stu-id="247fa-169">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="247fa-170">Esempio di codice seguente viene illustrata in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="247fa-170">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="247fa-171">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="247fa-171">Parameter Arrays</span></span>
<span data-ttu-id="247fa-172">In alcuni casi è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo.</span><span class="sxs-lookup"><span data-stu-id="247fa-172">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="247fa-173">Non sarebbe pratico creare tutti i possibili metodi di overload per l'account per tutti i tipi che può essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="247fa-173">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="247fa-174">Le implementazioni .NET forniscono supporto per tali metodi tramite la funzionalità di parametro matrice.</span><span class="sxs-lookup"><span data-stu-id="247fa-174">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="247fa-175">Un metodo che accetta una matrice di parametri nella firma può essere fornito con un numero arbitrario di parametri.</span><span class="sxs-lookup"><span data-stu-id="247fa-175">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="247fa-176">I parametri vengono inseriti in una matrice.</span><span class="sxs-lookup"><span data-stu-id="247fa-176">The parameters are put into an array.</span></span> <span data-ttu-id="247fa-177">Il tipo degli elementi della matrice determina i tipi di parametro che possono essere passati alla funzione.</span><span class="sxs-lookup"><span data-stu-id="247fa-177">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="247fa-178">Se si definisce la matrice di parametri con `System.Object` come tipo di elemento, quindi il codice client può passare i valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="247fa-178">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="247fa-179">In F #, matrici di parametro possono essere definite solo nei metodi.</span><span class="sxs-lookup"><span data-stu-id="247fa-179">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="247fa-180">Non possono essere utilizzate in funzioni che sono definite nei moduli o funzioni autonome.</span><span class="sxs-lookup"><span data-stu-id="247fa-180">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="247fa-181">Per definire una matrice di parametri, utilizzare il `ParamArray` attributo.</span><span class="sxs-lookup"><span data-stu-id="247fa-181">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="247fa-182">Il `ParamArray` attributo può essere applicato solo all'ultimo parametro.</span><span class="sxs-lookup"><span data-stu-id="247fa-182">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="247fa-183">Il codice seguente illustra sia la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di un tipo in F # che dispone di un metodo che accetta una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="247fa-183">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="247fa-184">Durante l'esecuzione in un progetto, l'output del codice precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="247fa-184">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="247fa-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="247fa-185">See Also</span></span>
[<span data-ttu-id="247fa-186">Membri</span><span class="sxs-lookup"><span data-stu-id="247fa-186">Members</span></span>](members/index.md)
