---
title: Utilizzo di tipi di valore C# Nullable-Guida alla programmazione
ms.custom: seodec18
description: Informazioni su come usare i C# tipi di valore Nullable
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396171"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="79547-103">Utilizzo di tipi di valoreC# Nullable (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="79547-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="79547-104">I tipi di valore nullable sono tipi che rappresentano tutti i valori di un tipo di valore sottostante `T` e un valore [null](../../language-reference/keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="79547-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="79547-105">Per ulteriori informazioni, vedere l'argomento [tipi di valore Nullable](index.md) .</span><span class="sxs-lookup"><span data-stu-id="79547-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="79547-106">C#8,0 introduce la funzionalità dei tipi di riferimento Nullable.</span><span class="sxs-lookup"><span data-stu-id="79547-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="79547-107">Per altre informazioni, vedere [tipi di riferimento Nullable](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="79547-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="79547-108">I tipi di valore nullable sono disponibili a C# partire da 2.</span><span class="sxs-lookup"><span data-stu-id="79547-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="79547-109">È possibile fare riferimento a un tipo di valore nullable in uno dei seguenti formati intercambiabili: `Nullable<T>` o `T?`.</span><span class="sxs-lookup"><span data-stu-id="79547-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="79547-110">`T` deve essere un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="79547-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="79547-111">Dichiarazione e assegnazione</span><span class="sxs-lookup"><span data-stu-id="79547-111">Declaration and assignment</span></span>

<span data-ttu-id="79547-112">Poiché un tipo di valore può essere convertito in modo implicito nel tipo di valore nullable corrispondente, assegnare un valore a un tipo nullable come per il tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="79547-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="79547-113">È anche possibile assegnare il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="79547-113">You also can assign the `null` value.</span></span> <span data-ttu-id="79547-114">Esempio:</span><span class="sxs-lookup"><span data-stu-id="79547-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="79547-115">Esame di un valore di tipo nullable</span><span class="sxs-lookup"><span data-stu-id="79547-115">Examination of a nullable type value</span></span>

<span data-ttu-id="79547-116">Usare le proprietà di sola lettura seguenti per esaminare un'istanza di un tipo di valore Nullable per null e recuperare un valore di un tipo sottostante:</span><span class="sxs-lookup"><span data-stu-id="79547-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="79547-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo nullable contiene un valore del relativo tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="79547-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="79547-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="79547-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="79547-119">Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="79547-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="79547-120">Il codice nell'esempio seguente usa la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarla:</span><span class="sxs-lookup"><span data-stu-id="79547-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="79547-121">È anche possibile confrontare una variabile di un tipo di valore nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79547-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="79547-122">A partire C# da 7,0, è possibile usare i [criteri](../../pattern-matching.md) di ricerca per esaminare e ottenere un valore di un tipo di valore Nullable:</span><span class="sxs-lookup"><span data-stu-id="79547-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="79547-123">Conversione da un tipo di valore Nullable a un tipo sottostante</span><span class="sxs-lookup"><span data-stu-id="79547-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="79547-124">Se è necessario assegnare un valore di un tipo di valore Nullable a un tipo non nullable, usare l'operatore di Unione [null `??`](../../language-reference/operators/null-coalescing-operator.md) per specificare il valore da assegnare se un valore di un tipo di valore Nullable è null. è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> per eseguire questa operazione. :</span><span class="sxs-lookup"><span data-stu-id="79547-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="79547-125">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di un tipo di valore Nullable è `null` deve essere il valore predefinito del tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="79547-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="79547-126">È possibile eseguire il cast esplicito di un tipo di valore Nullable a un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="79547-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="79547-127">Esempio:</span><span class="sxs-lookup"><span data-stu-id="79547-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="79547-128">In fase di esecuzione, se il valore di un tipo di valore Nullable è `null`, il cast esplicito genera un'<xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="79547-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="79547-129">Un tipo valore non nullable viene convertito in modo implicito nel tipo nullable corrispondente.</span><span class="sxs-lookup"><span data-stu-id="79547-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="79547-130">Operatori</span><span class="sxs-lookup"><span data-stu-id="79547-130">Operators</span></span>

<span data-ttu-id="79547-131">Gli operatori unari e binari predefiniti e tutti gli operatori definiti dall'utente esistenti per i tipi di valore possono essere utilizzati anche dai tipi nullable corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="79547-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="79547-132">Questi operatori producono `null` se uno o entrambi gli operandi sono `null`; in caso contrario, l'operatore utilizza i valori contenuti per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="79547-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="79547-133">Esempio:</span><span class="sxs-lookup"><span data-stu-id="79547-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="79547-134">Per il tipo `bool?`, gli operatori `&` e `|` predefiniti non seguono le regole descritte in questa sezione: il risultato di una valutazione dell'operatore può essere diverso da null anche se uno degli operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="79547-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="79547-135">Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="79547-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="79547-136">Per gli operatori relazionali (`<`, `>`, `<=`, `>=`), se uno o entrambi gli operandi sono `null`, il risultato sarà `false`.</span><span class="sxs-lookup"><span data-stu-id="79547-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="79547-137">Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="79547-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="79547-138">L'esempio seguente mostra che 10</span><span class="sxs-lookup"><span data-stu-id="79547-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="79547-139">non è maggiore o uguale a `null`,</span><span class="sxs-lookup"><span data-stu-id="79547-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="79547-140">né minore di `null`.</span><span class="sxs-lookup"><span data-stu-id="79547-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="79547-141">Nell'esempio precedente viene inoltre illustrato che un confronto di uguaglianza tra due tipi valore nullable che sono entrambi null restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="79547-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="79547-142">Per altre informazioni, vedere la sezione [Operatori elevati](~/_csharplang/spec/expressions.md#lifted-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="79547-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="79547-143">Boxing e unboxing</span><span class="sxs-lookup"><span data-stu-id="79547-143">Boxing and unboxing</span></span>

<span data-ttu-id="79547-144">Un tipo valore nullable viene sottoposto a [boxing](../types/boxing-and-unboxing.md) in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="79547-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="79547-145">Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="79547-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="79547-146">Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, viene sottoposto a boxing un valore del tipo valore sottostante `T` e non l'istanza di <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="79547-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="79547-147">È possibile eseguire la conversione unboxing del tipo valore sottoposto a boxing nel tipo nullable corrispondente, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79547-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="79547-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79547-148">See also</span></span>

- [<span data-ttu-id="79547-149">Tipi valore nullable</span><span class="sxs-lookup"><span data-stu-id="79547-149">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="79547-150">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="79547-150">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
