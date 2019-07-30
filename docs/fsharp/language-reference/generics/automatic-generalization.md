---
title: Generalizzazione automatica
description: Informazioni su F# come generalizza automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi, quando possibile.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630631"
---
# <a name="automatic-generalization"></a><span data-ttu-id="c079d-103">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="c079d-103">Automatic Generalization</span></span>

<span data-ttu-id="c079d-104">F#Usa l'inferenza del tipo per valutare i tipi di funzioni ed espressioni.</span><span class="sxs-lookup"><span data-stu-id="c079d-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="c079d-105">In questo argomento viene F# descritto come generalizzare automaticamente gli argomenti e i tipi di funzioni in modo che funzionino con più tipi quando possibile.</span><span class="sxs-lookup"><span data-stu-id="c079d-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="c079d-106">Generalizzazione automatica</span><span class="sxs-lookup"><span data-stu-id="c079d-106">Automatic Generalization</span></span>

<span data-ttu-id="c079d-107">Il F# compilatore, quando esegue l'inferenza del tipo in una funzione, determina se un determinato parametro può essere generico.</span><span class="sxs-lookup"><span data-stu-id="c079d-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="c079d-108">Il compilatore esamina ogni parametro e determina se la funzione ha una dipendenza dal tipo specifico di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="c079d-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="c079d-109">In caso contrario, il tipo viene dedotto come generico.</span><span class="sxs-lookup"><span data-stu-id="c079d-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="c079d-110">Nell'esempio di codice seguente viene illustrata una funzione che il compilatore deduce da generica.</span><span class="sxs-lookup"><span data-stu-id="c079d-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="c079d-111">Il tipo viene dedotto come `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="c079d-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="c079d-112">Il tipo indica che si tratta di una funzione che accetta due argomenti dello stesso tipo sconosciuto e restituisce un valore dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="c079d-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="c079d-113">Uno dei motivi per cui la funzione precedente può essere generica è che l'operatore Greater-`>`than () è generico.</span><span class="sxs-lookup"><span data-stu-id="c079d-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="c079d-114">L'operatore Greater-than dispone della `'a -> 'a -> bool`firma.</span><span class="sxs-lookup"><span data-stu-id="c079d-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="c079d-115">Non tutti gli operatori sono generici e se il codice in una funzione utilizza un tipo di parametro insieme a una funzione o a un operatore non generico, il tipo di parametro non può essere generalizzato.</span><span class="sxs-lookup"><span data-stu-id="c079d-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="c079d-116">Poiché `max` è generico, può essere usato con tipi `int`come, `float`e così via, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c079d-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="c079d-117">Tuttavia, i due argomenti devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="c079d-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="c079d-118">La firma è `'a -> 'a -> 'a`, non `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="c079d-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="c079d-119">Pertanto, il codice seguente genera un errore perché i tipi non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="c079d-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="c079d-120">La `max` funzione funziona anche con qualsiasi tipo che supporta l'operatore Greater-than.</span><span class="sxs-lookup"><span data-stu-id="c079d-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="c079d-121">Pertanto, è possibile utilizzarlo anche in una stringa, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c079d-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="c079d-122">Restrizione valore</span><span class="sxs-lookup"><span data-stu-id="c079d-122">Value Restriction</span></span>

<span data-ttu-id="c079d-123">Il compilatore esegue la generalizzazione automatica solo per le definizioni di funzione complete con argomenti espliciti e su valori non modificabili semplici.</span><span class="sxs-lookup"><span data-stu-id="c079d-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="c079d-124">Questo significa che il compilatore genera un errore se si tenta di compilare codice non sufficientemente vincolato per essere un tipo specifico, ma anche non generalizzabile.</span><span class="sxs-lookup"><span data-stu-id="c079d-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="c079d-125">Il messaggio di errore per questo problema si riferisce a questa restrizione sulla generalizzazione automatica per i valori come restrizione del *valore*.</span><span class="sxs-lookup"><span data-stu-id="c079d-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="c079d-126">In genere, l'errore di restrizione del valore si verifica quando si vuole che un costrutto sia generico, ma il compilatore non dispone di informazioni sufficienti per generalizzarlo o quando si omette involontariamente informazioni sul tipo sufficienti in un costrutto non generico.</span><span class="sxs-lookup"><span data-stu-id="c079d-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="c079d-127">La soluzione per l'errore di restrizione del valore consiste nel fornire informazioni più esplicite per limitare completamente il problema di inferenza del tipo, in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c079d-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="c079d-128">Vincolare un tipo come non generico aggiungendo un'annotazione di tipo esplicita a un valore o a un parametro.</span><span class="sxs-lookup"><span data-stu-id="c079d-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="c079d-129">Se il problema sta usando un costrutto non generalizzabile per definire una funzione generica, ad esempio una composizione della funzione o gli argomenti della funzione sottoposta a currying, provare a riscrivere la funzione come definizione di funzione ordinaria.</span><span class="sxs-lookup"><span data-stu-id="c079d-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="c079d-130">Se il problema è un'espressione troppo complessa da generalizzare, impostarla in una funzione aggiungendo un parametro aggiuntivo inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c079d-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="c079d-131">Aggiungere parametri di tipo generico espliciti.</span><span class="sxs-lookup"><span data-stu-id="c079d-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="c079d-132">Questa opzione viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="c079d-132">This option is rarely used.</span></span>

- <span data-ttu-id="c079d-133">Gli esempi di codice seguenti illustrano ognuno di questi scenari.</span><span class="sxs-lookup"><span data-stu-id="c079d-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="c079d-134">Caso 1: Espressione troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="c079d-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="c079d-135">In questo esempio, l'elenco `counter` è pensato `int option ref`come, ma non è definito come valore non modificabile semplice.</span><span class="sxs-lookup"><span data-stu-id="c079d-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="c079d-136">Caso 2: Utilizzo di un costrutto non generalizzabile per definire una funzione generica.</span><span class="sxs-lookup"><span data-stu-id="c079d-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="c079d-137">In questo esempio il costrutto è non generalizzabile perché comporta l'applicazione parziale degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="c079d-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="c079d-138">Caso 3: Aggiunta di un parametro aggiuntivo non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c079d-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="c079d-139">Poiché questa espressione non è abbastanza semplice da generalizzare, il compilatore genera l'errore di restrizione del valore.</span><span class="sxs-lookup"><span data-stu-id="c079d-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="c079d-140">Caso 4: Aggiunta di parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="c079d-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="c079d-141">Nell'ultimo caso, il valore diventa una funzione di tipo, che può essere usata per creare valori di molti tipi diversi, ad esempio come segue:</span><span class="sxs-lookup"><span data-stu-id="c079d-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="c079d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c079d-142">See also</span></span>

- [<span data-ttu-id="c079d-143">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="c079d-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="c079d-144">Generics</span><span class="sxs-lookup"><span data-stu-id="c079d-144">Generics</span></span>](index.md)
- [<span data-ttu-id="c079d-145">Parametri di tipo risolti staticamente</span><span class="sxs-lookup"><span data-stu-id="c079d-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="c079d-146">Vincoli</span><span class="sxs-lookup"><span data-stu-id="c079d-146">Constraints</span></span>](constraints.md)
