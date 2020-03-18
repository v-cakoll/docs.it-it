---
title: Tipi di valore - Riferimenti per C
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 406e5b8bbe0802146a65bb4b9a053e753a7827ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399581"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="4d70a-102">Tipi di valore (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="4d70a-102">Value types (C# reference)</span></span>

<span data-ttu-id="4d70a-103">*I tipi di valore* e i tipi di [riferimento](../keywords/reference-types.md) sono le due categorie principali di tipi C.</span><span class="sxs-lookup"><span data-stu-id="4d70a-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="4d70a-104">Una variabile di un tipo di valore contiene un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4d70a-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="4d70a-105">Questo è diverso da una variabile di un tipo di riferimento, che contiene un riferimento a un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4d70a-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="4d70a-106">Per impostazione predefinita, durante [l'assegnazione](../operators/assignment-operator.md), il passaggio di un argomento a un metodo e la restituzione di un risultato del metodo vengono copiati i valori delle variabili.</span><span class="sxs-lookup"><span data-stu-id="4d70a-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="4d70a-107">Nel caso di variabili di tipo valore, vengono copiate le istanze di tipo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4d70a-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="4d70a-108">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="4d70a-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="4d70a-109">Come illustrato nell'esempio precedente, le operazioni su una variabile di tipo valore influiscono solo sull'istanza del tipo di valore, archiviata nella variabile.</span><span class="sxs-lookup"><span data-stu-id="4d70a-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="4d70a-110">Se un tipo di valore contiene un membro dati di un tipo di riferimento, solo il riferimento all'istanza del tipo di riferimento viene copiato quando viene copiata un'istanza di tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="4d70a-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="4d70a-111">Sia l'istanza di tipo di valore copia che quella originale hanno accesso alla stessa istanza del tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4d70a-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="4d70a-112">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="4d70a-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="4d70a-113">Per rendere il codice meno soggetto a errori e più affidabile, definire e usare tipi di valore non modificabili.</span><span class="sxs-lookup"><span data-stu-id="4d70a-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="4d70a-114">In questo articolo vengono utilizzati tipi di valore modificabili solo a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="4d70a-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="4d70a-115">Tipi di tipi di valore</span><span class="sxs-lookup"><span data-stu-id="4d70a-115">Kinds of value types</span></span>

<span data-ttu-id="4d70a-116">Un tipo di valore può essere uno dei due tipi seguenti:A value type can be one of the two following kinds:</span><span class="sxs-lookup"><span data-stu-id="4d70a-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="4d70a-117">un [tipo di struttura](struct.md), che incapsula dati e funzionalità correlate</span><span class="sxs-lookup"><span data-stu-id="4d70a-117">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="4d70a-118">un tipo di [enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte</span><span class="sxs-lookup"><span data-stu-id="4d70a-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="4d70a-119">Un tipo `T?` di [valore nullable](nullable-value-types.md) rappresenta `T` tutti i valori del tipo di valore sottostante e un valore [null](../keywords/null.md) aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="4d70a-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="4d70a-120">Non è `null` possibile assegnare a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="4d70a-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="4d70a-121">Tipi di valore incorporati</span><span class="sxs-lookup"><span data-stu-id="4d70a-121">Built-in value types</span></span>

<span data-ttu-id="4d70a-122">In C' sono disponibili i seguenti tipi di valore incorporati, noti anche come *tipi semplici:*</span><span class="sxs-lookup"><span data-stu-id="4d70a-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="4d70a-123">Tipi numerici integrali</span><span class="sxs-lookup"><span data-stu-id="4d70a-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="4d70a-124">Tipi numerici a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="4d70a-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="4d70a-125">[bool](bool.md) che rappresenta un valore booleano</span><span class="sxs-lookup"><span data-stu-id="4d70a-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="4d70a-126">[char](char.md) che rappresenta un carattere Unicode UTF-16</span><span class="sxs-lookup"><span data-stu-id="4d70a-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="4d70a-127">Tutti i tipi semplici sono tipi di struttura e differiscono da altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:All simple types are types and differ from other structure types in that they permit certain additional operations:</span><span class="sxs-lookup"><span data-stu-id="4d70a-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="4d70a-128">È possibile utilizzare valori letterali per fornire un valore di un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="4d70a-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="4d70a-129">Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="4d70a-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="4d70a-130">È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="4d70a-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="4d70a-131">Non è possibile avere costanti di altri tipi di struttura.</span><span class="sxs-lookup"><span data-stu-id="4d70a-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="4d70a-132">Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4d70a-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="4d70a-133">A partire dalla versione 7.0 di C, C'è supporta le tuple di [valori](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="4d70a-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="4d70a-134">Una tupla di valori è un tipo di valore, ma non un tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="4d70a-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4d70a-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4d70a-135">C# language specification</span></span>

<span data-ttu-id="4d70a-136">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="4d70a-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4d70a-137">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="4d70a-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="4d70a-138">Tipi semplici</span><span class="sxs-lookup"><span data-stu-id="4d70a-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="4d70a-139">Variabili</span><span class="sxs-lookup"><span data-stu-id="4d70a-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="4d70a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d70a-140">See also</span></span>

- [<span data-ttu-id="4d70a-141">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="4d70a-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="4d70a-142">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="4d70a-142">Reference types</span></span>](../keywords/reference-types.md)
