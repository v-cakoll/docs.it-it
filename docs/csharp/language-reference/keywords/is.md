---
title: is - Riferimenti per C#
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399637"
---
# <a name="is-c-reference"></a><span data-ttu-id="1b54c-102">is (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1b54c-102">is (C# Reference)</span></span>

<span data-ttu-id="1b54c-103">L'operatore `is` controlla se il risultato di un'espressione è compatibile con un determinato tipo oppure (a partire da C# 7.0) controlla un'espressione rispetto a un criterio.</span><span class="sxs-lookup"><span data-stu-id="1b54c-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="1b54c-104">Per informazioni sull'operatore di test del tipo `is`, vedere la sezione [Operatore is](../operators/type-testing-and-cast.md#is-operator) dell'articolo [Operatori di cast e di test del tipo](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="1b54c-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="1b54c-105">Criteri di ricerca con `is`</span><span class="sxs-lookup"><span data-stu-id="1b54c-105">Pattern matching with `is`</span></span>

<span data-ttu-id="1b54c-106">A partire da C# 7.0, le istruzioni `is` e [switch](switch.md) supportano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1b54c-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="1b54c-107">La parola chiave `is` supporta i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b54c-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="1b54c-108">[Criterio del tipo](#type-pattern), che verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="1b54c-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="1b54c-109">[Criterio costante](#constant-pattern), che verifica se un'espressione restituisce un valore costante specificato.</span><span class="sxs-lookup"><span data-stu-id="1b54c-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="1b54c-110">[Criterio var](#var-pattern), una corrispondenza che ha sempre esito positivo e associa il valore di un'espressione a una nuova variabile locale.</span><span class="sxs-lookup"><span data-stu-id="1b54c-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="1b54c-111">Criterio del tipo</span><span class="sxs-lookup"><span data-stu-id="1b54c-111">Type pattern</span></span>

<span data-ttu-id="1b54c-112">Quando si usa il criterio del tipo per eseguire i criteri di ricerca, `is` verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="1b54c-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="1b54c-113">È una semplice estensione dell'istruzione `is` che consente la valutazione e la conversione concisa del tipo.</span><span class="sxs-lookup"><span data-stu-id="1b54c-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="1b54c-114">Il formato generale del criterio del tipo è `is`:</span><span class="sxs-lookup"><span data-stu-id="1b54c-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="1b54c-115">Dove *expr* è un'espressione che restituisce un'istanza di un tipo, *type* è il nome del tipo in cui deve essere convertito il risultato `true`di *expr* e *varname* è l'oggetto in cui viene convertito il risultato di *expr* se il `is` test è .</span><span class="sxs-lookup"><span data-stu-id="1b54c-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="1b54c-116">L'espressione `is` è `true` se *expr* non è `null` e una delle condizioni seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="1b54c-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="1b54c-117">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="1b54c-118">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="1b54c-119">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="1b54c-120">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="1b54c-121">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="1b54c-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="1b54c-122">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="1b54c-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="1b54c-123">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="1b54c-124">A partire da C# 7.1, *expr* può avere un tipo in fase di compilazione definito da un parametro di tipo generico e dai relativi vincoli.</span><span class="sxs-lookup"><span data-stu-id="1b54c-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="1b54c-125">Se *expr* è `true` e `is` viene usato con un'istruzione `if`, *varname* viene assegnato solo all'interno dell'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="1b54c-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="1b54c-126">L'ambito di *varname* va dall'espressione `is` alla fine del blocco che racchiude l'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="1b54c-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="1b54c-127">Se si usa *varname* in qualsiasi altra posizione, viene generato un errore in fase di compilazione perché è stata usata una variabile che non è stata assegnata.</span><span class="sxs-lookup"><span data-stu-id="1b54c-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="1b54c-128">Nell'esempio seguente viene usato il criterio del tipo `is` per specificare l'implementazione di un metodo <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> del tipo.</span><span class="sxs-lookup"><span data-stu-id="1b54c-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="1b54c-129">Senza criteri di ricerca, questo codice potrebbe essere scritto come segue.</span><span class="sxs-lookup"><span data-stu-id="1b54c-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="1b54c-130">L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null`.</span><span class="sxs-lookup"><span data-stu-id="1b54c-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="1b54c-131">Anche il criterio del tipo `is` produce codice più compatto quando determina il tipo di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="1b54c-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="1b54c-132">Nell'esempio seguente viene usato il criterio del tipo `is` per determinare se un oggetto è un'istanza `Person` o `Dog` prima di visualizzare il valore di una proprietà appropriata.</span><span class="sxs-lookup"><span data-stu-id="1b54c-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="1b54c-133">Il codice equivalente senza criteri di ricerca richiede un'assegnazione separata che include un cast esplicito.</span><span class="sxs-lookup"><span data-stu-id="1b54c-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="1b54c-134">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="1b54c-134">Constant pattern</span></span>

<span data-ttu-id="1b54c-135">Quando si eseguono criteri di ricerca con il criterio costante, `is` verifica se un'espressione è uguale a una costante specificata.</span><span class="sxs-lookup"><span data-stu-id="1b54c-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="1b54c-136">In C# 6 e versioni precedenti, il criterio costante è supportato per l'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="1b54c-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="1b54c-137">A partire da C# 7.0 è supportato anche dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="1b54c-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="1b54c-138">La relativa sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1b54c-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="1b54c-139">dove *expr* è l'espressione da valutare e *constant* è il valore da testare.</span><span class="sxs-lookup"><span data-stu-id="1b54c-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="1b54c-140">*constant* può essere una delle espressioni costanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b54c-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="1b54c-141">Valore letterale.</span><span class="sxs-lookup"><span data-stu-id="1b54c-141">A literal value.</span></span>

- <span data-ttu-id="1b54c-142">Il nome di una variabile `const` dichiarata.</span><span class="sxs-lookup"><span data-stu-id="1b54c-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="1b54c-143">Una costante di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1b54c-143">An enumeration constant.</span></span>

<span data-ttu-id="1b54c-144">L'espressione costante viene valutata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b54c-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="1b54c-145">Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="1b54c-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="1b54c-146">In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.</span><span class="sxs-lookup"><span data-stu-id="1b54c-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="1b54c-147">Nell'esempio seguente vengono combinati i criteri di tipo e costante per verificare se un oggetto è un'istanza `Dice` e, in tal caso, per determinare se il valore di un tiro di dadi è 6.</span><span class="sxs-lookup"><span data-stu-id="1b54c-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="1b54c-148">Verifica che `null` possa essere eseguito usando il criterio costante.</span><span class="sxs-lookup"><span data-stu-id="1b54c-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="1b54c-149">La parola chiave `null` è supportata dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="1b54c-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="1b54c-150">La relativa sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1b54c-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="1b54c-151">L'esempio seguente illustra un confronto di controlli `null`:</span><span class="sxs-lookup"><span data-stu-id="1b54c-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="1b54c-152">Criterio var</span><span class="sxs-lookup"><span data-stu-id="1b54c-152">var pattern</span></span>

<span data-ttu-id="1b54c-153">Una corrispondenza `var` di modello con il modello ha sempre esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1b54c-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="1b54c-154">La relativa sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="1b54c-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="1b54c-155">Dove il valore di *expr* viene sempre assegnato a una variabile locale denominata *varname*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="1b54c-156">*varname* è una variabile dello stesso tipo del tipo in fase di compilazione di *expr*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="1b54c-157">Se *expr* restituisce `null` `is` , `true` l'espressione `null` produce e assegna a *varname*.</span><span class="sxs-lookup"><span data-stu-id="1b54c-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="1b54c-158">Il modello var è uno `is` dei `true` pochi `null` usi di che produce per un valore.</span><span class="sxs-lookup"><span data-stu-id="1b54c-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="1b54c-159">È possibile `var` utilizzare il modello per creare una variabile temporanea all'interno di un'espressione booleana, come illustrato nell'esempio seguente:You can use the pattern to create a temporary variable within a Boolean expression, as the following example shows:</span><span class="sxs-lookup"><span data-stu-id="1b54c-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="1b54c-160">Nell'esempio precedente, la variabile temporanea viene utilizzata per archiviare il risultato di un'operazione costosa.</span><span class="sxs-lookup"><span data-stu-id="1b54c-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="1b54c-161">La variabile può quindi essere utilizzata più volte.</span><span class="sxs-lookup"><span data-stu-id="1b54c-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1b54c-162">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1b54c-162">C# language specification</span></span>
  
<span data-ttu-id="1b54c-163">Per altre informazioni, vedere la sezione [Operatore is](~/_csharplang/spec/expressions.md#the-is-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md) e le proposte di linguaggio C# seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b54c-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="1b54c-164">Corrispondenza dei criteri</span><span class="sxs-lookup"><span data-stu-id="1b54c-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="1b54c-165">Criteri di ricerca con generics</span><span class="sxs-lookup"><span data-stu-id="1b54c-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="1b54c-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b54c-166">See also</span></span>

- [<span data-ttu-id="1b54c-167">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="1b54c-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1b54c-168">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="1b54c-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="1b54c-169">Operatori di cast e di test del tipo</span><span class="sxs-lookup"><span data-stu-id="1b54c-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
