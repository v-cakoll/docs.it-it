---
title: Operatore ~ (Riferimenti per C#)
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 1bcb07c5639a098e3a8c566e92083ca0d48efb81
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153215"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7a839-102">Operatore ~ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7a839-102">~ Operator (C# Reference)</span></span>

<span data-ttu-id="7a839-103">L'operatore di complemento bit per bit `~` è un operatore unario che produce un complemento bit per bit del suo operando invertendo ogni bit.</span><span class="sxs-lookup"><span data-stu-id="7a839-103">The bitwise complement operator `~` is a unary operator that produces a bitwise complement of its operand by reversing each bit.</span></span> <span data-ttu-id="7a839-104">Tutti i tipi integer supportano l'operatore `~`.</span><span class="sxs-lookup"><span data-stu-id="7a839-104">All integer types support the `~` operator.</span></span>

> [!NOTE]
> <span data-ttu-id="7a839-105">È possibile anche usare il simbolo `~` per dichiarare i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="7a839-105">The `~` symbol is also used to declare finalizers.</span></span> <span data-ttu-id="7a839-106">Per altre informazioni, vedere [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="7a839-106">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

<span data-ttu-id="7a839-107">Nell'esempio seguente viene illustrato l'uso dell'operatore `~`:</span><span class="sxs-lookup"><span data-stu-id="7a839-107">The following example demonstrates the usage of the `~` operator:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> <span data-ttu-id="7a839-108">L'esempio precedente usa i valori letterali binari [introdotti in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) e [migliorati in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="7a839-108">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced  in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7a839-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="7a839-109">Operator overloadability</span></span>

<span data-ttu-id="7a839-110">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `~`.</span><span class="sxs-lookup"><span data-stu-id="7a839-110">User-defined types can [overload](../keywords/operator.md) the `~` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7a839-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7a839-111">C# language specification</span></span>

<span data-ttu-id="7a839-112">Per altre informazioni, vedere la sezione [Operatore di complemento bit per bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator) nelle [specifiche del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="7a839-112">For more information, see the [Bitwise complement operator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7a839-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a839-113">See also</span></span>

- [<span data-ttu-id="7a839-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7a839-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7a839-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7a839-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7a839-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7a839-116">C# Operators</span></span>](index.md)
- [<span data-ttu-id="7a839-117">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="7a839-117">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="7a839-118">Operatore &</span><span class="sxs-lookup"><span data-stu-id="7a839-118">& operator</span></span>](and-operator.md)
- [<span data-ttu-id="7a839-119">Operatore |</span><span class="sxs-lookup"><span data-stu-id="7a839-119">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="7a839-120">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="7a839-120">^ operator</span></span>](xor-operator.md)
