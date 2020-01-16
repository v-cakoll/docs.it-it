---
title: Tipi di valore Nullable C# -Reference
description: Informazioni sui C# tipi di valore nullable e su come usarli
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 3b9a29e75fe894f7d8a0751feefa9eb0a39baa2c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964322"
---
# <a name="nullable-value-types-c-reference"></a><span data-ttu-id="bb53d-103">Tipi di valore NullableC# (riferimento)</span><span class="sxs-lookup"><span data-stu-id="bb53d-103">Nullable value types (C# reference)</span></span>

<span data-ttu-id="bb53d-104">Un tipo di valore Nullable `T?` rappresenta tutti i valori del [tipo di valore](../keywords/value-types.md) sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bb53d-104">A nullable value type `T?` represents all values of its underlying [value type](../keywords/value-types.md) `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="bb53d-105">Ad esempio, è possibile assegnare uno dei tre valori seguenti a una variabile `bool?`: `true`, `false`o `null`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-105">For example, you can assign any of the following three values to a `bool?` variable: `true`, `false`, or `null`.</span></span> <span data-ttu-id="bb53d-106">Un tipo di valore sottostante `T` non può essere un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="bb53d-106">An underlying value type `T` cannot be a nullable value type itself.</span></span>

> [!NOTE]
> <span data-ttu-id="bb53d-107">C#8,0 introduce la funzionalità dei tipi di riferimento Nullable.</span><span class="sxs-lookup"><span data-stu-id="bb53d-107">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="bb53d-108">Per altre informazioni, vedere [tipi di riferimento Nullable](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="bb53d-108">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="bb53d-109">I tipi di valore nullable sono disponibili a C# partire da 2.</span><span class="sxs-lookup"><span data-stu-id="bb53d-109">The nullable value types are available beginning with C# 2.</span></span>

<span data-ttu-id="bb53d-110">Qualsiasi tipo di valore Nullable è un'istanza della struttura <xref:System.Nullable%601?displayProperty=nameWithType> generica.</span><span class="sxs-lookup"><span data-stu-id="bb53d-110">Any nullable value type is an instance of the generic <xref:System.Nullable%601?displayProperty=nameWithType> structure.</span></span> <span data-ttu-id="bb53d-111">È possibile fare riferimento a un tipo di valore nullable con un tipo sottostante `T` in uno qualsiasi dei seguenti formati intercambiabili: `Nullable<T>` o `T?`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-111">You can refer to a nullable value type with an underlying type `T` in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span>

<span data-ttu-id="bb53d-112">Si usa in genere un tipo di valore nullable quando è necessario rappresentare il valore non definito di un tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="bb53d-112">You typically use a nullable value type when you need to represent the undefined value of an underlying value type.</span></span> <span data-ttu-id="bb53d-113">Una variabile booleana o `bool`, ad esempio, può essere solo `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-113">For example, a Boolean, or `bool`, variable can only be either `true` or `false`.</span></span> <span data-ttu-id="bb53d-114">Tuttavia, in alcune applicazioni un valore di variabile può essere non definito o mancante.</span><span class="sxs-lookup"><span data-stu-id="bb53d-114">However, in some applications a variable value can be undefined or missing.</span></span> <span data-ttu-id="bb53d-115">Un campo di database, ad esempio, può contenere `true` o `false`, oppure non può contenere alcun valore, ovvero `NULL`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-115">For example, a database field may contain `true` or `false`, or it may contain no value at all, that is, `NULL`.</span></span> <span data-ttu-id="bb53d-116">In questo scenario è possibile utilizzare il tipo `bool?`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-116">You can use the `bool?` type in that scenario.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="bb53d-117">Dichiarazione e assegnazione</span><span class="sxs-lookup"><span data-stu-id="bb53d-117">Declaration and assignment</span></span>

<span data-ttu-id="bb53d-118">Poiché un tipo valore è convertibile in modo implicito nel tipo di valore nullable corrispondente, è possibile assegnare un valore a una variabile di un tipo di valore nullable come per il tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="bb53d-118">As a value type is implicitly convertible to the corresponding nullable value type, you can assign a value to a variable of a nullable value type as you would do that for its underlying value type.</span></span> <span data-ttu-id="bb53d-119">È anche possibile assegnare il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-119">You also can assign the `null` value.</span></span> <span data-ttu-id="bb53d-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bb53d-120">For example:</span></span>

[!code-csharp[declare and assign](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Declaration)]

<span data-ttu-id="bb53d-121">Il valore predefinito di un tipo di valore Nullable rappresenta `null`, ovvero un'istanza la cui proprietà <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-121">The default value of a nullable value type represents `null`, that is, it's an instance whose <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> property returns `false`.</span></span>

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a><span data-ttu-id="bb53d-122">Esame di un'istanza di un tipo di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-122">Examination of an instance of a nullable value type</span></span>

<span data-ttu-id="bb53d-123">A partire C# da 7,0, è possibile usare l' [operatore`is` con un modello di tipo](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) per esaminare un'istanza di un tipo di valore Nullable per `null` e recuperare un valore di un tipo sottostante:</span><span class="sxs-lookup"><span data-stu-id="bb53d-123">Beginning with C# 7.0, you can use the [`is` operator with a type pattern](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) to both examine an instance of a nullable value type for `null` and retrieve a value of an underlying type:</span></span>

[!code-csharp-interactive[use pattern matching](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#PatternMatching)]

<span data-ttu-id="bb53d-124">Per esaminare e ottenere un valore di una variabile di tipo valore Nullable, è sempre possibile usare le proprietà di sola lettura seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb53d-124">You always can use the following read-only properties to examine and get a value of a nullable value type variable:</span></span>

- <span data-ttu-id="bb53d-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo di valore nullable ha un valore del tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="bb53d-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable value type has a value of its underlying type.</span></span>

- <span data-ttu-id="bb53d-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="bb53d-127">Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-127">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="bb53d-128">Nell'esempio seguente viene utilizzata la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarlo:</span><span class="sxs-lookup"><span data-stu-id="bb53d-128">The following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#HasValue)]

<span data-ttu-id="bb53d-129">È anche possibile confrontare una variabile di un tipo di valore nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bb53d-129">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="bb53d-130">Conversione da un tipo di valore Nullable a un tipo sottostante</span><span class="sxs-lookup"><span data-stu-id="bb53d-130">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="bb53d-131">Se si desidera assegnare un valore di un tipo di valore Nullable a una variabile di tipo valore non nullable, potrebbe essere necessario specificare il valore da assegnare al posto di `null`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-131">If you want to assign a value of a nullable value type to a non-nullable value type variable, you might need to specify the value to be assigned in place of `null`.</span></span> <span data-ttu-id="bb53d-132">Usare l' [operatore di Unione null `??`](../operators/null-coalescing-operator.md) a tale scopo. è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> per lo stesso scopo:</span><span class="sxs-lookup"><span data-stu-id="bb53d-132">Use the [null-coalescing operator `??`](../operators/null-coalescing-operator.md) to do that (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method for the same purpose):</span></span>

[!code-csharp-interactive[?? operator](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#NullCoalescing)]

<span data-ttu-id="bb53d-133">Se si desidera utilizzare il valore [predefinito](default-values.md) del tipo di valore sottostante al posto di `null`, utilizzare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-133">If you want to use the [default](default-values.md) value of the underlying value type in place of `null`, use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bb53d-134">È anche possibile eseguire il cast esplicito di un tipo di valore Nullable a un tipo non nullable, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bb53d-134">You also can explicitly cast a nullable value type to a non-nullable type, as the following example shows:</span></span>

[!code-csharp[explicit cast](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Cast)]

<span data-ttu-id="bb53d-135">In fase di esecuzione, se il valore di un tipo di valore Nullable è `null`, il cast esplicito genera un'<xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-135">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="bb53d-136">Un tipo di valore non nullable `T` è convertibile in modo implicito nel tipo di valore nullable corrispondente `T?`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-136">A non-nullable value type `T` is implicitly convertible to the corresponding nullable value type `T?`.</span></span>

## <a name="lifted-operators"></a><span data-ttu-id="bb53d-137">Operatori rimossi</span><span class="sxs-lookup"><span data-stu-id="bb53d-137">Lifted operators</span></span>

<span data-ttu-id="bb53d-138">Gli operatori unari e binari predefiniti o gli operatori di overload supportati da un tipo di valore `T` sono supportati anche dal tipo di valore nullable corrispondente `T?`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-138">The predefined unary and binary operators or any overloaded operators that are supported by a value type `T` are also supported by the corresponding nullable value type `T?`.</span></span> <span data-ttu-id="bb53d-139">Questi operatori, noti anche come *operatori lifted*, producono `null` se uno o entrambi gli operandi sono `null`; in caso contrario, l'operatore utilizza i valori contenuti degli operandi per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="bb53d-139">These operators, also known as *lifted operators*, produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values of its operands to calculate the result.</span></span> <span data-ttu-id="bb53d-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bb53d-140">For example:</span></span>

[!code-csharp[lifted operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> <span data-ttu-id="bb53d-141">Per il tipo di `bool?`, gli operatori `&` e `|` predefiniti non seguono le regole descritte in questa sezione: il risultato di una valutazione dell'operatore può essere diverso da null anche se uno degli operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-141">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="bb53d-142">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="bb53d-142">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="bb53d-143">Per gli [operatori di confronto](../operators/comparison-operators.md) `<`, `>`, `<=`e `>=`, se uno o entrambi gli operandi sono `null`, il risultato sarà `false`; in caso contrario, vengono confrontati i valori contenuti degli operandi.</span><span class="sxs-lookup"><span data-stu-id="bb53d-143">For the [comparison operators](../operators/comparison-operators.md) `<`, `>`, `<=`, and `>=`, if one or both operands are `null`, the result is `false`; otherwise the contained values of operands are compared.</span></span> <span data-ttu-id="bb53d-144">Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-144">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="bb53d-145">L'esempio seguente mostra che 10</span><span class="sxs-lookup"><span data-stu-id="bb53d-145">The following example shows that 10 is</span></span>

- <span data-ttu-id="bb53d-146">non è maggiore o uguale a `null`</span><span class="sxs-lookup"><span data-stu-id="bb53d-146">neither greater than or equal to `null`</span></span>
- <span data-ttu-id="bb53d-147">né minore di `null`</span><span class="sxs-lookup"><span data-stu-id="bb53d-147">nor less than `null`</span></span>

[!code-csharp-interactive[relational and equality operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#ComparisonOperators)]

<span data-ttu-id="bb53d-148">Nell'esempio precedente viene inoltre illustrato che un confronto di uguaglianza tra due istanze di tipi di valore nullable che sono entrambe `null` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="bb53d-148">The preceding example also shows that an equality comparison of two nullable value type instances that are both `null` evaluates to `true`.</span></span>

<span data-ttu-id="bb53d-149">Se esiste una [conversione definita dall'utente](../operators/user-defined-conversion-operators.md) tra due tipi di valore, è possibile usare la stessa conversione anche tra i tipi di valore nullable corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="bb53d-149">If there exists a [user-defined conversion](../operators/user-defined-conversion-operators.md) between two value types, the same conversion can also be used between the corresponding nullable value types.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="bb53d-150">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="bb53d-150">Boxing and unboxing</span></span>

<span data-ttu-id="bb53d-151">Un'istanza di un tipo di valore Nullable `T?` viene [boxed](../../programming-guide/types/boxing-and-unboxing.md) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bb53d-151">An instance of a nullable value type `T?` is [boxed](../../programming-guide/types/boxing-and-unboxing.md) as follows:</span></span>

- <span data-ttu-id="bb53d-152">Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="bb53d-152">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="bb53d-153">Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, il valore corrispondente del tipo di valore sottostante `T` è boxed, non l'istanza di <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-153">If <xref:System.Nullable%601.HasValue%2A> returns `true`, the corresponding value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="bb53d-154">È possibile eseguire l'unboxing di un valore boxed di un tipo di valore `T` al tipo di valore nullable corrispondente `T?`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bb53d-154">You can unbox a boxed value of a value type `T` to the corresponding nullable value type `T?`, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a><span data-ttu-id="bb53d-155">Come identificare un tipo di valore Nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-155">How to identify a nullable value type</span></span>

<span data-ttu-id="bb53d-156">Nell'esempio seguente viene illustrato come determinare se un'istanza di <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo di valore Nullable costruito, ovvero il tipo di <xref:System.Nullable%601?displayProperty=nameWithType> con un parametro di tipo specificato `T`:</span><span class="sxs-lookup"><span data-stu-id="bb53d-156">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a constructed nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsTypeNullable)]

<span data-ttu-id="bb53d-157">Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) per creare un'istanza di <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-157">As the example shows, you use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> instance.</span></span>

<span data-ttu-id="bb53d-158">Per determinare se un'istanza è di un tipo di valore Nullable, non usare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza di <xref:System.Type> da testare con il codice precedente.</span><span class="sxs-lookup"><span data-stu-id="bb53d-158">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="bb53d-159">Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> su un'istanza di un tipo di valore Nullable, l'istanza viene sottoposta a [boxing](#boxing-and-unboxing) <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="bb53d-159">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="bb53d-160">Poiché la conversione boxing di un'istanza non null di un tipo di valore Nullable equivale alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un'istanza di <xref:System.Type> che rappresenta il tipo sottostante di un tipo di valore Nullable:</span><span class="sxs-lookup"><span data-stu-id="bb53d-160">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> instance that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#GetType)]

<span data-ttu-id="bb53d-161">Inoltre, non usare l'operatore [is](../operators/type-testing-and-cast.md#is-operator) per determinare se un'istanza è un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="bb53d-161">Also, don't use the [is](../operators/type-testing-and-cast.md#is-operator) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="bb53d-162">Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di un'istanza del tipo di valore nullable e l'istanza del tipo sottostante con l'operatore `is`:</span><span class="sxs-lookup"><span data-stu-id="bb53d-162">As the following example shows, you cannot distinguish types of a nullable value type instance and its underlying type instance with the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsOperator)]

<span data-ttu-id="bb53d-163">È possibile utilizzare il codice presentato nell'esempio seguente per determinare se un'istanza è un tipo di valore Nullable:</span><span class="sxs-lookup"><span data-stu-id="bb53d-163">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> <span data-ttu-id="bb53d-164">I metodi descritti in questa sezione non sono applicabili in caso di [tipi di riferimento Nullable](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="bb53d-164">The methods described in this section are not applicable in the case of [nullable reference types](../../nullable-references.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb53d-165">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bb53d-165">C# language specification</span></span>

<span data-ttu-id="bb53d-166">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bb53d-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bb53d-167">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-167">Nullable types</span></span>](~/_csharplang/spec/types.md#nullable-types)
- [<span data-ttu-id="bb53d-168">Operatori rimossi</span><span class="sxs-lookup"><span data-stu-id="bb53d-168">Lifted operators</span></span>](~/_csharplang/spec/expressions.md#lifted-operators)
- [<span data-ttu-id="bb53d-169">Conversioni implicite Nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-169">Implicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [<span data-ttu-id="bb53d-170">Conversioni esplicite Nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-170">Explicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [<span data-ttu-id="bb53d-171">Operatori di conversione accurati</span><span class="sxs-lookup"><span data-stu-id="bb53d-171">Lifted conversion operators</span></span>](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a><span data-ttu-id="bb53d-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb53d-172">See also</span></span>

- [<span data-ttu-id="bb53d-173">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bb53d-173">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bb53d-174">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="bb53d-174">What exactly does 'lifted' mean?</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bb53d-175">Tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="bb53d-175">Nullable reference types</span></span>](../../nullable-references.md)
