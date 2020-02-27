---
title: Tipi valore- C# riferimento
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 76f4a3ed929e3ac8e3e6cc74158e75af7a6c8cf2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625947"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="7cd20-102">Tipi di valoreC# (riferimento)</span><span class="sxs-lookup"><span data-stu-id="7cd20-102">Value types (C# reference)</span></span>

<span data-ttu-id="7cd20-103">I tipi di *valore* e i [tipi di riferimento](../keywords/reference-types.md) sono le C# due categorie principali di tipi.</span><span class="sxs-lookup"><span data-stu-id="7cd20-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="7cd20-104">Una variabile di un tipo di valore contiene un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="7cd20-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="7cd20-105">Questo comportamento è diverso da una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="7cd20-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="7cd20-106">Per impostazione predefinita, durante l' [assegnazione](../operators/assignment-operator.md), passando un argomento a un metodo e restituendo il risultato di un metodo, vengono copiati i valori delle variabili.</span><span class="sxs-lookup"><span data-stu-id="7cd20-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="7cd20-107">Nel caso di variabili di tipo valore, vengono copiate le istanze del tipo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7cd20-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="7cd20-108">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="7cd20-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="7cd20-109">Come illustrato nell'esempio precedente, le operazioni su una variabile di tipo valore influiscono solo su tale istanza del tipo di valore, archiviata nella variabile.</span><span class="sxs-lookup"><span data-stu-id="7cd20-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="7cd20-110">Se un tipo di valore contiene un membro dati di un tipo di riferimento, quando viene copiata un'istanza del tipo di valore viene copiato solo il riferimento all'istanza del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7cd20-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="7cd20-111">Sia la copia che l'istanza del tipo di valore originale hanno accesso alla stessa istanza del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7cd20-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="7cd20-112">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="7cd20-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="7cd20-113">Per rendere il codice meno soggetto a errori e più affidabile, definire e utilizzare tipi di valore non modificabili.</span><span class="sxs-lookup"><span data-stu-id="7cd20-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="7cd20-114">Questo articolo usa tipi di valore modificabili solo a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="7cd20-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="7cd20-115">Tipi di tipi di valore</span><span class="sxs-lookup"><span data-stu-id="7cd20-115">Kinds of value types</span></span>

<span data-ttu-id="7cd20-116">Un tipo di valore può essere uno dei due tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cd20-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="7cd20-117">[tipo di struttura](struct.md)che incapsula i dati e la funzionalità correlata</span><span class="sxs-lookup"><span data-stu-id="7cd20-117">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="7cd20-118">un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte</span><span class="sxs-lookup"><span data-stu-id="7cd20-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="7cd20-119">Un [tipo di valore nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="7cd20-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="7cd20-120">Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="7cd20-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="7cd20-121">Tipi di valore predefiniti</span><span class="sxs-lookup"><span data-stu-id="7cd20-121">Built-in value types</span></span>

<span data-ttu-id="7cd20-122">C#in sono disponibili i tipi di valore predefiniti seguenti, noti anche come *tipi semplici*:</span><span class="sxs-lookup"><span data-stu-id="7cd20-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="7cd20-123">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="7cd20-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="7cd20-124">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="7cd20-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="7cd20-125">[bool](bool.md) che rappresenta un valore booleano</span><span class="sxs-lookup"><span data-stu-id="7cd20-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="7cd20-126">[char](char.md) che rappresenta un carattere UTF-16 Unicode</span><span class="sxs-lookup"><span data-stu-id="7cd20-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="7cd20-127">Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="7cd20-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="7cd20-128">È possibile utilizzare valori letterali per fornire un valore di un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="7cd20-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="7cd20-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="7cd20-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="7cd20-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="7cd20-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="7cd20-131">Non è possibile avere costanti di altri tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="7cd20-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="7cd20-132">Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7cd20-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="7cd20-133">A partire C# da 7,0 C# , supporta le [Tuple di valori](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="7cd20-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="7cd20-134">Una tupla di valori è un tipo di valore, ma non un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="7cd20-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7cd20-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7cd20-135">C# language specification</span></span>

<span data-ttu-id="7cd20-136">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="7cd20-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="7cd20-137">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="7cd20-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="7cd20-138">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="7cd20-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="7cd20-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="7cd20-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="7cd20-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd20-140">See also</span></span>

- [<span data-ttu-id="7cd20-141">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7cd20-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="7cd20-142">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="7cd20-142">Reference types</span></span>](../keywords/reference-types.md)
