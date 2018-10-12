---
title: Parametri e argomenti (F#)
description: 'Informazioni sul supporto del linguaggio F # per la definizione dei parametri e passare argomenti a funzioni, metodi e proprietà.'
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123358"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="74b36-103">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="74b36-103">Parameters and Arguments</span></span>

<span data-ttu-id="74b36-104">In questo argomento viene descritto il supporto di language per la definizione dei parametri e passare argomenti a funzioni, metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="74b36-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="74b36-105">Sono incluse informazioni su come passare per riferimento e su come definire e usare i metodi che possono accettare un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="74b36-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="74b36-106">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="74b36-106">Parameters and Arguments</span></span>

<span data-ttu-id="74b36-107">Il termine *parametro* viene usato per descrivere i nomi per i valori che dovrebbero essere forniti.</span><span class="sxs-lookup"><span data-stu-id="74b36-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="74b36-108">Il termine *argomento* viene usato per i valori specificati per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="74b36-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="74b36-109">Parametri possono essere specificati nella tupla o sottoposto a currying o in una combinazione dei due.</span><span class="sxs-lookup"><span data-stu-id="74b36-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="74b36-110">È possibile passare argomenti usando un nome di parametro espliciti.</span><span class="sxs-lookup"><span data-stu-id="74b36-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="74b36-111">I parametri dei metodi possono essere specificati come facoltativi e assegnati il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="74b36-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="74b36-112">Modelli di parametri</span><span class="sxs-lookup"><span data-stu-id="74b36-112">Parameter Patterns</span></span>

<span data-ttu-id="74b36-113">I parametri specificati per le funzioni e i metodi disponibili, in generale, modelli separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="74b36-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="74b36-114">Ciò significa che, in teoria, tutti i modelli descritti in [espressioni di ricerca](match-expressions.md) può essere utilizzato in un elenco di parametri per una funzione o membro.</span><span class="sxs-lookup"><span data-stu-id="74b36-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="74b36-115">Metodi usano in genere il formato di tupla del passaggio di argomenti.</span><span class="sxs-lookup"><span data-stu-id="74b36-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="74b36-116">Ciò consente di ottenere un risultato più chiaro dalla prospettiva di altri linguaggi .NET perché il formato di tupla corrisponde alla modalità di argomenti vengono passati nei metodi .NET.</span><span class="sxs-lookup"><span data-stu-id="74b36-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="74b36-117">Il currying viene spesso utilizzata con funzioni create con `let` associazioni.</span><span class="sxs-lookup"><span data-stu-id="74b36-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="74b36-118">Lo pseudocodice seguente illustra esempi di tupla e argomenti sottoposti a currying.</span><span class="sxs-lookup"><span data-stu-id="74b36-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="74b36-119">Form combinato sono possibili quando alcuni argomenti sono le tuple e altri non lo sono.</span><span class="sxs-lookup"><span data-stu-id="74b36-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="74b36-120">Altri modelli possono anche essere usati in elenchi di parametri, ma se il modello di parametro non corrisponde a tutti i possibili input, potrebbe esserci una corrispondenza completa in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="74b36-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="74b36-121">L'eccezione `MatchFailureException` viene generato quando il valore di un argomento non corrisponde ai modelli specificati nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="74b36-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="74b36-122">Il compilatore genera un avviso quando si consente a un modello di parametro per le corrispondenze incomplete.</span><span class="sxs-lookup"><span data-stu-id="74b36-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="74b36-123">Almeno un altro modello è comunemente utile per gli elenchi di parametri e che è il carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="74b36-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="74b36-124">È consigliabile usare il modello carattere jolly in un elenco di parametri quando vuoi semplicemente ignorare gli argomenti specificati.</span><span class="sxs-lookup"><span data-stu-id="74b36-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="74b36-125">Il codice seguente viene illustrato l'utilizzo del modello con caratteri jolly in un elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="74b36-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="74b36-126">Il modello carattere jolly può essere utile ogni volta che gli argomenti passati non è necessario, ad esempio il punto di ingresso principale per un programma, se non si è interessati agli argomenti della riga di comando che vengono generalmente forniti come una matrice di stringhe, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="74b36-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="74b36-127">Altri modelli che vengono a volte usati negli argomenti sono la `as` modello e i modelli di identificatori associati a criteri attivi e le unioni discriminate.</span><span class="sxs-lookup"><span data-stu-id="74b36-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="74b36-128">È possibile usare il modello di unione discriminata case singolo come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="74b36-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="74b36-129">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="74b36-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="74b36-130">Criteri attivi possono risultare utili come parametri, ad esempio, durante la trasformazione di un argomento in un formato desiderato, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="74b36-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="74b36-131">È possibile usare il `as` criterio per archiviare un valore corrispondente come valore locale, come illustrato nella seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="74b36-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="74b36-132">Un altro modello che viene usato in alcuni casi è una funzione che lascia l'ultimo argomento senza nome, fornendo come corpo della funzione, un'espressione lambda che consente di eseguire immediatamente un criterio di ricerca in base all'argomento implicito.</span><span class="sxs-lookup"><span data-stu-id="74b36-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="74b36-133">Un esempio di questa è la seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="74b36-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="74b36-134">Questo codice definisce una funzione che accetta un elenco generico e restituisce `true` se l'elenco è vuoto, e `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="74b36-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="74b36-135">L'utilizzo di tali tecniche possa rendere più difficile da leggere codice.</span><span class="sxs-lookup"><span data-stu-id="74b36-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="74b36-136">In alcuni casi, i modelli che prevedono corrispondenze incomplete sono utili, ad esempio, se è noto che gli elenchi nel programma dispongono solo di tre elementi, si potrebbe utilizzare un modello simile al seguente in un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="74b36-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="74b36-137">Uso di criteri di corrispondenza incompleta è consigliabile riservarla ai creazione rapida di prototipi e altri usi temporanei.</span><span class="sxs-lookup"><span data-stu-id="74b36-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="74b36-138">Il compilatore genererà un avviso per tale codice.</span><span class="sxs-lookup"><span data-stu-id="74b36-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="74b36-139">Tali modelli non possono coprire caso generale di tutti i possibili input e pertanto non sono adatti per le API dei componenti.</span><span class="sxs-lookup"><span data-stu-id="74b36-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="74b36-140">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="74b36-140">Named Arguments</span></span>

<span data-ttu-id="74b36-141">Argomenti per i metodi possono essere specificati in base alla posizione in un elenco di argomenti delimitati da virgole, o può essere passati in modo esplicito a un metodo, fornendo il nome, seguito da un segno di uguale e il valore deve essere passato.</span><span class="sxs-lookup"><span data-stu-id="74b36-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="74b36-142">Se specificato, fornendo il nome, possono essere visualizzati in un ordine diverso da quello usato nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="74b36-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="74b36-143">Gli argomenti denominati possono rendere codice più leggibile e più adattabile a determinati tipi di modifiche nell'API, ad esempio un riordinamento dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="74b36-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="74b36-144">Gli argomenti denominati sono consentiti solo per metodi, non per `let`-associati valori di funzioni, funzioni o le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="74b36-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="74b36-145">Esempio di codice seguente viene illustrato l'utilizzo di argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="74b36-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="74b36-146">In una chiamata a un costruttore di classe, è possibile impostare i valori delle proprietà della classe utilizzando una sintassi simile a quella degli argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="74b36-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="74b36-147">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="74b36-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="74b36-148">Per altre informazioni, vedere [costruttori (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="74b36-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="74b36-149">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="74b36-149">Optional Parameters</span></span>

<span data-ttu-id="74b36-150">È possibile specificare un parametro facoltativo per un metodo con un punto interrogativo davanti al nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="74b36-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="74b36-151">I parametri facoltativi vengono interpretati come tipo di opzione F #, pertanto è possibile eseguire le query in modo normale che i tipi di opzione sono sottoposti a query, usando un `match` espressione con `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="74b36-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="74b36-152">I parametri facoltativi sono consentiti solo per i membri, non su funzioni create tramite `let` associazioni.</span><span class="sxs-lookup"><span data-stu-id="74b36-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="74b36-153">È anche possibile usare una funzione `defaultArg`, che imposta un valore predefinito di un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="74b36-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="74b36-154">Il `defaultArg` funzione accetta il parametro facoltativo come primo argomento e il valore predefinito come il secondo.</span><span class="sxs-lookup"><span data-stu-id="74b36-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="74b36-155">Nell'esempio seguente viene illustrato l'utilizzo di parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="74b36-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="74b36-156">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="74b36-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="74b36-157">Il passaggio per riferimento</span><span class="sxs-lookup"><span data-stu-id="74b36-157">Passing by Reference</span></span>

<span data-ttu-id="74b36-158">Passaggio di un valore di F # per riferimento implica [zkratka](byrefs.md), che sono tipi puntatore gestito.</span><span class="sxs-lookup"><span data-stu-id="74b36-158">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="74b36-159">Materiale sussidiario per il tipo da usare è il seguente:</span><span class="sxs-lookup"><span data-stu-id="74b36-159">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="74b36-160">Usare `inref<'T>` se è necessario solo leggere il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="74b36-160">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="74b36-161">Usare `outref<'T>` se è necessario solo scrivere il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="74b36-161">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="74b36-162">Usare `byref<'T>` se è necessario leggere da e scrivere il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="74b36-162">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="74b36-163">Poiché il parametro è un puntatore e il valore è modificabile, qualsiasi modifica del valore viene mantenute dopo l'esecuzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="74b36-163">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="74b36-164">È possibile usare una tupla come valore restituito per archiviare qualsiasi `out` parametri nei metodi della libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="74b36-164">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="74b36-165">In alternativa, è possibile trattare il `out` come parametro un `byref` parametro.</span><span class="sxs-lookup"><span data-stu-id="74b36-165">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="74b36-166">L'esempio di codice seguente illustra entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="74b36-166">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="74b36-167">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="74b36-167">Parameter Arrays</span></span>

<span data-ttu-id="74b36-168">In alcuni casi è necessario definire una funzione che accetta un numero arbitrario di parametri di tipo eterogeneo.</span><span class="sxs-lookup"><span data-stu-id="74b36-168">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="74b36-169">Non sarebbe pratico creare tutti i possibili metodi di overload per conto di tutti i tipi che può essere usati.</span><span class="sxs-lookup"><span data-stu-id="74b36-169">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="74b36-170">Le implementazioni di .NET forniscono supporto per tali metodi tramite la funzionalità di matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="74b36-170">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="74b36-171">Un metodo che accetta una matrice di parametri nella sua firma può essere fornito con un numero arbitrario di parametri.</span><span class="sxs-lookup"><span data-stu-id="74b36-171">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="74b36-172">I parametri vengono inseriti in una matrice.</span><span class="sxs-lookup"><span data-stu-id="74b36-172">The parameters are put into an array.</span></span> <span data-ttu-id="74b36-173">Il tipo degli elementi della matrice determina i tipi di parametro che possono essere passati alla funzione.</span><span class="sxs-lookup"><span data-stu-id="74b36-173">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="74b36-174">Se si definisce la matrice di parametri con `System.Object` come tipo di elemento, quindi il codice client può passare i valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="74b36-174">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="74b36-175">In F #, matrici di parametri possono essere definite solo nei metodi.</span><span class="sxs-lookup"><span data-stu-id="74b36-175">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="74b36-176">Non possono essere usate in funzioni autonome o funzioni definite nei moduli.</span><span class="sxs-lookup"><span data-stu-id="74b36-176">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="74b36-177">Per definire una matrice di parametri, utilizzare il `ParamArray` attributo.</span><span class="sxs-lookup"><span data-stu-id="74b36-177">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="74b36-178">Il `ParamArray` attributo può essere applicato solo all'ultimo parametro.</span><span class="sxs-lookup"><span data-stu-id="74b36-178">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="74b36-179">Il codice seguente viene illustrato sia la chiamata a un metodo .NET che accetta una matrice di parametri e la definizione di un tipo in F # che dispone di un metodo che accetta una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="74b36-179">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="74b36-180">Quando si esegue in un progetto, l'output del codice precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="74b36-180">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="74b36-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74b36-181">See also</span></span>

- [<span data-ttu-id="74b36-182">Membri</span><span class="sxs-lookup"><span data-stu-id="74b36-182">Members</span></span>](members/index.md)
