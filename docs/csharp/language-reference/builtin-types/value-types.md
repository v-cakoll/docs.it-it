---
title: Tipi di valore-riferimenti per C#
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 0a05b2b0f3f2a8377fdba6144b8aeb12bdee1086
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86172951"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="c3762-102">Tipi di valore (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c3762-102">Value types (C# reference)</span></span>

<span data-ttu-id="c3762-103">I tipi di *valore* e i [tipi di riferimento](../keywords/reference-types.md) sono le due categorie principali di tipi C#.</span><span class="sxs-lookup"><span data-stu-id="c3762-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="c3762-104">Una variabile di un tipo di valore contiene un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="c3762-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="c3762-105">Questo comportamento è diverso da una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="c3762-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="c3762-106">Per impostazione predefinita, durante l' [assegnazione](../operators/assignment-operator.md), passando un argomento a un metodo e restituendo il risultato di un metodo, vengono copiati i valori delle variabili.</span><span class="sxs-lookup"><span data-stu-id="c3762-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="c3762-107">Nel caso di variabili di tipo valore, vengono copiate le istanze del tipo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c3762-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="c3762-108">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="c3762-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="c3762-109">Come illustrato nell'esempio precedente, le operazioni su una variabile di tipo valore influiscono solo su tale istanza del tipo di valore, archiviata nella variabile.</span><span class="sxs-lookup"><span data-stu-id="c3762-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="c3762-110">Se un tipo di valore contiene un membro dati di un tipo di riferimento, quando viene copiata un'istanza del tipo di valore viene copiato solo il riferimento all'istanza del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c3762-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="c3762-111">Sia la copia che l'istanza del tipo di valore originale hanno accesso alla stessa istanza del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c3762-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="c3762-112">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="c3762-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="c3762-113">Per rendere il codice meno soggetto a errori e più affidabile, definire e utilizzare tipi di valore non modificabili.</span><span class="sxs-lookup"><span data-stu-id="c3762-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="c3762-114">Questo articolo usa tipi di valore modificabili solo a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="c3762-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="c3762-115">Tipi di tipi di valore</span><span class="sxs-lookup"><span data-stu-id="c3762-115">Kinds of value types</span></span>

<span data-ttu-id="c3762-116">Un tipo di valore può essere uno dei due tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3762-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="c3762-117">[tipo di struttura](struct.md)che incapsula i dati e la funzionalità correlata</span><span class="sxs-lookup"><span data-stu-id="c3762-117">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="c3762-118">un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte</span><span class="sxs-lookup"><span data-stu-id="c3762-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="c3762-119">Un [tipo di valore Nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c3762-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="c3762-120">Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="c3762-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="c3762-121">Tipi di valore predefiniti</span><span class="sxs-lookup"><span data-stu-id="c3762-121">Built-in value types</span></span>

<span data-ttu-id="c3762-122">In C# sono disponibili i seguenti tipi di valore predefiniti, noti anche come *tipi semplici*:</span><span class="sxs-lookup"><span data-stu-id="c3762-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="c3762-123">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="c3762-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="c3762-124">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="c3762-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="c3762-125">[bool](bool.md) che rappresenta un valore booleano</span><span class="sxs-lookup"><span data-stu-id="c3762-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="c3762-126">[char](char.md) che rappresenta un carattere UTF-16 Unicode</span><span class="sxs-lookup"><span data-stu-id="c3762-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="c3762-127">Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="c3762-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="c3762-128">È possibile utilizzare valori letterali per fornire un valore di un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="c3762-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="c3762-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="c3762-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="c3762-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="c3762-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="c3762-131">Non è possibile avere costanti di altri tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="c3762-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="c3762-132">Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c3762-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="c3762-133">A partire da C# 7,0, C# supporta le [Tuple di valori](value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="c3762-133">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="c3762-134">Una tupla di valori è un tipo di valore, ma non un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="c3762-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c3762-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c3762-135">C# language specification</span></span>

<span data-ttu-id="c3762-136">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c3762-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c3762-137">Tipi di valori</span><span class="sxs-lookup"><span data-stu-id="c3762-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="c3762-138">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="c3762-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="c3762-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="c3762-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="c3762-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3762-140">See also</span></span>

- [<span data-ttu-id="c3762-141">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="c3762-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="c3762-142">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="c3762-142">Reference types</span></span>](../keywords/reference-types.md)
