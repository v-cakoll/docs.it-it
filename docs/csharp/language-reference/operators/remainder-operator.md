---
title: Operatore % - Riferimenti per C#
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: a5c12b6683e35cc1ec2d40446dd0ed068c3d2552
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236479"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1726d-102">Operatore % (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1726d-102">% Operator (C# Reference)</span></span>

<span data-ttu-id="1726d-103">L'operatore di resto `%` calcola il resto dopo aver diviso il primo operando per il secondo.</span><span class="sxs-lookup"><span data-stu-id="1726d-103">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

<span data-ttu-id="1726d-104">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `%`.</span><span class="sxs-lookup"><span data-stu-id="1726d-104">User-defined types can [overload](../keywords/operator.md) the `%` operator.</span></span> <span data-ttu-id="1726d-105">Quando `%` viene sottoposto a overload, anche l'[operatore di assegnazione di resto](remainder-assignment-operator.md) `%=` viene sottoposto implicitamente a overload.</span><span class="sxs-lookup"><span data-stu-id="1726d-105">When the `%` is overloaded, the [remainder assignment operator](remainder-assignment-operator.md) `%=` is also implicitly overloaded.</span></span>

<span data-ttu-id="1726d-106">Tutti i tipi numerici supportano l'operatore di resto.</span><span class="sxs-lookup"><span data-stu-id="1726d-106">All numeric types support the remainder operator.</span></span>

## <a name="integer-remainder"></a><span data-ttu-id="1726d-107">Resto intero</span><span class="sxs-lookup"><span data-stu-id="1726d-107">Integer remainder</span></span>
  
<span data-ttu-id="1726d-108">Per gli operandi di intero, il risultato di `a % b` è il valore prodotto da `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="1726d-108">For the integer operands, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="1726d-109">Il segno del resto diverso da zero è uguale a quello del primo operando, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1726d-109">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a><span data-ttu-id="1726d-110">Resto a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="1726d-110">Floating-point remainder</span></span>

<span data-ttu-id="1726d-111">Per gli operandi [float](../keywords/float.md) e [double](../keywords/double.md), il risultato di `x % y` per `x` e `y` finiti è il valore `z` tale per cui</span><span class="sxs-lookup"><span data-stu-id="1726d-111">For the [float](../keywords/float.md) and [double](../keywords/double.md) operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="1726d-112">il segno di `z`, se diverso da zero, è uguale a quello di `x`;</span><span class="sxs-lookup"><span data-stu-id="1726d-112">the sign of `z`, if non-zero, is the same as the sign of `x`;</span></span>
- <span data-ttu-id="1726d-113">il valore assoluto di `z` è il valore prodotto da `|x| - n * |y|` in cui `n` è l'intero più grande possibile, che è minore o uguale a `|x| / |y|` e `|x|` e `|y|` sono i valori assoluti di `x` e `y`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="1726d-113">the absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

<span data-ttu-id="1726d-114">Per informazioni sul comportamento dell'operatore `%` in caso di operandi non finiti, vedere la sezione [Operatore di resto](~/_csharplang/spec/expressions.md#remainder-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1726d-114">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1726d-115">Questo metodo di calcolo del resto è analogo a quello utilizzato per gli operandi di numero intero, ma differisce da IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="1726d-115">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="1726d-116">Se è necessario che l'operazione di resto sia compatibile con il valore IEEE 754, usare il metodo <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1726d-116">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1726d-117">Nell'esempio seguente viene illustrato il comportamento dell'operatore di resto per gli operandi `float` e `double`.</span><span class="sxs-lookup"><span data-stu-id="1726d-117">The following example demonstrates the behavior of the remainder operator for `float` and `double` operands:</span></span>

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

<span data-ttu-id="1726d-118">Prendere nota degli errori di arrotondamento che possono essere associati ai tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="1726d-118">Note the round-off errors that can be associated with the floating-point types.</span></span>

<span data-ttu-id="1726d-119">Per gli operandi [decimali](../keywords/decimal.md), l'operatore di resto è `%` equivale all'[operatore di resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) di tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1726d-119">For the [decimal](../keywords/decimal.md) operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

## <a name="see-also"></a><span data-ttu-id="1726d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1726d-120">See also</span></span>

- [<span data-ttu-id="1726d-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1726d-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1726d-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1726d-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1726d-123">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1726d-123">C# Operators</span></span>](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
