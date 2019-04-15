---
title: Operatore | - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312878"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fa318-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fa318-102">| operator (C# Reference)</span></span>

<span data-ttu-id="fa318-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="fa318-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="fa318-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="fa318-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="fa318-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="fa318-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa318-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa318-106">Remarks</span></span>

<span data-ttu-id="fa318-107">L'operatore binario `|` valuta i due operatori indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.</span><span class="sxs-lookup"><span data-stu-id="fa318-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.</span></span>

<span data-ttu-id="fa318-108">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fa318-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="fa318-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa318-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="fa318-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa318-110">See also</span></span>

- [<span data-ttu-id="fa318-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fa318-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fa318-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fa318-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fa318-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="fa318-113">C# operators</span></span>](index.md)