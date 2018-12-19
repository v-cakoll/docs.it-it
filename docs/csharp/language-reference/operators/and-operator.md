---
title: Operatore &amp; - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: a799c0e37d6607e8ff72ab984ff5e540a4e11063
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236375"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="5b11a-102">Operatore &amp; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5b11a-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="5b11a-103">L'operatore `&` è supportato in due forme: un operatore address-of unario o un operatore logico binario.</span><span class="sxs-lookup"><span data-stu-id="5b11a-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="5b11a-104">Operatore address-of unario</span><span class="sxs-lookup"><span data-stu-id="5b11a-104">Unary address-of operator</span></span>

<span data-ttu-id="5b11a-105">L'operatore `&` unario restituisce l'indirizzo del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="5b11a-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="5b11a-106">Per altre informazioni, vedere [Procedura: Ottenere l'indirizzo di una variabile](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5b11a-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="5b11a-107">L'operatore address-of `&` richiede un contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="5b11a-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="5b11a-108">Operatore AND logico bit per bit intero</span><span class="sxs-lookup"><span data-stu-id="5b11a-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="5b11a-109">Per i tipi interi, l'operatore `&` calcola l'AND logico bit per bit dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="5b11a-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="5b11a-110">L'esempio precedente usa i valori letterali binari [introdotti in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) e [migliorati in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="5b11a-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="5b11a-111">Poiché le operazioni sui tipi interi sono in genere consentite sui tipi di enumerazione, l'operatore `&` supporta anche gli operandi [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="5b11a-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="5b11a-112">Operatore AND logico booleano</span><span class="sxs-lookup"><span data-stu-id="5b11a-112">Boolean logical AND operator</span></span>

<span data-ttu-id="5b11a-113">Per gli operandi [bool](../keywords/bool.md), l'operatore `&` calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="5b11a-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="5b11a-114">Il risultato di `x & y` è `true` se `x` e `y` sono `true`.</span><span class="sxs-lookup"><span data-stu-id="5b11a-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="5b11a-115">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="5b11a-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="5b11a-116">L'operatore `&` valuta entrambi gli operandi anche se il primo operando restituisce `false`, in modo che il risultato sia `false` indipendentemente dal valore del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="5b11a-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="5b11a-117">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="5b11a-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="5b11a-118">L'[operatore AND condizionale](conditional-and-operator.md) `&&` calcola l'AND logico dei relativi operandi, ma valuta il secondo operando solo se il primo operando restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="5b11a-118">The [conditional AND operator](conditional-and-operator.md) `&&` also computes the logical AND of its operands, but evaluates the second operand only if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="5b11a-119">Per gli operandi bool nullable, il comportamento dell'operatore `&` è coerente con la logica a tre valori di SQL.</span><span class="sxs-lookup"><span data-stu-id="5b11a-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="5b11a-120">Per altre informazioni, vedere la sezione [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="5b11a-120">For more information, see the [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5b11a-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="5b11a-121">Operator overloadability</span></span>

<span data-ttu-id="5b11a-122">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `&` binario.</span><span class="sxs-lookup"><span data-stu-id="5b11a-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="5b11a-123">Quando viene eseguito l'overload di un operatore `&` binario, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione AND](and-assignment-operator.md) `&=`.</span><span class="sxs-lookup"><span data-stu-id="5b11a-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5b11a-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5b11a-124">C# language specification</span></span>

<span data-ttu-id="5b11a-125">Per altre informazioni, vedere le sezioni [Operatore address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) e [Operatori logici](~/_csharplang/spec/expressions.md#logical-operators) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5b11a-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b11a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b11a-126">See also</span></span>

- [<span data-ttu-id="5b11a-127">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5b11a-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5b11a-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5b11a-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5b11a-129">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5b11a-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5b11a-130">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="5b11a-130">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="5b11a-131">Operatore |</span><span class="sxs-lookup"><span data-stu-id="5b11a-131">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="5b11a-132">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="5b11a-132">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="5b11a-133">Operatore ~</span><span class="sxs-lookup"><span data-stu-id="5b11a-133">~ operator</span></span>](bitwise-complement-operator.md)
- [<span data-ttu-id="5b11a-134">Operatore &&</span><span class="sxs-lookup"><span data-stu-id="5b11a-134">&& operator</span></span>](conditional-and-operator.md)
