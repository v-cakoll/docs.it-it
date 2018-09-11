---
title: Cast e conversioni (F#)
description: 'Informazioni su come il linguaggio di programmazione F # offre operatori di conversione per le conversioni aritmetiche tra vari tipi primitivi.'
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338233"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="add6c-103">Cast e conversioni (F#)</span><span class="sxs-lookup"><span data-stu-id="add6c-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="add6c-104">In questo argomento viene descritto il supporto per le conversioni di tipo in F #.</span><span class="sxs-lookup"><span data-stu-id="add6c-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="add6c-105">Tipi aritmetici</span><span class="sxs-lookup"><span data-stu-id="add6c-105">Arithmetic Types</span></span>

<span data-ttu-id="add6c-106">F # fornisce gli operatori di conversione per le conversioni aritmetiche tra vari tipi di primitivi, ad esempio tra valori interi e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="add6c-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="add6c-107">Gli operatori di conversione integrale e char sono stati verificati e form unchecked; gli operatori della virgola mobile e `enum` operatore di conversione non lo sono.</span><span class="sxs-lookup"><span data-stu-id="add6c-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="add6c-108">I moduli deselezionati vengono definiti in `Microsoft.FSharp.Core.Operators` e i moduli selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="add6c-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="add6c-109">I moduli selezionati verificare la presenza di overflow e generano un'eccezione di runtime se il valore risultante supera i limiti del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="add6c-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="add6c-110">Ognuno di questi operatori ha lo stesso nome come nome del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="add6c-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="add6c-111">Ad esempio, nel codice seguente, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi.</span><span class="sxs-lookup"><span data-stu-id="add6c-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="add6c-112">La prima occorrenza è il tipo e il secondo è l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="add6c-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="add6c-113">La tabella seguente illustra gli operatori di conversione definiti in F #.</span><span class="sxs-lookup"><span data-stu-id="add6c-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="add6c-114">Operatore</span><span class="sxs-lookup"><span data-stu-id="add6c-114">Operator</span></span>|<span data-ttu-id="add6c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="add6c-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="add6c-116">Converte in byte, un tipo senza segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="add6c-117">Converte in byte con segno.</span><span class="sxs-lookup"><span data-stu-id="add6c-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="add6c-118">Convertire in un intero con segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="add6c-119">Convertire in un intero senza segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="add6c-120">Convertire in un intero con segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="add6c-121">Convertire in un intero senza segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="add6c-122">Convertire in un intero con segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="add6c-123">Convertire in un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="add6c-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="add6c-124">Converte in un integer nativo.</span><span class="sxs-lookup"><span data-stu-id="add6c-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="add6c-125">Convertire in un unsigned integer nativo.</span><span class="sxs-lookup"><span data-stu-id="add6c-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="add6c-126">Convertire un IEEE a precisione doppia a 64 bit numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="add6c-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="add6c-127">Convertire un IEEE a 32 bit con precisione singola numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="add6c-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="add6c-128">Converti in `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="add6c-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="add6c-129">Converti in `System.Char`, un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="add6c-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="add6c-130">Convertire in un tipo enumerato.</span><span class="sxs-lookup"><span data-stu-id="add6c-130">Convert to an enumerated type.</span></span>|
<span data-ttu-id="add6c-131">Oltre ai tipi primitivi incorporati, è possibile usare questi operatori con i tipi che implementano `op_Explicit` o `op_Implicit` metodi con firme appropriate.</span><span class="sxs-lookup"><span data-stu-id="add6c-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="add6c-132">Ad esempio, il `int` operatore di conversione funziona con qualsiasi tipo che fornisce un metodo statico `op_Explicit` che accetta il tipo come parametro e restituisce `int`.</span><span class="sxs-lookup"><span data-stu-id="add6c-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="add6c-133">Come eccezione speciale per la regola generale che non possono essere sottoposti a overload di metodi per il tipo restituito, è possibile farlo `op_Explicit` e `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="add6c-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="add6c-134">Tipi enumerati</span><span class="sxs-lookup"><span data-stu-id="add6c-134">Enumerated Types</span></span>

<span data-ttu-id="add6c-135">Il `enum` è un operatore di tipo generico che accetta un parametro di tipo che rappresenta il tipo del `enum` da convertire in.</span><span class="sxs-lookup"><span data-stu-id="add6c-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="add6c-136">Quando converte un tipo enumerato, digitare l'inferenza tenta di determinare il tipo del `enum` che si desidera convertire.</span><span class="sxs-lookup"><span data-stu-id="add6c-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="add6c-137">Nell'esempio seguente, la variabile `col1` non è annotato in modo esplicito, ma il relativo tipo viene dedotto dal test di uguaglianza più avanti.</span><span class="sxs-lookup"><span data-stu-id="add6c-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="add6c-138">Pertanto, il compilatore può dedurre che si desidera convertire in un `Color` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="add6c-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="add6c-139">In alternativa, è possibile fornire un'annotazione di tipo, come con `col2` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="add6c-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="add6c-140">È anche possibile specificare il tipo di enumerazione di destinazione in modo esplicito come un parametro di tipo, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="add6c-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="add6c-141">Si noti che l'enumerazione esegue il cast di lavoro solo se il tipo sottostante dell'enumerazione è compatibile con il tipo da convertire.</span><span class="sxs-lookup"><span data-stu-id="add6c-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="add6c-142">Nel codice seguente, la conversione ha esito negativo per la compilazione a causa della mancata corrispondenza tra `int32` e `uint32`.</span><span class="sxs-lookup"><span data-stu-id="add6c-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="add6c-143">Per altre informazioni, vedere [enumerazioni](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="add6c-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="add6c-144">Il cast dei tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="add6c-144">Casting Object Types</span></span>

<span data-ttu-id="add6c-145">Conversione tra tipi in una gerarchia di oggetti è fondamentale per la programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="add6c-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="add6c-146">Esistono due tipi di base delle conversioni: cast backup (l'upcast) e cast verso il basso (downcast).</span><span class="sxs-lookup"><span data-stu-id="add6c-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="add6c-147">Eseguire il cast di una gerarchia indica che il cast da un riferimento all'oggetto derivato da un riferimento di oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="add6c-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="add6c-148">Un cast di questo tipo sarà sicuramente funzionante, purché sia la classe di base nella gerarchia di ereditarietà della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="add6c-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="add6c-149">Il downcast in una gerarchia, da un riferimento di oggetto di base a un riferimento all'oggetto derivato, ha esito positivo solo se l'oggetto è effettivamente un'istanza del tipo corretto di destinazione (derivato) o un tipo derivato dal tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="add6c-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="add6c-150">F # fornisce operatori per questi tipi di conversioni.</span><span class="sxs-lookup"><span data-stu-id="add6c-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="add6c-151">Il `:>` viene eseguito il cast operatore nella gerarchia e `:?>` operatore viene eseguito il cast verso il basso della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="add6c-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="add6c-152">Upcast</span><span class="sxs-lookup"><span data-stu-id="add6c-152">Upcasting</span></span>

<span data-ttu-id="add6c-153">In molti linguaggi orientate a oggetti, è implicita; l'upcast in F #, le regole sono leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="add6c-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="add6c-154">Upcast viene applicata automaticamente quando si passano argomenti ai metodi in un tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="add6c-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="add6c-155">Tuttavia, per le funzioni consentono di associazione in un modulo, l'upcast non è automatica, a meno che il tipo di parametro è dichiarato come tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="add6c-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="add6c-156">Per altre informazioni, vedere [tipi flessibili](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="add6c-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="add6c-157">Il `:>` operatore esegue un cast statico, che significa che il successo del cast è determinato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="add6c-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="add6c-158">Se un cast che usa `:>` viene compilato correttamente, è un cast valido e non dispone di alcuna possibilità di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="add6c-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="add6c-159">È anche possibile usare il `upcast` operatore per eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="add6c-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="add6c-160">L'espressione seguente specifica una conversione nella gerarchia:</span><span class="sxs-lookup"><span data-stu-id="add6c-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="add6c-161">Quando si usa l'upcast (operatore), il compilatore prova a dedurre il tipo che si sta convertendo dal contesto.</span><span class="sxs-lookup"><span data-stu-id="add6c-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="add6c-162">Se il compilatore non riesce a determinare il tipo di destinazione, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="add6c-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="add6c-163">Downcast</span><span class="sxs-lookup"><span data-stu-id="add6c-163">Downcasting</span></span>

<span data-ttu-id="add6c-164">Il `:?>` operatore esegue un cast dinamico, il che significa che il successo del cast è determinato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="add6c-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="add6c-165">Un cast che utilizza il `:?>` operatore non è selezionato in fase di compilazione; ma in fase di esecuzione, viene effettuato un tentativo di eseguire il cast nel tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="add6c-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="add6c-166">Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="add6c-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="add6c-167">Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera un `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="add6c-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="add6c-168">È anche possibile usare il `downcast` operatore per eseguire una conversione di tipo dinamico.</span><span class="sxs-lookup"><span data-stu-id="add6c-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="add6c-169">L'espressione seguente specifica una conversione verso il basso della gerarchia a un tipo viene dedotto dal contesto del programma:</span><span class="sxs-lookup"><span data-stu-id="add6c-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="add6c-170">Come per il `upcast` (operatore), se il compilatore non è possibile dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="add6c-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="add6c-171">Il codice seguente viene illustrato l'utilizzo dei `:>` e `:?>` operatori.</span><span class="sxs-lookup"><span data-stu-id="add6c-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="add6c-172">Il codice viene illustrato che il `:?>` operatore è più adatta quando si è certi che la conversione avrà esito positivo, perché genera `InvalidCastException` se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="add6c-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="add6c-173">Se non si conosce che una conversione avrà esito positivo, un tipo test che usa un `match` espressione è preferibile perché evita l'overhead della generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="add6c-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="add6c-174">Poiché gli operatori generici `downcast` e `upcast` basarsi sull'inferenza del tipo per determinare il tipo di argomenti e valori restituiti, nel codice precedente, è possibile sostituire</span><span class="sxs-lookup"><span data-stu-id="add6c-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="add6c-175">con</span><span class="sxs-lookup"><span data-stu-id="add6c-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="add6c-176">Nel codice precedente, il tipo di argomento e tipi restituiti sono `Derived1` e `Base1`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="add6c-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="add6c-177">Per altre informazioni sui test di tipo, vedere [espressioni di ricerca](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="add6c-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="add6c-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="add6c-178">See also</span></span>

- [<span data-ttu-id="add6c-179">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="add6c-179">F# Language Reference</span></span>](index.md)
