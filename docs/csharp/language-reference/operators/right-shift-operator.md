---
title: '>> Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 703d4ee50bb9f49c66df029de9c5a280449d11fa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255315"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8694f-102">Operatore >> (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8694f-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="8694f-103">L'operatore di spostamento a destra (`>>`) sposta verso destra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="8694f-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="8694f-104">Note</span><span class="sxs-lookup"><span data-stu-id="8694f-104">Remarks</span></span>

<span data-ttu-id="8694f-105">Se il primo operando è di tipo [int](../keywords/int.md) o [uint](../keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando (secondo operando e 0x1f).</span><span class="sxs-lookup"><span data-stu-id="8694f-105">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>

<span data-ttu-id="8694f-106">Se il primo operando è di tipo [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando (secondo operando e 0x3f).</span><span class="sxs-lookup"><span data-stu-id="8694f-106">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>

<span data-ttu-id="8694f-107">Se il primo operando è di tipo [int](../keywords/int.md) o [long](../keywords/long.md), lo spostamento a destra è uno spostamento aritmetico (i bit più significativi vuoti sono impostati sul bit di segno).</span><span class="sxs-lookup"><span data-stu-id="8694f-107">If the first operand is an [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="8694f-108">Se il primo operando è di tipo [uint](../keywords/uint.md) o [ulong](../keywords/ulong.md), lo spostamento a destra è uno spostamento logico (i bit più significativi vengono riempiti con zero).</span><span class="sxs-lookup"><span data-stu-id="8694f-108">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>

<span data-ttu-id="8694f-109">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>>`: il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere [int](../keywords/int.md). Per altre informazioni, vedere l'argomento relativo all'[operatore](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="8694f-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../keywords/int.md). For more information, see [operator](../keywords/operator.md).</span></span> <span data-ttu-id="8694f-110">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="8694f-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="8694f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8694f-111">Example</span></span>

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a><span data-ttu-id="8694f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8694f-112">See also</span></span>

- [<span data-ttu-id="8694f-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8694f-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8694f-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8694f-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8694f-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8694f-115">C# operators</span></span>](index.md)