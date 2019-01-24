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
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333512"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a0163-102">Operatore | (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a0163-102">| operator (C# Reference)</span></span>

<span data-ttu-id="a0163-103">Gli operatori `|` binari sono predefiniti per i tipi integrali e `bool`.</span><span class="sxs-lookup"><span data-stu-id="a0163-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="a0163-104">Per i tipi integrali, `|` calcola l'operatore OR bit per bit dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="a0163-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="a0163-105">Per gli operandi `bool`, `|` calcola l'operatore OR logico dei relativi operandi, ovvero, il risultato è `false` se e solo se entrambi gli operandi sono `false`.</span><span class="sxs-lookup"><span data-stu-id="a0163-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0163-106">Note</span><span class="sxs-lookup"><span data-stu-id="a0163-106">Remarks</span></span>

<span data-ttu-id="a0163-107">L'operatore binario `|` valuta i due operatori indipendentemente dal valore del primo, diversamente dall'[operatore OR condizionale](conditional-or-operator.md) `||`.</span><span class="sxs-lookup"><span data-stu-id="a0163-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>

<span data-ttu-id="a0163-108">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `|` (vedere [operatore](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a0163-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="a0163-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0163-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="a0163-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0163-110">See also</span></span>

- [<span data-ttu-id="a0163-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a0163-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a0163-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a0163-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a0163-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a0163-113">C# operators</span></span>](index.md)