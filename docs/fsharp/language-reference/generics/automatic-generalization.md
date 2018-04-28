---
title: Generalizzazione automatica (F#)
description: 'Informazioni su come F # generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9b599fd9fe1220b41987bc14a420ed5740aa05f5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="automatic-generalization"></a><span data-ttu-id="29bf7-103">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="29bf7-103">Automatic Generalization</span></span>

<span data-ttu-id="29bf7-104">F # utilizza l'inferenza del tipo per valutare i tipi di espressioni e funzioni.</span><span class="sxs-lookup"><span data-stu-id="29bf7-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="29bf7-105">In questo argomento viene descritto come F # generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile.</span><span class="sxs-lookup"><span data-stu-id="29bf7-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>


## <a name="automatic-generalization"></a><span data-ttu-id="29bf7-106">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="29bf7-106">Automatic Generalization</span></span>
<span data-ttu-id="29bf7-107">Il compilatore F # quando si esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico.</span><span class="sxs-lookup"><span data-stu-id="29bf7-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="29bf7-108">Il compilatore esamina ogni parametro e determina se la funzione presenta una dipendenza dal tipo specifico di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="29bf7-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="29bf7-109">In caso contrario, viene dedotto il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="29bf7-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="29bf7-110">Esempio di codice seguente viene illustrata una funzione che il compilatore deduce per essere generico.</span><span class="sxs-lookup"><span data-stu-id="29bf7-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="29bf7-111">Il tipo viene dedotto da `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="29bf7-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="29bf7-112">Il tipo di indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="29bf7-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="29bf7-113">Uno dei motivi per cui la funzione precedente può essere generico è che la maggiore-operatore (`>`) è generico.</span><span class="sxs-lookup"><span data-stu-id="29bf7-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="29bf7-114">Maggiore-rispetto a operatore ha la firma `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="29bf7-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="29bf7-115">Non tutti gli operatori sono generici e se il codice in una funzione utilizza un tipo di parametro insieme a una funzione non generico o un operatore, tale tipo di parametro non può essere generalizzato.</span><span class="sxs-lookup"><span data-stu-id="29bf7-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="29bf7-116">Poiché `max` è generico, può essere utilizzato con tipi, ad esempio `int`, `float`e così via, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="29bf7-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="29bf7-117">Tuttavia, i due argomenti devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="29bf7-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="29bf7-118">La firma è `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="29bf7-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="29bf7-119">Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="29bf7-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="29bf7-120">Il `max` funzione funziona anche con qualsiasi tipo che supporta la maggiore-operatore.</span><span class="sxs-lookup"><span data-stu-id="29bf7-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="29bf7-121">Di conseguenza, è possibile usare anche su una stringa, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29bf7-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a><span data-ttu-id="29bf7-122">Limitazione valore</span><span class="sxs-lookup"><span data-stu-id="29bf7-122">Value Restriction</span></span>
<span data-ttu-id="29bf7-123">Il compilatore esegue generalizzazione automatica solo definizioni di funzione completa che includono argomenti espliciti e valori semplici non modificabili.</span><span class="sxs-lookup"><span data-stu-id="29bf7-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="29bf7-124">Ciò significa che il compilatore genera un errore se si tenta di compilare il codice che non è sufficientemente vincolato a un tipo specifico, ma anche non generalizzabile.</span><span class="sxs-lookup"><span data-stu-id="29bf7-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="29bf7-125">Il messaggio di errore per questo problema si riferisce a questa restrizione sulla generalizzazione automatica per i valori come il *valore restrizione*.</span><span class="sxs-lookup"><span data-stu-id="29bf7-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="29bf7-126">L'errore di restrizione di valore si verifica in genere, quando si desidera un costrutto generico, ma il compilatore dispone di informazioni insufficienti per generalizzarla o quando si omettono involontariamente sufficienti informazioni sul tipo di un costrutto non generico.</span><span class="sxs-lookup"><span data-stu-id="29bf7-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="29bf7-127">La soluzione all'errore di restrizione di valore consiste nel fornire ulteriori informazioni esplicite per vincolare meglio il problema di inferenza del tipo, in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29bf7-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>


- <span data-ttu-id="29bf7-128">Vincolare un tipo deve essere non generici mediante l'aggiunta di un'annotazione di tipo esplicito per un parametro o valore.</span><span class="sxs-lookup"><span data-stu-id="29bf7-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="29bf7-129">Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione di funzione o in modo incompleto applicati gli argomenti della funzione sottoposte a currying, provare a riscrivere la funzione come una definizione di funzione ordinaria.</span><span class="sxs-lookup"><span data-stu-id="29bf7-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="29bf7-130">Se il problema è un'espressione troppo complessa per essere generalizzato, è necessario inserirla in una funzione mediante l'aggiunta di un parametro aggiuntivo e inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="29bf7-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="29bf7-131">Aggiungere parametri di tipo generico espliciti.</span><span class="sxs-lookup"><span data-stu-id="29bf7-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="29bf7-132">Questa opzione viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="29bf7-132">This option is rarely used.</span></span>

- <span data-ttu-id="29bf7-133">Gli esempi di codice seguenti illustrano ognuno di questi scenari.</span><span class="sxs-lookup"><span data-stu-id="29bf7-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="29bf7-134">Caso 1: Espressione troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="29bf7-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="29bf7-135">In questo esempio, l'elenco `counter` deve essere `int option ref`, ma non è definito come valore semplice non modificabile.</span><span class="sxs-lookup"><span data-stu-id="29bf7-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="29bf7-136">Caso 2: Utilizzo di un costrutto non generalizzabile per definire una funzione generica.</span><span class="sxs-lookup"><span data-stu-id="29bf7-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="29bf7-137">In questo esempio, il costrutto è non generalizzabile perché implica applicazione parziale degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="29bf7-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="29bf7-138">Caso 3: Aggiunta di un parametro aggiuntivo e inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="29bf7-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="29bf7-139">Poiché questa espressione non è abbastanza semplice per la generalizzazione, il compilatore genera l'errore di restrizione di valore.</span><span class="sxs-lookup"><span data-stu-id="29bf7-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="29bf7-140">Caso 4: Aggiunta di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="29bf7-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="29bf7-141">Nell'ultimo caso, il valore diventa una funzione di tipo, che può essere utilizzata per creare valori di molti tipi diversi, ad esempio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29bf7-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="29bf7-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29bf7-142">See Also</span></span>
[<span data-ttu-id="29bf7-143">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="29bf7-143">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="29bf7-144">Generics</span><span class="sxs-lookup"><span data-stu-id="29bf7-144">Generics</span></span>](index.md)

[<span data-ttu-id="29bf7-145">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="29bf7-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="29bf7-146">Vincoli</span><span class="sxs-lookup"><span data-stu-id="29bf7-146">Constraints</span></span>](constraints.md)

