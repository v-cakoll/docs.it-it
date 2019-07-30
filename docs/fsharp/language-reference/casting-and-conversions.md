---
title: Cast e conversioni
description: Informazioni su come F# il linguaggio di programmazione fornisce operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi.
ms.date: 05/16/2016
ms.openlocfilehash: ee4df588caabf58c7b9e18961e217ef8f15fcf93
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630429"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="616b6-103">Cast e conversioni (F#)</span><span class="sxs-lookup"><span data-stu-id="616b6-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="616b6-104">In questo argomento viene descritto il supporto per le conversioni di tipi in F#.</span><span class="sxs-lookup"><span data-stu-id="616b6-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="616b6-105">Tipi aritmetici</span><span class="sxs-lookup"><span data-stu-id="616b6-105">Arithmetic Types</span></span>

<span data-ttu-id="616b6-106">F#fornisce operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi, ad esempio tra tipi integer e a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="616b6-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="616b6-107">Gli operatori di conversione integrale e char hanno form selezionati e non controllati; gli operatori a virgola mobile `enum` e l'operatore di conversione non lo sono.</span><span class="sxs-lookup"><span data-stu-id="616b6-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="616b6-108">I moduli deselezionati vengono definiti in `Microsoft.FSharp.Core.Operators` e i form selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="616b6-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="616b6-109">I moduli controllati verificano l'overflow e generano un'eccezione in fase di esecuzione se il valore risultante supera i limiti del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="616b6-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="616b6-110">Ognuno di questi operatori ha lo stesso nome del nome del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="616b6-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="616b6-111">Ad esempio, nel codice seguente, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi.</span><span class="sxs-lookup"><span data-stu-id="616b6-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="616b6-112">La prima occorrenza è il tipo e il secondo è l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="616b6-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="616b6-113">Nella tabella seguente vengono illustrati gli operatori F#di conversione definiti in.</span><span class="sxs-lookup"><span data-stu-id="616b6-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="616b6-114">Operator</span><span class="sxs-lookup"><span data-stu-id="616b6-114">Operator</span></span>|<span data-ttu-id="616b6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616b6-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="616b6-116">Converte in byte, un tipo senza segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="616b6-117">Converte in byte con segno.</span><span class="sxs-lookup"><span data-stu-id="616b6-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="616b6-118">Converte in un intero con segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="616b6-119">Convertire in un Unsigned Integer a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="616b6-120">Converte in un intero con segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="616b6-121">Convertire in un Unsigned Integer a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="616b6-122">Converte in un intero con segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="616b6-123">Convertire in un Unsigned Integer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="616b6-124">Convertire in un intero nativo.</span><span class="sxs-lookup"><span data-stu-id="616b6-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="616b6-125">Convertire in un intero nativo senza segno.</span><span class="sxs-lookup"><span data-stu-id="616b6-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="616b6-126">Convertire in un numero a virgola mobile IEEE a precisione doppia a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="616b6-127">Convertire in un numero a virgola mobile IEEE a precisione singola a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="616b6-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="616b6-128">Convertire in `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="616b6-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="616b6-129">Convertire in `System.Char`, un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="616b6-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="616b6-130">Convertire in un tipo enumerato.</span><span class="sxs-lookup"><span data-stu-id="616b6-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="616b6-131">Oltre ai tipi primitivi incorporati, è possibile usare questi operatori con i tipi che `op_Explicit` implementano `op_Implicit` i metodi o con le firme appropriate.</span><span class="sxs-lookup"><span data-stu-id="616b6-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="616b6-132">Ad esempio, l' `int` operatore di conversione funziona con qualsiasi tipo che fornisce un metodo `op_Explicit` statico che accetta il tipo come parametro e restituisce `int`.</span><span class="sxs-lookup"><span data-stu-id="616b6-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="616b6-133">Come eccezione speciale alla regola generale, non è possibile eseguire l'overload dei metodi per tipo restituito, per `op_Explicit` e. `op_Implicit`</span><span class="sxs-lookup"><span data-stu-id="616b6-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="616b6-134">Tipi enumerati</span><span class="sxs-lookup"><span data-stu-id="616b6-134">Enumerated Types</span></span>

<span data-ttu-id="616b6-135">L' `enum` operatore è un operatore generico che accetta un parametro di tipo che rappresenta il tipo dell' `enum` oggetto in cui eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="616b6-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="616b6-136">Quando si esegue la conversione in un tipo enumerato, l'inferenza del tipo tenta di `enum` determinare il tipo di in cui si desidera eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="616b6-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="616b6-137">Nell'esempio seguente, la variabile `col1` non è annotata in modo esplicito, ma il tipo viene dedotto dal test di uguaglianza successivo.</span><span class="sxs-lookup"><span data-stu-id="616b6-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="616b6-138">Pertanto, il compilatore può dedurre la conversione in un' `Color` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="616b6-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="616b6-139">`col2` In alternativa, è possibile fornire un'annotazione di tipo, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="616b6-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="616b6-140">È anche possibile specificare il tipo di enumerazione di destinazione in modo esplicito come parametro di tipo, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="616b6-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="616b6-141">Si noti che i cast dell'enumerazione funzionano solo se il tipo sottostante dell'enumerazione è compatibile con il tipo convertito.</span><span class="sxs-lookup"><span data-stu-id="616b6-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="616b6-142">Nel codice seguente, la conversione non viene eseguita a causa della mancata corrispondenza tra `int32` e `uint32`.</span><span class="sxs-lookup"><span data-stu-id="616b6-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="616b6-143">Per ulteriori informazioni, vedere [enumerazioni](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="616b6-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="616b6-144">Cast di tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="616b6-144">Casting Object Types</span></span>

<span data-ttu-id="616b6-145">La conversione tra i tipi in una gerarchia di oggetti è fondamentale per la programmazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="616b6-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="616b6-146">Sono disponibili due tipi di conversioni di base: il cast (multicast) e il cast verso il basso (downcast).</span><span class="sxs-lookup"><span data-stu-id="616b6-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="616b6-147">Il cast di una gerarchia implica il cast da un riferimento a un oggetto derivato a un riferimento a un oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="616b6-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="616b6-148">Un cast di questo tipo può funzionare purché la classe di base si trovi nella gerarchia di ereditarietà della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="616b6-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="616b6-149">Il cast di una gerarchia, da un riferimento a un oggetto di base a un riferimento a un oggetto derivato, ha esito positivo solo se l'oggetto è effettivamente un'istanza del tipo di destinazione (derivato) corretto o un tipo derivato dal tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="616b6-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="616b6-150">F#fornisce operatori per questi tipi di conversione.</span><span class="sxs-lookup"><span data-stu-id="616b6-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="616b6-151">L' `:>` operatore esegue il cast della gerarchia e l' `:?>` operatore esegue il cast della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="616b6-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="616b6-152">Upcast</span><span class="sxs-lookup"><span data-stu-id="616b6-152">Upcasting</span></span>

<span data-ttu-id="616b6-153">In molti linguaggi orientati a oggetti, il cast è implicito; in F#le regole sono leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="616b6-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="616b6-154">Il multicast viene applicato automaticamente quando si passano argomenti a metodi su un tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="616b6-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="616b6-155">Tuttavia, per le funzioni con binding Let in un modulo, il cast non è automatico, a meno che il tipo di parametro non venga dichiarato come tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="616b6-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="616b6-156">Per ulteriori informazioni, vedere [tipi flessibili](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="616b6-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="616b6-157">L' `:>` operatore esegue un cast statico, il che significa che la riuscita del cast è determinata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="616b6-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="616b6-158">Se un cast che utilizza `:>` la compilazione viene eseguito correttamente, si tratta di un cast valido e non ha alcuna possibilità di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="616b6-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="616b6-159">È anche possibile usare l' `upcast` operatore per eseguire tale conversione.</span><span class="sxs-lookup"><span data-stu-id="616b6-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="616b6-160">L'espressione seguente specifica una conversione della gerarchia:</span><span class="sxs-lookup"><span data-stu-id="616b6-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="616b6-161">Quando si usa l'operatore di cast, il compilatore tenta di dedurre il tipo da cui si esegue la conversione dal contesto.</span><span class="sxs-lookup"><span data-stu-id="616b6-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="616b6-162">Se il compilatore non è in grado di determinare il tipo di destinazione, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="616b6-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="616b6-163">Downcast</span><span class="sxs-lookup"><span data-stu-id="616b6-163">Downcasting</span></span>

<span data-ttu-id="616b6-164">L' `:?>` operatore esegue un cast dinamico, il che significa che la riuscita del cast è determinata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="616b6-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="616b6-165">Un cast che usa l' `:?>` operatore non viene controllato in fase di compilazione, ma in fase di esecuzione viene effettuato un tentativo di eseguire il cast al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="616b6-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="616b6-166">Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="616b6-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="616b6-167">Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera `InvalidCastException`un'.</span><span class="sxs-lookup"><span data-stu-id="616b6-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="616b6-168">È anche possibile usare l' `downcast` operatore per eseguire una conversione dinamica dei tipi.</span><span class="sxs-lookup"><span data-stu-id="616b6-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="616b6-169">L'espressione seguente specifica una conversione della gerarchia in un tipo dedotto dal contesto del programma:</span><span class="sxs-lookup"><span data-stu-id="616b6-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="616b6-170">Come per l' `upcast` operatore, se il compilatore non è in grado di dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="616b6-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="616b6-171">Il codice seguente illustra l'uso degli `:>` operatori e. `:?>`</span><span class="sxs-lookup"><span data-stu-id="616b6-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="616b6-172">Nel codice viene illustrato che l' `:?>` operatore viene utilizzato meglio quando si è certi che la conversione avrà esito positivo `InvalidCastException` , perché genera un'eccezione se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="616b6-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="616b6-173">Se non si è certi che la conversione avrà esito positivo, un test di tipo `match` che usa un'espressione è migliore perché evita l'overhead causato dalla generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="616b6-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="616b6-174">Poiché gli operatori `downcast` generici e `upcast` si basano sull'inferenza del tipo per determinare l'argomento e il tipo restituito, nel codice precedente, è possibile sostituire</span><span class="sxs-lookup"><span data-stu-id="616b6-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="616b6-175">con</span><span class="sxs-lookup"><span data-stu-id="616b6-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="616b6-176">Nel codice precedente, il tipo di argomento e i tipi restituiti `Derived1` sono `Base1`rispettivamente e.</span><span class="sxs-lookup"><span data-stu-id="616b6-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="616b6-177">Per ulteriori informazioni sui test dei tipi, vedere [espressioni di corrispondenza](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="616b6-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="616b6-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="616b6-178">See also</span></span>

- [<span data-ttu-id="616b6-179">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="616b6-179">F# Language Reference</span></span>](index.md)
