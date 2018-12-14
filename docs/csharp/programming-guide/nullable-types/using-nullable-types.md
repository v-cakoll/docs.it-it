---
title: Uso dei tipi nullable (Guida per programmatori C#)
description: Informazioni su come usare i tipi nullable in C#
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 9c9ab5c3ca1dd49f011bf9c980945fa9da0d8cfc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148353"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="37853-103">Uso dei tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="37853-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="37853-104">I tipi nullable sono tipi che rappresentano tutti i valori di un tipo valore sottostante `T` e un valore [Null](../../language-reference/keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="37853-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="37853-105">Per altre informazioni, vedere l'argomento [Tipi nullable](index.md).</span><span class="sxs-lookup"><span data-stu-id="37853-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="37853-106">È possibile fare riferimento a un tipo nullable in uno dei formati seguenti: `Nullable<T>` o `T?`.</span><span class="sxs-lookup"><span data-stu-id="37853-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="37853-107">Questi due formati sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="37853-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="37853-108">Dichiarazione e assegnazione</span><span class="sxs-lookup"><span data-stu-id="37853-108">Declaration and assignment</span></span>

<span data-ttu-id="37853-109">Dal momento che un tipo valore può essere convertito in modo implicito nel tipo nullable corrispondente, è possibile assegnare un valore a un tipo nullable seguendo la stessa procedura adottata per il relativo tipo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="37853-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="37853-110">È anche possibile assegnare il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="37853-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="37853-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="37853-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="37853-112">Esame di un valore di tipo nullable</span><span class="sxs-lookup"><span data-stu-id="37853-112">Examination of a nullable type value</span></span>

<span data-ttu-id="37853-113">Usare le proprietà di sola lettura seguenti per esaminare un'istanza di un tipo nullable e verificare la presenza di valori Null e recuperare un valore di un tipo sottostante:</span><span class="sxs-lookup"><span data-stu-id="37853-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="37853-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo nullable contiene un valore del relativo tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="37853-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="37853-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="37853-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="37853-116">Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="37853-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="37853-117">Il codice nell'esempio seguente usa la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarla:</span><span class="sxs-lookup"><span data-stu-id="37853-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="37853-118">È anche possibile confrontare una variabile di tipo nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="37853-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="37853-119">A partire da C# 7.0, è possibile usare i [criteri di ricerca](../../pattern-matching.md) per esaminare e ottenere un valore di un tipo nullable:</span><span class="sxs-lookup"><span data-stu-id="37853-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="37853-120">Conversione da un tipo nullable a un tipo sottostante</span><span class="sxs-lookup"><span data-stu-id="37853-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="37853-121">Se è necessario assegnare un valore di tipo nullable a un tipo non nullable, usare l'[operatore null-coalescing `??` ](../../language-reference/operators/null-coalescing-operator.md) per specificare il valore da assegnare se un valore di tipo nullable è Null. A questo scopo, è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="37853-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="37853-122">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è Null deve essere il valore predefinito del tipo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="37853-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="37853-123">È possibile eseguire il cast in modo esplicito di un tipo nullable in un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="37853-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="37853-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="37853-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="37853-125">Se in fase di esecuzione il valore di un tipo nullable è Null, il cast esplicito genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="37853-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="37853-126">Un tipo valore non nullable viene convertito in modo implicito nel tipo nullable corrispondente.</span><span class="sxs-lookup"><span data-stu-id="37853-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="37853-127">Operatori</span><span class="sxs-lookup"><span data-stu-id="37853-127">Operators</span></span>

<span data-ttu-id="37853-128">Gli operatori unari e binari predefiniti e gli eventuali operatori definiti dall'utente esistenti per i tipi di valore possono essere usati anche dai tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="37853-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="37853-129">Questi operatori generano un valore Null se uno o entrambi gli operandi sono Null. In caso contrario, l'operatore usa i valori contenuti per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="37853-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="37853-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="37853-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
<span data-ttu-id="37853-131">Per gli operatori relazionali (`<`, `>`, `<=`, `>=`), se uno o entrambi gli operandi sono Null, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="37853-131">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="37853-132">Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="37853-132">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="37853-133">L'esempio seguente mostra che 10</span><span class="sxs-lookup"><span data-stu-id="37853-133">The following example shows that 10 is</span></span>

- <span data-ttu-id="37853-134">non è né maggiore o uguale a Null,</span><span class="sxs-lookup"><span data-stu-id="37853-134">neither greater than or equal to null,</span></span>
- <span data-ttu-id="37853-135">né minore di Null.</span><span class="sxs-lookup"><span data-stu-id="37853-135">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="37853-136">L'esempio precedente mostra anche che un confronto di uguaglianza tra due tipi nullable che sono entrambi Null restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="37853-136">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="37853-137">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="37853-137">Boxing and unboxing</span></span>

<span data-ttu-id="37853-138">Un tipo valore nullable viene sottoposto a [boxing](../types/boxing-and-unboxing.md) in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="37853-138">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="37853-139">Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="37853-139">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="37853-140">Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, viene sottoposto a boxing un valore del tipo valore sottostante `T` e non l'istanza di <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="37853-140">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="37853-141">È possibile eseguire la conversione unboxing del tipo valore sottoposto a boxing nel tipo nullable corrispondente, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="37853-141">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a><span data-ttu-id="37853-142">Tipo bool?</span><span class="sxs-lookup"><span data-stu-id="37853-142">The bool? type</span></span>

<span data-ttu-id="37853-143">Il tipo nullable `bool?` può contenere tre valori diversi: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) e [null](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="37853-143">The `bool?` nullable type can contain three different values: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md), and [null](../../language-reference/keywords/null.md).</span></span> <span data-ttu-id="37853-144">Il tipo `bool?` è simile al tipo di variabile booleano usato in SQL.</span><span class="sxs-lookup"><span data-stu-id="37853-144">The `bool?` type is like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="37853-145">Per garantire che i risultati prodotti dagli operatori `&` e `|` siano coerenti con il tipo booleano a tre valori in SQL, sono disponibili gli operatori predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="37853-145">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
<span data-ttu-id="37853-146">La semantica di questi operatori è definita dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="37853-146">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="37853-147">x</span><span class="sxs-lookup"><span data-stu-id="37853-147">x</span></span>|<span data-ttu-id="37853-148">y</span><span class="sxs-lookup"><span data-stu-id="37853-148">y</span></span>|<span data-ttu-id="37853-149">x&y</span><span class="sxs-lookup"><span data-stu-id="37853-149">x&y</span></span>|<span data-ttu-id="37853-150">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="37853-150">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="37853-151">true</span><span class="sxs-lookup"><span data-stu-id="37853-151">true</span></span>|<span data-ttu-id="37853-152">true</span><span class="sxs-lookup"><span data-stu-id="37853-152">true</span></span>|<span data-ttu-id="37853-153">true</span><span class="sxs-lookup"><span data-stu-id="37853-153">true</span></span>|<span data-ttu-id="37853-154">true</span><span class="sxs-lookup"><span data-stu-id="37853-154">true</span></span>|  
|<span data-ttu-id="37853-155">true</span><span class="sxs-lookup"><span data-stu-id="37853-155">true</span></span>|<span data-ttu-id="37853-156">False</span><span class="sxs-lookup"><span data-stu-id="37853-156">false</span></span>|<span data-ttu-id="37853-157">false</span><span class="sxs-lookup"><span data-stu-id="37853-157">false</span></span>|<span data-ttu-id="37853-158">true</span><span class="sxs-lookup"><span data-stu-id="37853-158">true</span></span>|  
|<span data-ttu-id="37853-159">true</span><span class="sxs-lookup"><span data-stu-id="37853-159">true</span></span>|<span data-ttu-id="37853-160">Null</span><span class="sxs-lookup"><span data-stu-id="37853-160">null</span></span>|<span data-ttu-id="37853-161">Null</span><span class="sxs-lookup"><span data-stu-id="37853-161">null</span></span>|<span data-ttu-id="37853-162">true</span><span class="sxs-lookup"><span data-stu-id="37853-162">true</span></span>|  
|<span data-ttu-id="37853-163">False</span><span class="sxs-lookup"><span data-stu-id="37853-163">false</span></span>|<span data-ttu-id="37853-164">true</span><span class="sxs-lookup"><span data-stu-id="37853-164">true</span></span>|<span data-ttu-id="37853-165">False</span><span class="sxs-lookup"><span data-stu-id="37853-165">false</span></span>|<span data-ttu-id="37853-166">true</span><span class="sxs-lookup"><span data-stu-id="37853-166">true</span></span>|  
|<span data-ttu-id="37853-167">False</span><span class="sxs-lookup"><span data-stu-id="37853-167">false</span></span>|<span data-ttu-id="37853-168">False</span><span class="sxs-lookup"><span data-stu-id="37853-168">false</span></span>|<span data-ttu-id="37853-169">False</span><span class="sxs-lookup"><span data-stu-id="37853-169">false</span></span>|<span data-ttu-id="37853-170">False</span><span class="sxs-lookup"><span data-stu-id="37853-170">false</span></span>|  
|<span data-ttu-id="37853-171">False</span><span class="sxs-lookup"><span data-stu-id="37853-171">false</span></span>|<span data-ttu-id="37853-172">Null</span><span class="sxs-lookup"><span data-stu-id="37853-172">null</span></span>|<span data-ttu-id="37853-173">False</span><span class="sxs-lookup"><span data-stu-id="37853-173">false</span></span>|<span data-ttu-id="37853-174">Null</span><span class="sxs-lookup"><span data-stu-id="37853-174">null</span></span>|  
|<span data-ttu-id="37853-175">Null</span><span class="sxs-lookup"><span data-stu-id="37853-175">null</span></span>|<span data-ttu-id="37853-176">true</span><span class="sxs-lookup"><span data-stu-id="37853-176">true</span></span>|<span data-ttu-id="37853-177">Null</span><span class="sxs-lookup"><span data-stu-id="37853-177">null</span></span>|<span data-ttu-id="37853-178">true</span><span class="sxs-lookup"><span data-stu-id="37853-178">true</span></span>|  
|<span data-ttu-id="37853-179">Null</span><span class="sxs-lookup"><span data-stu-id="37853-179">null</span></span>|<span data-ttu-id="37853-180">False</span><span class="sxs-lookup"><span data-stu-id="37853-180">false</span></span>|<span data-ttu-id="37853-181">False</span><span class="sxs-lookup"><span data-stu-id="37853-181">false</span></span>|<span data-ttu-id="37853-182">Null</span><span class="sxs-lookup"><span data-stu-id="37853-182">null</span></span>|  
|<span data-ttu-id="37853-183">Null</span><span class="sxs-lookup"><span data-stu-id="37853-183">null</span></span>|<span data-ttu-id="37853-184">Null</span><span class="sxs-lookup"><span data-stu-id="37853-184">null</span></span>|<span data-ttu-id="37853-185">Null</span><span class="sxs-lookup"><span data-stu-id="37853-185">null</span></span>|<span data-ttu-id="37853-186">Null</span><span class="sxs-lookup"><span data-stu-id="37853-186">null</span></span>|  

<span data-ttu-id="37853-187">Tenere presente che questi due operatori non si attengono alle regole descritte nella sezione [Operatori](#operators): il risultato di una valutazione degli operatori può essere diverso da Null, anche se uno degli operandi è Null.</span><span class="sxs-lookup"><span data-stu-id="37853-187">Note that these two operators don't follow the rules described in the [Operators](#operators) section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="37853-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37853-188">See Also</span></span>

- [<span data-ttu-id="37853-189">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="37853-189">Nullable types</span></span>](index.md)  
- [<span data-ttu-id="37853-190">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="37853-190">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="37853-191">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="37853-191">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)  
