---
title: Cast e conversioni (F#)
description: 'Informazioni su come il linguaggio di programmazione F # fornisce gli operatori di conversione per le conversioni aritmetiche tra diversi tipi primitivi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: f17d3919c59c5881213d28a59cea7ae184493949
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="084c1-104">Cast e conversioni (F#)</span><span class="sxs-lookup"><span data-stu-id="084c1-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="084c1-105">In questo argomento viene descritto il supporto per le conversioni in F #.</span><span class="sxs-lookup"><span data-stu-id="084c1-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="084c1-106">Tipi aritmetici</span><span class="sxs-lookup"><span data-stu-id="084c1-106">Arithmetic Types</span></span>
<span data-ttu-id="084c1-107">F # fornisce gli operatori di conversione per le conversioni aritmetiche tra diversi tipi di primitivi, ad esempio integer e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="084c1-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="084c1-108">Gli operatori di conversione integrale e char sono controllati e form non è selezionato. operatori di virgola mobile e `enum` non operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="084c1-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="084c1-109">I moduli non controllati vengono definiti in `Microsoft.FSharp.Core.Operators` e i moduli selezionati sono definiti in `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="084c1-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="084c1-110">I moduli selezionati, verificare la presenza di overflow e generano un'eccezione in fase di esecuzione se il valore risultante supera i limiti del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="084c1-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="084c1-111">Ognuno di questi operatori ha lo stesso nome come nome del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="084c1-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="084c1-112">Ad esempio, nel codice seguente, in cui i tipi vengono annotati in modo esplicito, `byte` viene visualizzato con due significati diversi.</span><span class="sxs-lookup"><span data-stu-id="084c1-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="084c1-113">La prima occorrenza è il tipo e il secondo è l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="084c1-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="084c1-114">La tabella seguente illustra gli operatori di conversione definiti in F #.</span><span class="sxs-lookup"><span data-stu-id="084c1-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="084c1-115">Operatore</span><span class="sxs-lookup"><span data-stu-id="084c1-115">Operator</span></span>|<span data-ttu-id="084c1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="084c1-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="084c1-117">Conversione in byte, un tipo senza segno a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="084c1-118">Convertire i byte con segno.</span><span class="sxs-lookup"><span data-stu-id="084c1-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="084c1-119">Convertire in un intero con segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="084c1-120">Convertire in un intero senza segno a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="084c1-121">Convertire in un intero con segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="084c1-122">Convertire in un intero senza segno a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="084c1-123">Convertire in un intero con segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="084c1-124">Convertire in un intero senza segno a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="084c1-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="084c1-125">Convertire un valore intero nativa.</span><span class="sxs-lookup"><span data-stu-id="084c1-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="084c1-126">Convertire in un intero senza segno nativo.</span><span class="sxs-lookup"><span data-stu-id="084c1-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="084c1-127">Convertire un IEEE a precisione doppia a 64 bit numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="084c1-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="084c1-128">Convertire un IEEE a 32 bit a precisione singola numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="084c1-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="084c1-129">Convertire `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="084c1-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="084c1-130">Converti in `System.Char`, un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="084c1-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="084c1-131">Convertire un tipo enumerato.</span><span class="sxs-lookup"><span data-stu-id="084c1-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="084c1-132">Oltre ai tipi primitivi incorporati, è possibile utilizzare questi operatori con tipi che implementano `op_Explicit` o `op_Implicit` metodi con firme appropriate.</span><span class="sxs-lookup"><span data-stu-id="084c1-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="084c1-133">Ad esempio, il `int` operatore di conversione funziona con qualsiasi tipo che fornisce un metodo statico `op_Explicit` che accetta il tipo come parametro e restituisce `int`.</span><span class="sxs-lookup"><span data-stu-id="084c1-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="084c1-134">Come un'eccezione speciale per la regola generale, che non è possibile eseguirne l'overload per il tipo restituito, è possibile eseguire questa operazione per `op_Explicit` e `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="084c1-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="084c1-135">Tipi enumerati</span><span class="sxs-lookup"><span data-stu-id="084c1-135">Enumerated Types</span></span>
<span data-ttu-id="084c1-136">Il `enum` è un operatore generico che accetta un parametro di tipo che rappresenta il tipo del `enum` da convertire.</span><span class="sxs-lookup"><span data-stu-id="084c1-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="084c1-137">Durante la conversione nel tipo enumerato, digitare l'inferenza del tipo di tentativi per determinare il tipo del `enum` che si desidera convertire.</span><span class="sxs-lookup"><span data-stu-id="084c1-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="084c1-138">Nell'esempio seguente, la variabile `col1` non è annotato in modo esplicito, ma il relativo tipo è derivato dal test di uguaglianza successivo.</span><span class="sxs-lookup"><span data-stu-id="084c1-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="084c1-139">Pertanto, il compilatore può dedurre che si desidera convertire in un `Color` enumerazione.</span><span class="sxs-lookup"><span data-stu-id="084c1-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="084c1-140">In alternativa, è possibile fornire un'annotazione di tipo, come con `col2` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="084c1-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="084c1-141">È inoltre possibile specificare il tipo di enumerazione di destinazione in modo esplicito come un parametro di tipo, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="084c1-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="084c1-142">Si noti che l'enumerazione esegue il cast di lavoro solo se il tipo sottostante dell'enumerazione è compatibile con il tipo da convertire.</span><span class="sxs-lookup"><span data-stu-id="084c1-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="084c1-143">Nel codice seguente, la conversione non riesce a compilare a causa della mancata corrispondenza tra `int32` e `uint32`.</span><span class="sxs-lookup"><span data-stu-id="084c1-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="084c1-144">Per ulteriori informazioni, vedere [enumerazioni](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="084c1-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="084c1-145">Il cast dei tipi di oggetto</span><span class="sxs-lookup"><span data-stu-id="084c1-145">Casting Object Types</span></span>
<span data-ttu-id="084c1-146">Conversione tra tipi di una gerarchia di oggetti è fondamentale per la programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="084c1-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="084c1-147">Esistono due tipi di conversioni: cast di backup (upcast) e cast verso il basso (downcast).</span><span class="sxs-lookup"><span data-stu-id="084c1-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="084c1-148">Eseguire il cast di una gerarchia indica il cast da un riferimento di oggetto derivato da un riferimento all'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="084c1-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="084c1-149">Questo cast è garantito per funzionare, purché sia la classe di base nella gerarchia di ereditarietà della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="084c1-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="084c1-150">In una gerarchia, da un riferimento di oggetto di base a un oggetto derivata, esegue il cast ha esito positivo solo se l'oggetto è in realtà di un'istanza del tipo di destinazione corretto (derivato) o un tipo derivato dal tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="084c1-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="084c1-151">F # fornisce gli operatori per questi tipi di conversioni.</span><span class="sxs-lookup"><span data-stu-id="084c1-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="084c1-152">Il `:>` superiore nella gerarchia, esegue il cast di operatore e `:?>` esegue il cast operatore inferiori della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="084c1-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="084c1-153">Upcast</span><span class="sxs-lookup"><span data-stu-id="084c1-153">Upcasting</span></span>
<span data-ttu-id="084c1-154">In molti linguaggi orientata agli oggetti, è implicita; upcast in F #, le regole sono leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="084c1-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="084c1-155">Upcast viene eseguito automaticamente quando si passano argomenti ai metodi del tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="084c1-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="084c1-156">Tuttavia, per le funzioni consentono di associazione in un modulo, l'upcast non è automatica, a meno che il tipo di parametro è dichiarato come tipo flessibile.</span><span class="sxs-lookup"><span data-stu-id="084c1-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="084c1-157">Per ulteriori informazioni, vedere [tipi flessibili](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="084c1-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="084c1-158">Il `:>` operatore esegue un cast statico, il che significa che la riuscita del cast viene determinata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="084c1-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="084c1-159">Se un cast che utilizza `:>` viene compilato correttamente, un cast valido ed non è alcuna possibilità di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="084c1-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="084c1-160">È inoltre possibile utilizzare il `upcast` operatore per eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="084c1-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="084c1-161">L'espressione seguente specifica una conversione nella gerarchia:</span><span class="sxs-lookup"><span data-stu-id="084c1-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="084c1-162">Quando si utilizza l'upcast (operatore), il compilatore prova a dedurre il tipo che si sta convertendo dal contesto.</span><span class="sxs-lookup"><span data-stu-id="084c1-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="084c1-163">Se il compilatore è in grado di determinare il tipo di destinazione, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="084c1-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="084c1-164">Downcast</span><span class="sxs-lookup"><span data-stu-id="084c1-164">Downcasting</span></span>
<span data-ttu-id="084c1-165">Il `:?>` operatore esegue un cast dinamico, il che significa che la riuscita del cast viene determinata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="084c1-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="084c1-166">Un cast che utilizza il `:?>` operatore non viene controllato in fase di compilazione; ma in fase di esecuzione, viene effettuato un tentativo di eseguire il cast al tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="084c1-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="084c1-167">Se l'oggetto è compatibile con il tipo di destinazione, il cast ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="084c1-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="084c1-168">Se l'oggetto non è compatibile con il tipo di destinazione, il runtime genera un `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="084c1-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="084c1-169">È inoltre possibile utilizzare il `downcast` operatore per eseguire una conversione di tipo dinamico.</span><span class="sxs-lookup"><span data-stu-id="084c1-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="084c1-170">L'espressione seguente specifica una conversione verso il basso della gerarchia a un tipo viene dedotto dal contesto di programma:</span><span class="sxs-lookup"><span data-stu-id="084c1-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="084c1-171">Come per il `upcast` (operatore), se il compilatore non è possibile dedurre un tipo di destinazione specifico dal contesto, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="084c1-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="084c1-172">Il codice seguente viene illustrato l'utilizzo del `:>` e `:?>` operatori.</span><span class="sxs-lookup"><span data-stu-id="084c1-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="084c1-173">Il codice viene illustrato che il `:?>` operatore viene utilizzato meglio quando si è certi che la conversione avrà esito positivo, perché genera `InvalidCastException` se la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="084c1-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="084c1-174">Se non si conosce che una conversione avrà esito positivo, un test del tipo che utilizza un `match` espressione è migliore in quanto evita l'overhead della generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="084c1-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="084c1-175">Poiché gli operatori generici `downcast` e `upcast` basarsi sull'inferenza del tipo per determinare il tipo di argomenti e valori restituiti nel codice precedente, è possibile sostituire</span><span class="sxs-lookup"><span data-stu-id="084c1-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="084c1-176">con</span><span class="sxs-lookup"><span data-stu-id="084c1-176">with</span></span>

```fsharp
base1 = upcast d1
```

<span data-ttu-id="084c1-177">Nel codice precedente, il tipo di argomento e tipi restituiti sono `Derived1` e `Base1`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="084c1-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="084c1-178">Per ulteriori informazioni sui test del tipo, vedere [espressioni Match](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="084c1-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="084c1-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="084c1-179">See Also</span></span>
[<span data-ttu-id="084c1-180">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="084c1-180">F# Language Reference</span></span>](index.md)
