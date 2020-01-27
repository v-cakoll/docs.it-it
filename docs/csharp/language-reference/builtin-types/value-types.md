---
title: Value types - C# reference
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6b96d65f657f2af1af5c9a245e956640ee06260e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748517"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="87573-102">Value types (C# reference)</span><span class="sxs-lookup"><span data-stu-id="87573-102">Value types (C# reference)</span></span>

<span data-ttu-id="87573-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span><span class="sxs-lookup"><span data-stu-id="87573-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="87573-104">A variable of a value type contains an instance of the type.</span><span class="sxs-lookup"><span data-stu-id="87573-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="87573-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span><span class="sxs-lookup"><span data-stu-id="87573-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="87573-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, or returning a method result, variable values are copied.</span><span class="sxs-lookup"><span data-stu-id="87573-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, or returning a method result, variable values are copied.</span></span> <span data-ttu-id="87573-107">In the case of value-type variables, the corresponding type instances are copied.</span><span class="sxs-lookup"><span data-stu-id="87573-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="87573-108">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="87573-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="87573-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span><span class="sxs-lookup"><span data-stu-id="87573-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="87573-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span><span class="sxs-lookup"><span data-stu-id="87573-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="87573-111">Both the copy and original value-type instance have access to the same reference-type instance.</span><span class="sxs-lookup"><span data-stu-id="87573-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="87573-112">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="87573-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="87573-113">To make your code less error-prone and more robust, define and use immutable value types.</span><span class="sxs-lookup"><span data-stu-id="87573-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="87573-114">This article uses mutable value types only for demonstration purposes.</span><span class="sxs-lookup"><span data-stu-id="87573-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="87573-115">Kinds of value types</span><span class="sxs-lookup"><span data-stu-id="87573-115">Kinds of value types</span></span>

<span data-ttu-id="87573-116">A value type can be one of the two following kinds:</span><span class="sxs-lookup"><span data-stu-id="87573-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="87573-117">a [structure type](../keywords/struct.md), which encapsulates data and related functionality</span><span class="sxs-lookup"><span data-stu-id="87573-117">a [structure type](../keywords/struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="87573-118">un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte</span><span class="sxs-lookup"><span data-stu-id="87573-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="87573-119">Un [tipo di valore nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="87573-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="87573-120">Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="87573-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="87573-121">Tipi di valore predefiniti</span><span class="sxs-lookup"><span data-stu-id="87573-121">Built-in value types</span></span>

<span data-ttu-id="87573-122">C#in sono disponibili i tipi di valore predefiniti seguenti, noti anche come *tipi semplici*:</span><span class="sxs-lookup"><span data-stu-id="87573-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="87573-123">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="87573-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="87573-124">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="87573-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="87573-125">[bool](bool.md) che rappresenta un valore booleano</span><span class="sxs-lookup"><span data-stu-id="87573-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="87573-126">[char](char.md) che rappresenta un carattere UTF-16 Unicode</span><span class="sxs-lookup"><span data-stu-id="87573-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="87573-127">Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="87573-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="87573-128">È possibile utilizzare valori letterali per fornire un valore di un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="87573-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="87573-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="87573-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="87573-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="87573-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="87573-131">Non è possibile avere costanti di altri tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="87573-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="87573-132">Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="87573-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="87573-133">A partire C# da 7,0 C# , supporta le [Tuple di valori](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="87573-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="87573-134">Una tupla di valori è un tipo di valore, ma non un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="87573-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="87573-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="87573-135">C# language specification</span></span>

<span data-ttu-id="87573-136">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="87573-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="87573-137">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="87573-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="87573-138">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="87573-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="87573-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="87573-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="87573-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87573-140">See also</span></span>

- [<span data-ttu-id="87573-141">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="87573-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="87573-142">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="87573-142">Reference types</span></span>](../keywords/reference-types.md)
