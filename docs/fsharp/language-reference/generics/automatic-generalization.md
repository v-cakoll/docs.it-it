---
title: Generalizzazione automatica (F#)
description: Informazioni su come F# generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionano con più tipi, laddove possibile.
ms.date: 05/16/2016
ms.openlocfilehash: 84de9cbb2b9fcf2488393f7dbdfc3b610cdcffb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43855777"
---
# <a name="automatic-generalization"></a><span data-ttu-id="bd286-103">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="bd286-103">Automatic Generalization</span></span>

<span data-ttu-id="bd286-104">F# Usa l'inferenza del tipo per valutare i tipi di funzioni ed espressioni.</span><span class="sxs-lookup"><span data-stu-id="bd286-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="bd286-105">In questo argomento viene descritto come F# generalizzati automaticamente gli argomenti e i tipi di funzioni in modo che funzionano con più tipi quando possibile.</span><span class="sxs-lookup"><span data-stu-id="bd286-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="bd286-106">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="bd286-106">Automatic Generalization</span></span>

<span data-ttu-id="bd286-107">Il compilatore F#, quando esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico.</span><span class="sxs-lookup"><span data-stu-id="bd286-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="bd286-108">Il compilatore esamina ogni parametro e determina se la funzione ha una dipendenza dal tipo specifico di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="bd286-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="bd286-109">Se non esiste, il tipo viene dedotto come generici.</span><span class="sxs-lookup"><span data-stu-id="bd286-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="bd286-110">Esempio di codice seguente viene illustrata una funzione che il compilatore deduce automaticamente per essere generica.</span><span class="sxs-lookup"><span data-stu-id="bd286-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="bd286-111">Il tipo viene dedotto per essere `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="bd286-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="bd286-112">Il tipo indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="bd286-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="bd286-113">Uno dei motivi per cui la funzione precedente può essere generica è che il maggiore-operatore (`>`) è a sua volta generico.</span><span class="sxs-lookup"><span data-stu-id="bd286-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="bd286-114">Maggiore-di operatore ha la firma `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="bd286-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="bd286-115">Non tutti gli operatori sono generici e se il codice in una funzione Usa un tipo di parametro insieme a una funzione non generico o un operatore, tale tipo di parametro non può essere generalizzato.</span><span class="sxs-lookup"><span data-stu-id="bd286-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="bd286-116">In quanto `max` è generico e può essere utilizzato con i tipi, ad esempio `int`, `float`e così via, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="bd286-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="bd286-117">Tuttavia, i due argomenti devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="bd286-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="bd286-118">La firma viene `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="bd286-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="bd286-119">Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="bd286-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="bd286-120">Il `max` funzione funziona anche con qualsiasi tipo che supporta il valore maggiore: operatore di maggioranza.</span><span class="sxs-lookup"><span data-stu-id="bd286-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="bd286-121">Pertanto, si può anche usarlo in una stringa, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bd286-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="bd286-122">Limitazione dei valori</span><span class="sxs-lookup"><span data-stu-id="bd286-122">Value Restriction</span></span>

<span data-ttu-id="bd286-123">Il compilatore esegue generalizzazione automatica solo nelle definizioni di funzione completa che includono argomenti espliciti e sul semplici valori non modificabili.</span><span class="sxs-lookup"><span data-stu-id="bd286-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="bd286-124">Ciò significa che il compilatore genera un errore se si prova a compilare il codice che non è sufficientemente vincolato a un tipo specifico, ma anche non generalizzabile.</span><span class="sxs-lookup"><span data-stu-id="bd286-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="bd286-125">Il messaggio di errore per questo problema è relativo a questa limitazione per la generalizzazione automatica per i valori come il *limitazione valore*.</span><span class="sxs-lookup"><span data-stu-id="bd286-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="bd286-126">L'errore di limitazione valore si verifica in genere, quando si desidera un costrutto per essere generico, ma il compilatore dispone di informazioni sufficienti per generalizzarla o quando si omette involontariamente sufficienti informazioni sul tipo in un costrutto non generico.</span><span class="sxs-lookup"><span data-stu-id="bd286-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="bd286-127">La soluzione per l'errore di limitazione valore consiste nel fornire informazioni più esplicite per comprenderle appieno limitare il problema di inferenza del tipo, in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd286-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="bd286-128">Vincolare un tipo può essere non generica aggiungendo un'annotazione di tipo esplicito a un parametro o valore.</span><span class="sxs-lookup"><span data-stu-id="bd286-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="bd286-129">Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione di funzione o in modo incompleto applicati gli argomenti della funzione sottoposti a currying, provare a riscrivere la funzione come una definizione di funzione ordinaria.</span><span class="sxs-lookup"><span data-stu-id="bd286-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="bd286-130">Se il problema è un'espressione troppo complessa per procedere alla generalizzazione, trasformarlo in una funzione mediante l'aggiunta di un parametro aggiuntivo e non usato.</span><span class="sxs-lookup"><span data-stu-id="bd286-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="bd286-131">Aggiungere parametri di tipo generico esplicita.</span><span class="sxs-lookup"><span data-stu-id="bd286-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="bd286-132">Questa opzione viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="bd286-132">This option is rarely used.</span></span>

- <span data-ttu-id="bd286-133">Gli esempi di codice seguente viene illustrato ognuno di questi scenari.</span><span class="sxs-lookup"><span data-stu-id="bd286-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="bd286-134">Caso 1: Un'espressione troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="bd286-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="bd286-135">In questo esempio, nell'elenco `counter` è destinato a essere `int option ref`, ma non è definito come un semplice valore non modificabile.</span><span class="sxs-lookup"><span data-stu-id="bd286-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="bd286-136">Caso 2: Utilizzo di un costrutto non generalizzabile per definire una funzione generica.</span><span class="sxs-lookup"><span data-stu-id="bd286-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="bd286-137">In questo esempio, il costrutto è non generalizzabile dal momento che implica l'applicazione parziale degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="bd286-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="bd286-138">Caso 3: Aggiunta di un parametro aggiuntivo e non usato.</span><span class="sxs-lookup"><span data-stu-id="bd286-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="bd286-139">Poiché questa espressione non è abbastanza semplice per la generalizzazione, il compilatore genera l'errore di limitazione valore.</span><span class="sxs-lookup"><span data-stu-id="bd286-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="bd286-140">Caso 4: Aggiunta di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="bd286-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="bd286-141">Nell'ultimo caso, il valore diventa una funzione di tipo, che può essere utilizzata per creare valori di molti tipi diversi, ad esempio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bd286-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="bd286-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd286-142">See also</span></span>

- [<span data-ttu-id="bd286-143">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="bd286-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="bd286-144">Generics</span><span class="sxs-lookup"><span data-stu-id="bd286-144">Generics</span></span>](index.md)
- [<span data-ttu-id="bd286-145">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="bd286-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="bd286-146">Vincoli</span><span class="sxs-lookup"><span data-stu-id="bd286-146">Constraints</span></span>](constraints.md)
