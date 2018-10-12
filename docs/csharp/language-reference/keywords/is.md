---
title: is (Riferimenti per C#)
ms.date: 02/17/2017
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 8e4103f8e71858ec74c348ee1f675828e6468eb2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170587"
---
# <a name="is-c-reference"></a><span data-ttu-id="f0a02-102">is (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f0a02-102">is (C# Reference)</span></span> #

<span data-ttu-id="f0a02-103">Controlla se un oggetto è compatibile con un determinato tipo o (a partire da C# 7.0) controlla un'espressione rispetto a un criterio.</span><span class="sxs-lookup"><span data-stu-id="f0a02-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="f0a02-104">Verifica della compatibilità del tipo</span><span class="sxs-lookup"><span data-stu-id="f0a02-104">Testing for type compatibility</span></span> ##

<span data-ttu-id="f0a02-105">La parola chiave `is` valuta la compatibilità dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f0a02-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="f0a02-106">Determina se un'istanza dell'oggetto o il risultato di un'espressione può essere convertito in un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="f0a02-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="f0a02-107">Presenta la sintassi</span><span class="sxs-lookup"><span data-stu-id="f0a02-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="f0a02-108">dove *expr* è un'espressione che restituisce un'istanza di un tipo e *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito.</span><span class="sxs-lookup"><span data-stu-id="f0a02-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="f0a02-109">L'istruzione `is` è `true` se *expr* è non Null e l'oggetto risultante dalla valutazione dell'espressione può essere convertito in *type*; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="f0a02-110">Ad esempio, il codice seguente determina se `obj` può essere convertito in un'istanza di tipo `Person`:</span><span class="sxs-lookup"><span data-stu-id="f0a02-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="f0a02-111">L'istruzione `is` è true se:</span><span class="sxs-lookup"><span data-stu-id="f0a02-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="f0a02-112">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="f0a02-113">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="f0a02-114">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="f0a02-115">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="f0a02-116">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f0a02-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="f0a02-117">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="f0a02-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="f0a02-118">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="f0a02-119">Nell'esempio seguente viene illustrato che l'espressione `is` restituisce `true` per ognuna di queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="f0a02-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="f0a02-120">La parola chiave `is` genera un avviso in fase di compilazione se è noto che l'espressione sarà sempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="f0a02-121">Considera solo le conversioni dei riferimenti, le conversioni boxing e unboxing; non considera le conversioni definite dall'utente o le conversioni definite dagli operatori [implicit](implicit.md) ed [explicit](explicit.md) di un tipo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="f0a02-122">Nell'esempio seguente vengono generati gli avvisi, poiché il risultato della conversione è noto in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f0a02-122">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="f0a02-123">Si noti che l'espressione `is` per le conversioni da `int` a `long` e `double` restituisce false, poiché queste conversioni vengono gestite dall'operatore [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="f0a02-123">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="f0a02-124">`expr` può essere qualsiasi espressione che restituisce un valore, ad eccezione di metodi anonimi ed espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="f0a02-124">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="f0a02-125">Nell'esempio seguente viene usato `is` per valutare il valore restituito di una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-125">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="f0a02-126">A partire da C# 7.0, è possibile usare criteri di ricerca con il [criterio del tipo](#type) per scrivere codice più conciso che usa l'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-126">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="f0a02-127">Criteri di ricerca con `is`</span><span class="sxs-lookup"><span data-stu-id="f0a02-127">Pattern matching with `is`</span></span> ##

<span data-ttu-id="f0a02-128">A partire da C# 7.0, le istruzioni `is` e [switch](../../../csharp/language-reference/keywords/switch.md) supportano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f0a02-128">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="f0a02-129">La parola chiave `is` supporta i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a02-129">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="f0a02-130">[Criterio del tipo](#type), che verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-130">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="f0a02-131">[Criterio costante](#constant), che verifica se un'espressione restituisce un valore costante specificato.</span><span class="sxs-lookup"><span data-stu-id="f0a02-131">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="f0a02-132">[Criterio var](#var), una corrispondenza che ha sempre esito positivo e associa il valore di un'espressione a una nuova variabile locale.</span><span class="sxs-lookup"><span data-stu-id="f0a02-132">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="f0a02-133"><a name="type" /> Criterio del tipo </a></span><span class="sxs-lookup"><span data-stu-id="f0a02-133"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="f0a02-134">Quando si usa il criterio del tipo per eseguire i criteri di ricerca, `is` verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-134">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="f0a02-135">È una semplice estensione dell'istruzione `is` che consente la valutazione e la conversione concisa del tipo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-135">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="f0a02-136">Il formato generale del criterio del tipo è `is`:</span><span class="sxs-lookup"><span data-stu-id="f0a02-136">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="f0a02-137">dove *expr* è un'espressione che restituisce un'istanza di un tipo, *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se il test `is` è `true`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-137">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="f0a02-138">L'espressione `is` è `true` se *expr* non è `null` e una delle condizioni seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="f0a02-138">The `is` expression is `true` if *expr* is not `null`, and any of the following is true:</span></span>

- <span data-ttu-id="f0a02-139">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-139">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="f0a02-140">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-140">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="f0a02-141">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-141">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="f0a02-142">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-142">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="f0a02-143">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f0a02-143">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="f0a02-144">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="f0a02-144">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="f0a02-145">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-145">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="f0a02-146">Se *expr* è `true` e `is` viene usato con un'istruzione `if`, *varname* viene assegnato e ha un ambito locale solo all'interno dell'istruzione `if`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-146">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="f0a02-147">Nell'esempio seguente viene usato il criterio del tipo `is` per specificare l'implementazione di un metodo <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> del tipo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-147">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="f0a02-148">Senza criteri di ricerca, questo codice potrebbe essere scritto come segue.</span><span class="sxs-lookup"><span data-stu-id="f0a02-148">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="f0a02-149">L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-149">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="f0a02-150">Anche il criterio del tipo `is` produce codice più compatto quando determina il tipo di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="f0a02-150">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="f0a02-151">Nell'esempio seguente viene usato il criterio del tipo `is` per determinare se un oggetto è un'istanza `Person` o `Dog` prima di visualizzare il valore di una proprietà appropriata.</span><span class="sxs-lookup"><span data-stu-id="f0a02-151">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="f0a02-152">Il codice equivalente senza criteri di ricerca richiede un'assegnazione separata che include un cast esplicito.</span><span class="sxs-lookup"><span data-stu-id="f0a02-152">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="f0a02-153"><a name="constant" /> Criterio costante</span><span class="sxs-lookup"><span data-stu-id="f0a02-153"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="f0a02-154">Quando si eseguono criteri di ricerca con il criterio costante, `is` verifica se un'espressione è uguale a una costante specificata.</span><span class="sxs-lookup"><span data-stu-id="f0a02-154">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="f0a02-155">In C# 6 e versioni precedenti, il criterio costante è supportato per l'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="f0a02-155">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="f0a02-156">A partire da C# 7.0, è supportato anche dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-156">Starting with C# 7.0, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="f0a02-157">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a02-157">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="f0a02-158">dove *expr* è l'espressione da valutare e *constant* è il valore da testare.</span><span class="sxs-lookup"><span data-stu-id="f0a02-158">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="f0a02-159">*constant* può essere una delle espressioni costanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a02-159">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="f0a02-160">Un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="f0a02-160">A literal value.</span></span>

- <span data-ttu-id="f0a02-161">Il nome di una variabile `const` dichiarata.</span><span class="sxs-lookup"><span data-stu-id="f0a02-161">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="f0a02-162">Una costante di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0a02-162">An enumeration constant.</span></span>

<span data-ttu-id="f0a02-163">L'espressione costante viene valutata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a02-163">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="f0a02-164">Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="f0a02-164">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="f0a02-165">In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.</span><span class="sxs-lookup"><span data-stu-id="f0a02-165">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="f0a02-166">Nell'esempio seguente vengono combinati i criteri di tipo e costante per verificare se un oggetto è un'istanza `Dice` e, in tal caso, per determinare se il valore di un tiro di dadi è 6.</span><span class="sxs-lookup"><span data-stu-id="f0a02-166">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="f0a02-167">Verifica che `null` possa essere eseguito usando il criterio costante.</span><span class="sxs-lookup"><span data-stu-id="f0a02-167">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="f0a02-168">La parola chiave `null` è supportata dall'istruzione `is`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-168">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="f0a02-169">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a02-169">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="f0a02-170">L'esempio seguente illustra un confronto di controlli `null`:</span><span class="sxs-lookup"><span data-stu-id="f0a02-170">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="f0a02-171"><a name="var" /> Criterio var </a></span><span class="sxs-lookup"><span data-stu-id="f0a02-171"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="f0a02-172">Un criterio di ricerca con il criterio var ha sempre esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f0a02-172">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="f0a02-173">Presenta la sintassi</span><span class="sxs-lookup"><span data-stu-id="f0a02-173">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="f0a02-174">dove il valore di *expr* viene sempre assegnato a una variabile locale denominata *varname*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-174">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="f0a02-175">*varname* è una variabile statica dello stesso tipo di *expr*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-175">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="f0a02-176">Nell'esempio seguente viene usato il criterio var per assegnare un'espressione a una variabile denominata `obj`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-176">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="f0a02-177">Viene quindi visualizzato il valore e il tipo di `obj`.</span><span class="sxs-lookup"><span data-stu-id="f0a02-177">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="f0a02-178">Si noti che se *expr* è `null`, l'espressione `is` è ancora true e assegna `null` a *varname*.</span><span class="sxs-lookup"><span data-stu-id="f0a02-178">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="f0a02-179">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f0a02-179">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0a02-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0a02-180">See also</span></span>

- [<span data-ttu-id="f0a02-181">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f0a02-181">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f0a02-182">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f0a02-182">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="f0a02-183">typeof</span><span class="sxs-lookup"><span data-stu-id="f0a02-183">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
- [<span data-ttu-id="f0a02-184">as</span><span class="sxs-lookup"><span data-stu-id="f0a02-184">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
- [<span data-ttu-id="f0a02-185">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="f0a02-185">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
