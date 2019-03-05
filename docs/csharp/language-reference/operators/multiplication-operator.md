---
title: '* Operatore * - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977344"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="54f1a-102">Operatore \* (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="54f1a-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="54f1a-103">L'operatore `*` è supportato in due forme: un operatore unario di riferimento indiretto a puntatore o un operatore di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="54f1a-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="54f1a-104">Operatore di riferimento indiretto a puntatore</span><span class="sxs-lookup"><span data-stu-id="54f1a-104">Pointer indirection operator</span></span>

<span data-ttu-id="54f1a-105">Usare l'operatore unario `*` per ottenere la variabile a cui punta un operando di un tipo di puntatore.</span><span class="sxs-lookup"><span data-stu-id="54f1a-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="54f1a-106">Per altre informazioni, vedere [Procedura: Ottenere il valore di una variabile puntatore](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span><span class="sxs-lookup"><span data-stu-id="54f1a-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="54f1a-107">L'operatore di riferimento indiretto a puntatore `*` richiede il contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="54f1a-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="54f1a-108">Operatore di moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="54f1a-108">Multiplication operator</span></span>

<span data-ttu-id="54f1a-109">Per i tipi numerici, l'operatore `*` calcola il prodotto dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="54f1a-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="54f1a-110">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="54f1a-110">Operator overloadability</span></span>

<span data-ttu-id="54f1a-111">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) di un operatore `*` binario.</span><span class="sxs-lookup"><span data-stu-id="54f1a-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="54f1a-112">Quando viene eseguito l'overload di un operatore `*`, viene anche aggiunto l'[operatore di assegnazione di moltiplicazione](multiplication-assignment-operator.md) `*=`.</span><span class="sxs-lookup"><span data-stu-id="54f1a-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="54f1a-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="54f1a-113">C# language specification</span></span>

<span data-ttu-id="54f1a-114">Per altre informazioni, vedere le sezioni [Riferimento indiretto a puntatore](~/_csharplang/spec/unsafe-code.md#pointer-indirection) e [Operatore di moltiplicazione](~/_csharplang/spec/expressions.md#multiplication-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="54f1a-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54f1a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f1a-115">See also</span></span>

- [<span data-ttu-id="54f1a-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="54f1a-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="54f1a-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="54f1a-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="54f1a-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="54f1a-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="54f1a-119">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="54f1a-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)