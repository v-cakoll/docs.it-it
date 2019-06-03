---
title: is - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: ac1ec7da7da465f4290000ac9c7254e9492c3c81
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421824"
---
# <a name="is-c-reference"></a><span data-ttu-id="e8255-102">is (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e8255-102">is (C# Reference)</span></span>

<span data-ttu-id="e8255-103">Controlla se un oggetto è compatibile con un determinato tipo o (a partire da C# 7.0) controlla un'espressione rispetto a un criterio.</span><span class="sxs-lookup"><span data-stu-id="e8255-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="e8255-104">Verifica della compatibilità del tipo</span><span class="sxs-lookup"><span data-stu-id="e8255-104">Testing for type compatibility</span></span>

<span data-ttu-id="e8255-105">La parola chiave `is` valuta la compatibilità dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e8255-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="e8255-106">Determina se un'istanza dell'oggetto o il risultato di un'espressione può essere convertito in un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="e8255-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="e8255-107">Presenta la sintassi</span><span class="sxs-lookup"><span data-stu-id="e8255-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="e8255-108">dove *expr* è un'espressione che restituisce un'istanza di un tipo e *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito.</span><span class="sxs-lookup"><span data-stu-id="e8255-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="e8255-109">L'istruzione `is` è `true` se *expr* è non Null e l'oggetto risultante dalla valutazione dell'espressione può essere convertito in *type*; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="e8255-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="e8255-110">Ad esempio, il codice seguente determina se `obj` può essere convertito in un'istanza di tipo `Person`:</span><span class="sxs-lookup"><span data-stu-id="e8255-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="e8255-111">L'istruzione `is` è true se:</span><span class="sxs-lookup"><span data-stu-id="e8255-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="e8255-112">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="e8255-113">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="e8255-114">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="e8255-115">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="e8255-116">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e8255-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="e8255-117">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e8255-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="e8255-118">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="e8255-119">Nell'esempio seguente viene illustrato che l'espressione `is` restituisce `true` per ognuna di queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="e8255-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="e8255-120">La parola chiave `is` genera un avviso in fase di compilazione se è noto che l'espressione sarà sempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e8255-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="e8255-121">Considera solo le conversioni dei riferimenti, le conversioni boxing e unboxing; non considera le conversioni definite dall'utente o le conversioni definite dagli operatori [implicit](implicit.md) ed [explicit](explicit.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="e8255-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="e8255-122">Nell'esempio seguente vengono generati gli avvisi, poiché il risultato della conversione è noto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e8255-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="e8255-123">L'espressione `is` per le conversioni da `int` a `long` e `double` restituisce false, poiché queste conversioni vengono gestite dall'operatore [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="e8255-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="e8255-124">`expr` non può essere un metodo anonimo o un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="e8255-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="e8255-125">Può essere una qualsiasi altra espressione che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="e8255-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="e8255-126">Nell'esempio seguente viene usato `is` per valutare il valore restituito di una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e8255-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="e8255-127">A partire da C# 7.0, è possibile usare criteri di ricerca con il [criterio del tipo](#type) per scrivere codice più conciso che usa l'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="e8255-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="e8255-128">Criteri di ricerca con `is`</span><span class="sxs-lookup"><span data-stu-id="e8255-128">Pattern matching with `is`</span></span>

<span data-ttu-id="e8255-129">A partire da C# 7.0, le istruzioni `is` e [switch](../../../csharp/language-reference/keywords/switch.md) supportano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e8255-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="e8255-130">La parola chiave `is` supporta i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8255-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="e8255-131">[Criterio del tipo](#type), che verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="e8255-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="e8255-132">[Criterio costante](#constant), che verifica se un'espressione restituisce un valore costante specificato.</span><span class="sxs-lookup"><span data-stu-id="e8255-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="e8255-133">[Criterio var](#var), una corrispondenza che ha sempre esito positivo e associa il valore di un'espressione a una nuova variabile locale.</span><span class="sxs-lookup"><span data-stu-id="e8255-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="e8255-134"><a name="type" />Criterio del tipo</span><span class="sxs-lookup"><span data-stu-id="e8255-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="e8255-135">Quando si usa il criterio del tipo per eseguire i criteri di ricerca, `is` verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="e8255-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="e8255-136">È una semplice estensione dell'istruzione `is` che consente la valutazione e la conversione concisa del tipo.</span><span class="sxs-lookup"><span data-stu-id="e8255-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="e8255-137">Il formato generale del criterio del tipo è `is`:</span><span class="sxs-lookup"><span data-stu-id="e8255-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="e8255-138">dove *expr* è un'espressione che restituisce un'istanza di un tipo, *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se il test `is` è `true`.</span><span class="sxs-lookup"><span data-stu-id="e8255-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="e8255-139">L'espressione `is` è `true` se *expr* non è `null` e una delle condizioni seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="e8255-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="e8255-140">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="e8255-141">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="e8255-142">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="e8255-143">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="e8255-144">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e8255-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="e8255-145">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e8255-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="e8255-146">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="e8255-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="e8255-147">A partire da C# 7.1, *expr* può avere un tipo in fase di compilazione definito da un parametro di tipo generico e dai relativi vincoli.</span><span class="sxs-lookup"><span data-stu-id="e8255-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="e8255-148">Se *expr* è `true` e `is` viene usato con un'istruzione `if`, *varname* viene assegnato solo all'interno dell'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="e8255-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="e8255-149">L'ambito di *varname* va dall'espressione `is` alla fine del blocco che racchiude l'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="e8255-149">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="e8255-150">Se si usa *varname* in qualsiasi altra posizione, viene generato un errore in fase di compilazione perché è stata usata una variabile che non è stata assegnata.</span><span class="sxs-lookup"><span data-stu-id="e8255-150">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="e8255-151">Nell'esempio seguente viene usato il criterio del tipo `is` per specificare l'implementazione di un metodo <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> del tipo.</span><span class="sxs-lookup"><span data-stu-id="e8255-151">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="e8255-152">Senza criteri di ricerca, questo codice potrebbe essere scritto come segue.</span><span class="sxs-lookup"><span data-stu-id="e8255-152">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="e8255-153">L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null`.</span><span class="sxs-lookup"><span data-stu-id="e8255-153">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="e8255-154">Anche il criterio del tipo `is` produce codice più compatto quando determina il tipo di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="e8255-154">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="e8255-155">Nell'esempio seguente viene usato il criterio del tipo `is` per determinare se un oggetto è un'istanza `Person` o `Dog` prima di visualizzare il valore di una proprietà appropriata.</span><span class="sxs-lookup"><span data-stu-id="e8255-155">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="e8255-156">Il codice equivalente senza criteri di ricerca richiede un'assegnazione separata che include un cast esplicito.</span><span class="sxs-lookup"><span data-stu-id="e8255-156">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="e8255-157"><a name="constant" /> Criterio costante</span><span class="sxs-lookup"><span data-stu-id="e8255-157"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="e8255-158">Quando si eseguono criteri di ricerca con il criterio costante, `is` verifica se un'espressione è uguale a una costante specificata.</span><span class="sxs-lookup"><span data-stu-id="e8255-158">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="e8255-159">In C# 6 e versioni precedenti, il criterio costante è supportato per l'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="e8255-159">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="e8255-160">A partire da C# 7.0 è supportato anche dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="e8255-160">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="e8255-161">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e8255-161">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="e8255-162">dove *expr* è l'espressione da valutare e *constant* è il valore da testare.</span><span class="sxs-lookup"><span data-stu-id="e8255-162">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="e8255-163">*constant* può essere una delle espressioni costanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8255-163">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="e8255-164">Un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="e8255-164">A literal value.</span></span>

- <span data-ttu-id="e8255-165">Il nome di una variabile `const` dichiarata.</span><span class="sxs-lookup"><span data-stu-id="e8255-165">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="e8255-166">Una costante di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e8255-166">An enumeration constant.</span></span>

<span data-ttu-id="e8255-167">L'espressione costante viene valutata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e8255-167">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="e8255-168">Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="e8255-168">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="e8255-169">In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.</span><span class="sxs-lookup"><span data-stu-id="e8255-169">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="e8255-170">Nell'esempio seguente vengono combinati i criteri di tipo e costante per verificare se un oggetto è un'istanza `Dice` e, in tal caso, per determinare se il valore di un tiro di dadi è 6.</span><span class="sxs-lookup"><span data-stu-id="e8255-170">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="e8255-171">Verifica che `null` possa essere eseguito usando il criterio costante.</span><span class="sxs-lookup"><span data-stu-id="e8255-171">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="e8255-172">La parola chiave `null` è supportata dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="e8255-172">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="e8255-173">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e8255-173">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="e8255-174">L'esempio seguente illustra un confronto di controlli `null`:</span><span class="sxs-lookup"><span data-stu-id="e8255-174">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="e8255-175"><a name="var" /> Criterio var </a></span><span class="sxs-lookup"><span data-stu-id="e8255-175"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="e8255-176">Il criterio `var` è applicabile a qualsiasi tipo o valore.</span><span class="sxs-lookup"><span data-stu-id="e8255-176">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="e8255-177">Il valore di *expr* viene sempre assegnato a una variabile locale dello stesso tipo del tipo della fase di compilazione di *expr*.</span><span class="sxs-lookup"><span data-stu-id="e8255-177">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="e8255-178">Il risultato dell'espressione `is` è sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="e8255-178">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="e8255-179">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e8255-179">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="e8255-180">Nell'esempio seguente viene usato il criterio var per assegnare un'espressione a una variabile denominata `obj`.</span><span class="sxs-lookup"><span data-stu-id="e8255-180">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="e8255-181">Viene quindi visualizzato il valore e il tipo di `obj`.</span><span class="sxs-lookup"><span data-stu-id="e8255-181">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="e8255-182">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e8255-182">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8255-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8255-183">See also</span></span>

- [<span data-ttu-id="e8255-184">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e8255-184">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e8255-185">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e8255-185">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="e8255-186">typeof</span><span class="sxs-lookup"><span data-stu-id="e8255-186">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="e8255-187">as</span><span class="sxs-lookup"><span data-stu-id="e8255-187">as</span></span>](../../../csharp/language-reference/keywords/as.md)
